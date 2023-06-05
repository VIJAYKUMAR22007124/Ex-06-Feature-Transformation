# Ex-06-Feature-Transformation

# AIM

To read the given data and perform Feature Transformation process and save the data to a file.



# Explanation

Feature Transformation is the process of transforming features into new features that better relate to the target.



# ALGORITHM

# STEP 1

Read the given Data



# STEP 2

Clean the Data Set using Data Cleaning Process



# STEP 3

Apply Feature Transformation techniques to all the feature of the data set



# STEP 4

Save the data to the file



# CODE:
```
import pandas as pd
df = pd.read_csv("Data_to_Transform.csv")
df

import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import statsmodels.api as sm
import scipy.stats as stats
from sklearn.preprocessing import QuantileTransformer
sm.qqplot(df['Highly Positive Skew'],fit = True,line ='45')
plt.show()

sm.qqplot(df['Moderate Positive Skew'],fit = True,line ='45')
plt.show()

sm.qqplot(df['Moderate Negative Skew'],fit = True,line ='45')
plt.show()

sm.qqplot(df['Highly Negative Skew'],fit = True,line ='45')
plt.show()

df['Highly Positive Skew'] = 1/df['Highly Positive Skew']
sm.qqplot(df['Highly Positive Skew'],fit = True,line ='45')
plt.show()

df['Highly Positive Skew'] = np.log(df['Highly Positive Skew'])
sm.qqplot(df['Highly Positive Skew'],fit = True,line ='45')
plt.show()

from sklearn.preprocessing import QuantileTransformer
qt = QuantileTransformer(output_distribution= 'normal')
df['Highly Positive Skew'] = pd.DataFrame(qt.fit_transform(df[['Highly Positive Skew']]))
sm.qqplot(df['Highly Positive Skew'],fit = True,line ='45')
plt.show()

from sklearn.preprocessing import PowerTransformer
t = PowerTransformer("yeo-johnson")
df['Highly Positive Skew_1'] = pd.DataFrame(t.fit_transform(df[['Highly Positive Skew']]))
sm.qqplot(df['Highly Positive Skew'],line ='45')
plt.show()

```


# OUPUT:

![Screenshot (342)](https://user-images.githubusercontent.com/119657657/233926739-4e00e32b-9bd9-48e3-959d-32d35f6106a6.png)

![Screenshot (343)](https://user-images.githubusercontent.com/119657657/233927094-24aed064-b2bb-40c8-8a22-0738400eb8d9.png)

![Screenshot (344)](https://user-images.githubusercontent.com/119657657/233927170-bdb9c547-ac03-47f8-acc0-79fb2b060d4b.png)

![Screenshot (345)](https://user-images.githubusercontent.com/119657657/233927356-bad94e04-da9f-40e3-8af4-a395617bcb46.png)

![Screenshot (346)](https://user-images.githubusercontent.com/119657657/233927451-87894fe2-48ff-47cb-ac50-067bd7000825.png)

![Screenshot (347)](https://user-images.githubusercontent.com/119657657/233927523-58b67648-00e3-4933-b808-5e36086ccc91.png)

![Screenshot (348)](https://user-images.githubusercontent.com/119657657/233927576-f18b0d46-f8ce-46de-b5a7-845243b98d00.png)


![Screenshot (349)](https://user-images.githubusercontent.com/119657657/233927622-fed872eb-d6de-4778-b1e0-dfb8ef35371c.png)

![Screenshot (350)](https://user-images.githubusercontent.com/119657657/233927698-cec6c13d-3513-4ad0-9dd4-8ee840494643.png)

# RESULT :

The Given Data is Read and performed with the Feature Transformation techniques and the data is stored.


