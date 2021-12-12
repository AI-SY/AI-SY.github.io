## 캐글 데이터셋(Customer Personality Analysis)을 활용한 데이터 분석 및 시각화
#### 캐글 사이트의 marketing_campaign.csv 데이터를 활용하여 고객군의 특성과 지출관계를 분석하고 시각화 해 보았습니다.


```python
import pandas as pd
```


```python
data = pd.read_csv('marketing_campaign.csv', sep="\t")
data.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>Year_Birth</th>
      <th>Education</th>
      <th>Marital_Status</th>
      <th>Income</th>
      <th>Kidhome</th>
      <th>Teenhome</th>
      <th>Dt_Customer</th>
      <th>Recency</th>
      <th>MntWines</th>
      <th>...</th>
      <th>NumWebVisitsMonth</th>
      <th>AcceptedCmp3</th>
      <th>AcceptedCmp4</th>
      <th>AcceptedCmp5</th>
      <th>AcceptedCmp1</th>
      <th>AcceptedCmp2</th>
      <th>Complain</th>
      <th>Z_CostContact</th>
      <th>Z_Revenue</th>
      <th>Response</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>5524</td>
      <td>1957</td>
      <td>Graduation</td>
      <td>Single</td>
      <td>58138.0</td>
      <td>0</td>
      <td>0</td>
      <td>04-09-2012</td>
      <td>58</td>
      <td>635</td>
      <td>...</td>
      <td>7</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>11</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2174</td>
      <td>1954</td>
      <td>Graduation</td>
      <td>Single</td>
      <td>46344.0</td>
      <td>1</td>
      <td>1</td>
      <td>08-03-2014</td>
      <td>38</td>
      <td>11</td>
      <td>...</td>
      <td>5</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>11</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4141</td>
      <td>1965</td>
      <td>Graduation</td>
      <td>Together</td>
      <td>71613.0</td>
      <td>0</td>
      <td>0</td>
      <td>21-08-2013</td>
      <td>26</td>
      <td>426</td>
      <td>...</td>
      <td>4</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>11</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>6182</td>
      <td>1984</td>
      <td>Graduation</td>
      <td>Together</td>
      <td>26646.0</td>
      <td>1</td>
      <td>0</td>
      <td>10-02-2014</td>
      <td>26</td>
      <td>11</td>
      <td>...</td>
      <td>6</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>11</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5324</td>
      <td>1981</td>
      <td>PhD</td>
      <td>Married</td>
      <td>58293.0</td>
      <td>1</td>
      <td>0</td>
      <td>19-01-2014</td>
      <td>94</td>
      <td>173</td>
      <td>...</td>
      <td>5</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>11</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 29 columns</p>
</div>




```python
print("데이터의 행과 컬럼수 는 : ", data.shape)
```

    데이터의 행과 컬럼수 는 :  (2240, 29)
    


```python
print("데이터 차원 : ", data.ndim)
```

    데이터 차원 :  2
    


```python
print("컬럼명 : ", data.columns)
```

    컬럼명 :  Index(['ID', 'Year_Birth', 'Education', 'Marital_Status', 'Income', 'Kidhome',
           'Teenhome', 'Dt_Customer', 'Recency', 'MntWines', 'MntFruits',
           'MntMeatProducts', 'MntFishProducts', 'MntSweetProducts',
           'MntGoldProds', 'NumDealsPurchases', 'NumWebPurchases',
           'NumCatalogPurchases', 'NumStorePurchases', 'NumWebVisitsMonth',
           'AcceptedCmp3', 'AcceptedCmp4', 'AcceptedCmp5', 'AcceptedCmp1',
           'AcceptedCmp2', 'Complain', 'Z_CostContact', 'Z_Revenue', 'Response'],
          dtype='object')
    


```python
data.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 2240 entries, 0 to 2239
    Data columns (total 29 columns):
     #   Column               Non-Null Count  Dtype  
    ---  ------               --------------  -----  
     0   ID                   2240 non-null   int64  
     1   Year_Birth           2240 non-null   int64  
     2   Education            2240 non-null   object 
     3   Marital_Status       2240 non-null   object 
     4   Income               2216 non-null   float64
     5   Kidhome              2240 non-null   int64  
     6   Teenhome             2240 non-null   int64  
     7   Dt_Customer          2240 non-null   object 
     8   Recency              2240 non-null   int64  
     9   MntWines             2240 non-null   int64  
     10  MntFruits            2240 non-null   int64  
     11  MntMeatProducts      2240 non-null   int64  
     12  MntFishProducts      2240 non-null   int64  
     13  MntSweetProducts     2240 non-null   int64  
     14  MntGoldProds         2240 non-null   int64  
     15  NumDealsPurchases    2240 non-null   int64  
     16  NumWebPurchases      2240 non-null   int64  
     17  NumCatalogPurchases  2240 non-null   int64  
     18  NumStorePurchases    2240 non-null   int64  
     19  NumWebVisitsMonth    2240 non-null   int64  
     20  AcceptedCmp3         2240 non-null   int64  
     21  AcceptedCmp4         2240 non-null   int64  
     22  AcceptedCmp5         2240 non-null   int64  
     23  AcceptedCmp1         2240 non-null   int64  
     24  AcceptedCmp2         2240 non-null   int64  
     25  Complain             2240 non-null   int64  
     26  Z_CostContact        2240 non-null   int64  
     27  Z_Revenue            2240 non-null   int64  
     28  Response             2240 non-null   int64  
    dtypes: float64(1), int64(25), object(3)
    memory usage: 507.6+ KB
    


```python
round(data.describe(),0)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>Year_Birth</th>
      <th>Income</th>
      <th>Kidhome</th>
      <th>Teenhome</th>
      <th>Recency</th>
      <th>MntWines</th>
      <th>MntFruits</th>
      <th>MntMeatProducts</th>
      <th>MntFishProducts</th>
      <th>...</th>
      <th>NumWebVisitsMonth</th>
      <th>AcceptedCmp3</th>
      <th>AcceptedCmp4</th>
      <th>AcceptedCmp5</th>
      <th>AcceptedCmp1</th>
      <th>AcceptedCmp2</th>
      <th>Complain</th>
      <th>Z_CostContact</th>
      <th>Z_Revenue</th>
      <th>Response</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>2240.0</td>
      <td>2240.0</td>
      <td>2216.0</td>
      <td>2240.0</td>
      <td>2240.0</td>
      <td>2240.0</td>
      <td>2240.0</td>
      <td>2240.0</td>
      <td>2240.0</td>
      <td>2240.0</td>
      <td>...</td>
      <td>2240.0</td>
      <td>2240.0</td>
      <td>2240.0</td>
      <td>2240.0</td>
      <td>2240.0</td>
      <td>2240.0</td>
      <td>2240.0</td>
      <td>2240.0</td>
      <td>2240.0</td>
      <td>2240.0</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>5592.0</td>
      <td>1969.0</td>
      <td>52247.0</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>49.0</td>
      <td>304.0</td>
      <td>26.0</td>
      <td>167.0</td>
      <td>38.0</td>
      <td>...</td>
      <td>5.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>3.0</td>
      <td>11.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>std</th>
      <td>3247.0</td>
      <td>12.0</td>
      <td>25173.0</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>29.0</td>
      <td>337.0</td>
      <td>40.0</td>
      <td>226.0</td>
      <td>55.0</td>
      <td>...</td>
      <td>2.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>min</th>
      <td>0.0</td>
      <td>1893.0</td>
      <td>1730.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>3.0</td>
      <td>11.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>2828.0</td>
      <td>1959.0</td>
      <td>35303.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>24.0</td>
      <td>24.0</td>
      <td>1.0</td>
      <td>16.0</td>
      <td>3.0</td>
      <td>...</td>
      <td>3.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>3.0</td>
      <td>11.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>5458.0</td>
      <td>1970.0</td>
      <td>51382.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>49.0</td>
      <td>174.0</td>
      <td>8.0</td>
      <td>67.0</td>
      <td>12.0</td>
      <td>...</td>
      <td>6.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>3.0</td>
      <td>11.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>8428.0</td>
      <td>1977.0</td>
      <td>68522.0</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>74.0</td>
      <td>504.0</td>
      <td>33.0</td>
      <td>232.0</td>
      <td>50.0</td>
      <td>...</td>
      <td>7.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>3.0</td>
      <td>11.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>max</th>
      <td>11191.0</td>
      <td>1996.0</td>
      <td>666666.0</td>
      <td>2.0</td>
      <td>2.0</td>
      <td>99.0</td>
      <td>1493.0</td>
      <td>199.0</td>
      <td>1725.0</td>
      <td>259.0</td>
      <td>...</td>
      <td>20.0</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>3.0</td>
      <td>11.0</td>
      <td>1.0</td>
    </tr>
  </tbody>
</table>
<p>8 rows × 26 columns</p>
</div>




```python
import matplotlib.pyplot as plt
import seaborn as sns
```


```python
# 결측치 확인
sns.heatmap(data.isnull(), cbar=False)
```




    <AxesSubplot:>




    
![png](output_9_1.png)
    



```python
# Income 컬럼의 결측치 행 확인
data.loc[data["Income"].isnull(),'Income']
```




    10     NaN
    27     NaN
    43     NaN
    48     NaN
    58     NaN
    71     NaN
    90     NaN
    91     NaN
    92     NaN
    128    NaN
    133    NaN
    312    NaN
    319    NaN
    1379   NaN
    1382   NaN
    1383   NaN
    1386   NaN
    2059   NaN
    2061   NaN
    2078   NaN
    2079   NaN
    2081   NaN
    2084   NaN
    2228   NaN
    Name: Income, dtype: float64




```python
# Income 컬럼의 결측치 갯수 확인
data['Income'].isnull().sum()
```




    24




```python
# Income 컬럼의 평균으로 결측치 채우기
data['Income']= data['Income'].fillna(data['Income'].mean())
```


```python
data['Income'].isnull().sum()
```




    0




```python
# 중복된 열 확인
data[data.duplicated()]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>Year_Birth</th>
      <th>Education</th>
      <th>Marital_Status</th>
      <th>Income</th>
      <th>Kidhome</th>
      <th>Teenhome</th>
      <th>Dt_Customer</th>
      <th>Recency</th>
      <th>MntWines</th>
      <th>...</th>
      <th>NumWebVisitsMonth</th>
      <th>AcceptedCmp3</th>
      <th>AcceptedCmp4</th>
      <th>AcceptedCmp5</th>
      <th>AcceptedCmp1</th>
      <th>AcceptedCmp2</th>
      <th>Complain</th>
      <th>Z_CostContact</th>
      <th>Z_Revenue</th>
      <th>Response</th>
    </tr>
  </thead>
  <tbody>
  </tbody>
</table>
<p>0 rows × 29 columns</p>
</div>




```python
# 각 컬럼들의 고유값들의 수 확인
data.nunique()
```




    ID                     2240
    Year_Birth               59
    Education                 5
    Marital_Status            8
    Income                 1975
    Kidhome                   3
    Teenhome                  3
    Dt_Customer             663
    Recency                 100
    MntWines                776
    MntFruits               158
    MntMeatProducts         558
    MntFishProducts         182
    MntSweetProducts        177
    MntGoldProds            213
    NumDealsPurchases        15
    NumWebPurchases          15
    NumCatalogPurchases      14
    NumStorePurchases        14
    NumWebVisitsMonth        16
    AcceptedCmp3              2
    AcceptedCmp4              2
    AcceptedCmp5              2
    AcceptedCmp1              2
    AcceptedCmp2              2
    Complain                  2
    Z_CostContact             1
    Z_Revenue                 1
    Response                  2
    dtype: int64




```python
# 각 컬럼별 연관성을 확인해보기
import matplotlib.pyplot as plt

plt.figure(figsize=(12,12))
sns.heatmap(data.corr(), annot=True)
# 필요없는 컬럼을 제외시켜주겠습니다.
```




    <AxesSubplot:>




    
![png](output_16_1.png)
    



```python
# 사람과 관계된 속성과 Mnt(2년간 각 제품에 대해 지출한 금액)관련 속성을 제외하고 다 없애주겠습니다.
df = data.iloc[:,:15]
df.head(20)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>Year_Birth</th>
      <th>Education</th>
      <th>Marital_Status</th>
      <th>Income</th>
      <th>Kidhome</th>
      <th>Teenhome</th>
      <th>Dt_Customer</th>
      <th>Recency</th>
      <th>MntWines</th>
      <th>MntFruits</th>
      <th>MntMeatProducts</th>
      <th>MntFishProducts</th>
      <th>MntSweetProducts</th>
      <th>MntGoldProds</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>5524</td>
      <td>1957</td>
      <td>Graduation</td>
      <td>Single</td>
      <td>58138.000000</td>
      <td>0</td>
      <td>0</td>
      <td>04-09-2012</td>
      <td>58</td>
      <td>635</td>
      <td>88</td>
      <td>546</td>
      <td>172</td>
      <td>88</td>
      <td>88</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2174</td>
      <td>1954</td>
      <td>Graduation</td>
      <td>Single</td>
      <td>46344.000000</td>
      <td>1</td>
      <td>1</td>
      <td>08-03-2014</td>
      <td>38</td>
      <td>11</td>
      <td>1</td>
      <td>6</td>
      <td>2</td>
      <td>1</td>
      <td>6</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4141</td>
      <td>1965</td>
      <td>Graduation</td>
      <td>Together</td>
      <td>71613.000000</td>
      <td>0</td>
      <td>0</td>
      <td>21-08-2013</td>
      <td>26</td>
      <td>426</td>
      <td>49</td>
      <td>127</td>
      <td>111</td>
      <td>21</td>
      <td>42</td>
    </tr>
    <tr>
      <th>3</th>
      <td>6182</td>
      <td>1984</td>
      <td>Graduation</td>
      <td>Together</td>
      <td>26646.000000</td>
      <td>1</td>
      <td>0</td>
      <td>10-02-2014</td>
      <td>26</td>
      <td>11</td>
      <td>4</td>
      <td>20</td>
      <td>10</td>
      <td>3</td>
      <td>5</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5324</td>
      <td>1981</td>
      <td>PhD</td>
      <td>Married</td>
      <td>58293.000000</td>
      <td>1</td>
      <td>0</td>
      <td>19-01-2014</td>
      <td>94</td>
      <td>173</td>
      <td>43</td>
      <td>118</td>
      <td>46</td>
      <td>27</td>
      <td>15</td>
    </tr>
    <tr>
      <th>5</th>
      <td>7446</td>
      <td>1967</td>
      <td>Master</td>
      <td>Together</td>
      <td>62513.000000</td>
      <td>0</td>
      <td>1</td>
      <td>09-09-2013</td>
      <td>16</td>
      <td>520</td>
      <td>42</td>
      <td>98</td>
      <td>0</td>
      <td>42</td>
      <td>14</td>
    </tr>
    <tr>
      <th>6</th>
      <td>965</td>
      <td>1971</td>
      <td>Graduation</td>
      <td>Divorced</td>
      <td>55635.000000</td>
      <td>0</td>
      <td>1</td>
      <td>13-11-2012</td>
      <td>34</td>
      <td>235</td>
      <td>65</td>
      <td>164</td>
      <td>50</td>
      <td>49</td>
      <td>27</td>
    </tr>
    <tr>
      <th>7</th>
      <td>6177</td>
      <td>1985</td>
      <td>PhD</td>
      <td>Married</td>
      <td>33454.000000</td>
      <td>1</td>
      <td>0</td>
      <td>08-05-2013</td>
      <td>32</td>
      <td>76</td>
      <td>10</td>
      <td>56</td>
      <td>3</td>
      <td>1</td>
      <td>23</td>
    </tr>
    <tr>
      <th>8</th>
      <td>4855</td>
      <td>1974</td>
      <td>PhD</td>
      <td>Together</td>
      <td>30351.000000</td>
      <td>1</td>
      <td>0</td>
      <td>06-06-2013</td>
      <td>19</td>
      <td>14</td>
      <td>0</td>
      <td>24</td>
      <td>3</td>
      <td>3</td>
      <td>2</td>
    </tr>
    <tr>
      <th>9</th>
      <td>5899</td>
      <td>1950</td>
      <td>PhD</td>
      <td>Together</td>
      <td>5648.000000</td>
      <td>1</td>
      <td>1</td>
      <td>13-03-2014</td>
      <td>68</td>
      <td>28</td>
      <td>0</td>
      <td>6</td>
      <td>1</td>
      <td>1</td>
      <td>13</td>
    </tr>
    <tr>
      <th>10</th>
      <td>1994</td>
      <td>1983</td>
      <td>Graduation</td>
      <td>Married</td>
      <td>52247.251354</td>
      <td>1</td>
      <td>0</td>
      <td>15-11-2013</td>
      <td>11</td>
      <td>5</td>
      <td>5</td>
      <td>6</td>
      <td>0</td>
      <td>2</td>
      <td>1</td>
    </tr>
    <tr>
      <th>11</th>
      <td>387</td>
      <td>1976</td>
      <td>Basic</td>
      <td>Married</td>
      <td>7500.000000</td>
      <td>0</td>
      <td>0</td>
      <td>13-11-2012</td>
      <td>59</td>
      <td>6</td>
      <td>16</td>
      <td>11</td>
      <td>11</td>
      <td>1</td>
      <td>16</td>
    </tr>
    <tr>
      <th>12</th>
      <td>2125</td>
      <td>1959</td>
      <td>Graduation</td>
      <td>Divorced</td>
      <td>63033.000000</td>
      <td>0</td>
      <td>0</td>
      <td>15-11-2013</td>
      <td>82</td>
      <td>194</td>
      <td>61</td>
      <td>480</td>
      <td>225</td>
      <td>112</td>
      <td>30</td>
    </tr>
    <tr>
      <th>13</th>
      <td>8180</td>
      <td>1952</td>
      <td>Master</td>
      <td>Divorced</td>
      <td>59354.000000</td>
      <td>1</td>
      <td>1</td>
      <td>15-11-2013</td>
      <td>53</td>
      <td>233</td>
      <td>2</td>
      <td>53</td>
      <td>3</td>
      <td>5</td>
      <td>14</td>
    </tr>
    <tr>
      <th>14</th>
      <td>2569</td>
      <td>1987</td>
      <td>Graduation</td>
      <td>Married</td>
      <td>17323.000000</td>
      <td>0</td>
      <td>0</td>
      <td>10-10-2012</td>
      <td>38</td>
      <td>3</td>
      <td>14</td>
      <td>17</td>
      <td>6</td>
      <td>1</td>
      <td>5</td>
    </tr>
    <tr>
      <th>15</th>
      <td>2114</td>
      <td>1946</td>
      <td>PhD</td>
      <td>Single</td>
      <td>82800.000000</td>
      <td>0</td>
      <td>0</td>
      <td>24-11-2012</td>
      <td>23</td>
      <td>1006</td>
      <td>22</td>
      <td>115</td>
      <td>59</td>
      <td>68</td>
      <td>45</td>
    </tr>
    <tr>
      <th>16</th>
      <td>9736</td>
      <td>1980</td>
      <td>Graduation</td>
      <td>Married</td>
      <td>41850.000000</td>
      <td>1</td>
      <td>1</td>
      <td>24-12-2012</td>
      <td>51</td>
      <td>53</td>
      <td>5</td>
      <td>19</td>
      <td>2</td>
      <td>13</td>
      <td>4</td>
    </tr>
    <tr>
      <th>17</th>
      <td>4939</td>
      <td>1946</td>
      <td>Graduation</td>
      <td>Together</td>
      <td>37760.000000</td>
      <td>0</td>
      <td>0</td>
      <td>31-08-2012</td>
      <td>20</td>
      <td>84</td>
      <td>5</td>
      <td>38</td>
      <td>150</td>
      <td>12</td>
      <td>28</td>
    </tr>
    <tr>
      <th>18</th>
      <td>6565</td>
      <td>1949</td>
      <td>Master</td>
      <td>Married</td>
      <td>76995.000000</td>
      <td>0</td>
      <td>1</td>
      <td>28-03-2013</td>
      <td>91</td>
      <td>1012</td>
      <td>80</td>
      <td>498</td>
      <td>0</td>
      <td>16</td>
      <td>176</td>
    </tr>
    <tr>
      <th>19</th>
      <td>2278</td>
      <td>1985</td>
      <td>2n Cycle</td>
      <td>Single</td>
      <td>33812.000000</td>
      <td>1</td>
      <td>0</td>
      <td>03-11-2012</td>
      <td>86</td>
      <td>4</td>
      <td>17</td>
      <td>19</td>
      <td>30</td>
      <td>24</td>
      <td>39</td>
    </tr>
  </tbody>
</table>
</div>




```python
plt.figure(figsize=(12,12))
sns.heatmap(df.corr(), annot=True)
# Income(지출) 컬럼과 각 제품에 대한 지출의 관련도가 높습니다.
# Kidhome(자녀 수) 컬럼은 제품에 대한 지출 관련도가 확연히 낮습니다.
```




    <AxesSubplot:>




    
![png](output_18_1.png)
    


### 데이터 전처리


```python
# Education(학력) 컬럼을 post, under로 재구분 했습니다.
df['Education'] = df['Education'].replace(['PhD','2n Cycle','Graduation', 'Master'],'Post Graduate')  
df['Education'] = df['Education'].replace(['Basic'], 'Under Graduate')
```


```python
# Marital_Status(결혼여부) 컬럼을 기혼과 미혼으로 재구분 했습니다.
df['Marital_Status'] = df['Marital_Status'].replace(['Married', 'Together'],'Relationship')
df['Marital_Status'] = df['Marital_Status'].replace(['Divorced', 'Widow', 'Alone', 'YOLO', 'Absurd'],'Single')
```


```python
# 자녀컬럼을 새로 생성해 자녀수와 청소년수의 각 컬럼을 합쳤습니다.
df['Kids'] = df['Kidhome'] + df['Teenhome']
```


```python
# 지출컬럼을 새로 생성해서 각 제품에 대한 지출을 합쳤습니다.
df['Expenses'] = df['MntWines'] + df['MntFruits'] + df['MntMeatProducts'] + df['MntFishProducts'] + df['MntSweetProducts'] + df['MntGoldProds']
```


```python
# 나이 컬럼 새로 만들었습니다.
df['Age'] = 2021-df['Year_Birth']
```


```python
df = df.loc[:,['ID','Age','Education','Marital_Status','Income','Kids','Expenses']]
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>Age</th>
      <th>Education</th>
      <th>Marital_Status</th>
      <th>Income</th>
      <th>Kids</th>
      <th>Expenses</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>5524</td>
      <td>64</td>
      <td>Post Graduate</td>
      <td>Single</td>
      <td>58138.0</td>
      <td>0</td>
      <td>1617</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2174</td>
      <td>67</td>
      <td>Post Graduate</td>
      <td>Single</td>
      <td>46344.0</td>
      <td>2</td>
      <td>27</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4141</td>
      <td>56</td>
      <td>Post Graduate</td>
      <td>Relationship</td>
      <td>71613.0</td>
      <td>0</td>
      <td>776</td>
    </tr>
    <tr>
      <th>3</th>
      <td>6182</td>
      <td>37</td>
      <td>Post Graduate</td>
      <td>Relationship</td>
      <td>26646.0</td>
      <td>1</td>
      <td>53</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5324</td>
      <td>40</td>
      <td>Post Graduate</td>
      <td>Relationship</td>
      <td>58293.0</td>
      <td>1</td>
      <td>422</td>
    </tr>
  </tbody>
</table>
</div>




```python
plt.figure(figsize=(7,7))
sns.heatmap(df.corr(), annot=True)
```




    <AxesSubplot:>




    
![png](output_27_1.png)
    



```python
# 결혼여부와 지출관의 관계를 바이올린 플롯으로 그려보았습니다.
sns.violinplot(data=df,
              x='Marital_Status',
              y='Expenses')
plt.show()
```


    
![png](output_28_0.png)
    



```python
# 소득과 지출간의 관계를 스케터 그래프로 그려보았습니다.
sns.scatterplot(data=df,
              x='Income',
              y='Expenses')
```




    <AxesSubplot:xlabel='Income', ylabel='Expenses'>




    
![png](output_29_1.png)
    



```python
# 이상치 값을 찾아 없애주도록 하겠습니다.
df[df['Income']>600000]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>Age</th>
      <th>Education</th>
      <th>Marital_Status</th>
      <th>Income</th>
      <th>Kids</th>
      <th>Expenses</th>
    </tr>
  </thead>
  <tbody>
  </tbody>
</table>
</div>




```python
df = df.drop(index=2233, axis=0)
```


```python
# 기혼,미혼에 대해서 각각 소득과 지출간의 관계를 보여주도록 했습니다.
sns.lmplot(x = 'Income', y = 'Expenses', data = df, hue = 'Marital_Status')
```




    <seaborn.axisgrid.FacetGrid at 0x256b6fe8fd0>




    
![png](output_32_1.png)
    



```python

```
