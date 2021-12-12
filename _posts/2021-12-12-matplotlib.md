```python
import matplotlib.pyplot as plt
```

#### 선 그래프


```python
# plot 함수 - 일직선으로 되어있는 line plot 그리기
y = [2,4,6]

plt.plot(y) # 그래프 그리기
plt.show()  # 그래프 출력
```


    
![png](output_2_0.png)
    



```python
y= [2,4,6]
x= [1,2,3]

plt.plot(x,y)
plt.show()
```


    
![png](output_3_0.png)
    



```python
#line style  -> ls (엘에스)
# 그려지는 라인의 스타일을 지정하는 속성
plt.plot(x, y, linestyle = '--')
plt.show()
```


    
![png](output_4_0.png)
    



```python
x = [2,4,6,8]
y = [10,13,15,20]
y2 = [10,20,17,15]
plt.plot(x,y, ls='-')
plt.plot(x,y2, ls = ':')
plt.show()
```


    
![png](output_5_0.png)
    



```python
# marker
plt.plot(x,y,marker = 'o') # 'p','.'
plt.show()
```


    
![png](output_6_0.png)
    


![KakaoTalk_20211029_143844893.png](attachment:KakaoTalk_20211029_143844893.png)


```python
# line width -> lw
# 라인의 두께 지정
plt.plot(x,y, linewidth = 5)
plt.show()
```


    
![png](output_8_0.png)
    



```python
# line color
plt.plot(x,y, color='#FF98A3', marker='o', markerfacecolor='#CC99FF') # RGB 컬러 코드 값
plt.show()
```


    
![png](output_9_0.png)
    



```python
plt.plot(x,y, color='#FF98A3', marker='o', mfc='#CC99FF', markersize = 10) # RGB 컬러 코드 값
plt.show()
```


    
![png](output_10_0.png)
    



```python
import numpy as np
x=np.arange(7)
y=[1,4,5,8,9,5,3]

plt.plot(x,y, color='g', ls='--', marker='o')
plt.show()
plt.plot(x,y, color='r', ls=':', marker='s', mfc='b', markersize=8)
plt.show()
```


    
![png](output_11_0.png)
    



    
![png](output_11_1.png)
    



```python
plt.plot(x,y, ls='--',lw = 5 ,marker='o', markersize=15, mec='g', mew=5, mfc='r')
plt.show()
```


    
![png](output_12_0.png)
    



```python
# 범위 지정 (그림의 영역 지정)
# xlim : x 범위 지정
# ylim : y 범위 지정
plt.plot(x,y, ls='--',lw = 5 ,marker='o', markersize=15, mec='g', mew=5, mfc='r')
plt.xlim(-1,7)
plt.ylim(-3,11)
plt.show()


```


    
![png](output_13_0.png)
    



```python
# ticks : 틱(축 상의 위치)
plt.plot(x,y, ls='--',lw = 5 ,marker='o', markersize=15, mec='g', mew=5, mfc='r')
plt.xticks([0,3,6])
plt.yticks([1,5,9])

plt.show()
```


    
![png](output_14_0.png)
    



```python
# grid
# 틱의 위치를 잘 보기 위해
plt.plot(x,y, ls='--',lw = 5 ,marker='o', markersize=15, mec='g', mew=5, mfc='r')
plt.grid()
plt.show()
```


    
![png](output_15_0.png)
    



```python
x = [1,2,3,4]
y = [2,4,6,8]
z = [3,6,9,12]
plt.plot(x)
plt.plot(y)
plt.plot(z)
plt.show()
```


    
![png](output_16_0.png)
    



```python
plt.plot(x, color = 'r')
plt.plot(y, color = 'm')
plt.plot(z, color = 'g')
plt.show()
```


    
![png](output_17_0.png)
    



```python
# 범례 (그래프의 데이터를 설명해주는 기능)
x = [1,2,3,4]
y = [2,4,6,8]
z = [3,6,9,12]
plt.plot(x, label = 'x')
plt.plot(y, label = 'y')
plt.plot(z, label = 'z')
plt.legend() #label 붙여놓은거 범례로 보여주기
plt.xlabel('x축')
plt.ylabel('y축')
plt.title('x,y,z 그래프')
plt.show()
```

    C:\Users\SMHRD\anaconda3\lib\site-packages\matplotlib\backends\backend_agg.py:238: RuntimeWarning: Glyph 44536 missing from current font.
      font.set_text(s, 0.0, flags=flags)
    C:\Users\SMHRD\anaconda3\lib\site-packages\matplotlib\backends\backend_agg.py:238: RuntimeWarning: Glyph 47000 missing from current font.
      font.set_text(s, 0.0, flags=flags)
    C:\Users\SMHRD\anaconda3\lib\site-packages\matplotlib\backends\backend_agg.py:238: RuntimeWarning: Glyph 54532 missing from current font.
      font.set_text(s, 0.0, flags=flags)
    C:\Users\SMHRD\anaconda3\lib\site-packages\matplotlib\backends\backend_agg.py:238: RuntimeWarning: Glyph 52629 missing from current font.
      font.set_text(s, 0.0, flags=flags)
    C:\Users\SMHRD\anaconda3\lib\site-packages\matplotlib\backends\backend_agg.py:201: RuntimeWarning: Glyph 52629 missing from current font.
      font.set_text(s, 0, flags=flags)
    C:\Users\SMHRD\anaconda3\lib\site-packages\matplotlib\backends\backend_agg.py:201: RuntimeWarning: Glyph 44536 missing from current font.
      font.set_text(s, 0, flags=flags)
    C:\Users\SMHRD\anaconda3\lib\site-packages\matplotlib\backends\backend_agg.py:201: RuntimeWarning: Glyph 47000 missing from current font.
      font.set_text(s, 0, flags=flags)
    C:\Users\SMHRD\anaconda3\lib\site-packages\matplotlib\backends\backend_agg.py:201: RuntimeWarning: Glyph 54532 missing from current font.
      font.set_text(s, 0, flags=flags)
    


    
![png](output_18_1.png)
    


#### 막대 그래프


```python
# bar chart
x = [0,1,2,3,4,5]
y = [80,85,70,60,50,90]
plt.bar(x,y)
plt.show()
```


    
![png](output_20_0.png)
    



```python
x = ['a','b','c',"d",'e','f']
y = [80,85,70,60,50,90]
plt.bar(x,y, color = 'gray')
plt.show()
```


    
![png](output_21_0.png)
    



```python
import pandas as pd
```


```python
data = pd.read_csv('Traffic_Accident_2017.csv', encoding = 'euc-kr')
```


```python
data.tail(4)
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
      <th>발생년</th>
      <th>발생년월일시</th>
      <th>발생분</th>
      <th>주야</th>
      <th>요일</th>
      <th>사망자수</th>
      <th>사상자수</th>
      <th>중상자수</th>
      <th>경상자수</th>
      <th>부상신고자수</th>
      <th>...</th>
      <th>도로형태_대분류</th>
      <th>도로형태</th>
      <th>당사자종별_1당_대분류</th>
      <th>당사자종별_1당</th>
      <th>당사자종별_2당_대분류</th>
      <th>당사자종별_2당</th>
      <th>발생위치X_UTMK</th>
      <th>발생위치Y_UTMK</th>
      <th>경도</th>
      <th>위도</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>4061</th>
      <td>2017</td>
      <td>2017123118</td>
      <td>25</td>
      <td>야간</td>
      <td>일</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>단일로</td>
      <td>기타단일로</td>
      <td>원동기장치자전거</td>
      <td>원동기장치자전거</td>
      <td>없음</td>
      <td>없음</td>
      <td>1160683</td>
      <td>1704380</td>
      <td>129.267745</td>
      <td>35.322087</td>
    </tr>
    <tr>
      <th>4062</th>
      <td>2017</td>
      <td>2017123119</td>
      <td>55</td>
      <td>야간</td>
      <td>일</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>단일로</td>
      <td>기타단일로</td>
      <td>화물차</td>
      <td>화물차</td>
      <td>없음</td>
      <td>없음</td>
      <td>1067639</td>
      <td>1980346</td>
      <td>128.268522</td>
      <td>37.820351</td>
    </tr>
    <tr>
      <th>4063</th>
      <td>2017</td>
      <td>2017123120</td>
      <td>40</td>
      <td>야간</td>
      <td>일</td>
      <td>1</td>
      <td>11</td>
      <td>1</td>
      <td>9</td>
      <td>0</td>
      <td>...</td>
      <td>단일로</td>
      <td>기타단일로</td>
      <td>승용차</td>
      <td>승용차</td>
      <td>승용차</td>
      <td>승용차</td>
      <td>961004</td>
      <td>1987481</td>
      <td>127.056525</td>
      <td>37.886331</td>
    </tr>
    <tr>
      <th>4064</th>
      <td>2017</td>
      <td>2017123123</td>
      <td>15</td>
      <td>야간</td>
      <td>일</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>단일로</td>
      <td>기타단일로</td>
      <td>이륜차</td>
      <td>이륜차</td>
      <td>보행자</td>
      <td>보행자</td>
      <td>995304</td>
      <td>1814453</td>
      <td>127.447679</td>
      <td>36.327435</td>
    </tr>
  </tbody>
</table>
<p>4 rows × 27 columns</p>
</div>




```python
data.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 4065 entries, 0 to 4064
    Data columns (total 27 columns):
     #   Column        Non-Null Count  Dtype  
    ---  ------        --------------  -----  
     0   발생년           4065 non-null   int64  
     1   발생년월일시        4065 non-null   int64  
     2   발생분           4065 non-null   int64  
     3   주야            4065 non-null   object 
     4   요일            4065 non-null   object 
     5   사망자수          4065 non-null   int64  
     6   사상자수          4065 non-null   int64  
     7   중상자수          4065 non-null   int64  
     8   경상자수          4065 non-null   int64  
     9   부상신고자수        4065 non-null   int64  
     10  발생지시도         4065 non-null   object 
     11  발생지시군구        4065 non-null   object 
     12  사고유형_대분류      4065 non-null   object 
     13  사고유형_중분류      4065 non-null   object 
     14  사고유형          4065 non-null   object 
     15  법규위반_대분류      4065 non-null   object 
     16  법규위반          4065 non-null   object 
     17  도로형태_대분류      4065 non-null   object 
     18  도로형태          4065 non-null   object 
     19  당사자종별_1당_대분류  4065 non-null   object 
     20  당사자종별_1당      4065 non-null   object 
     21  당사자종별_2당_대분류  4065 non-null   object 
     22  당사자종별_2당      4065 non-null   object 
     23  발생위치X_UTMK    4065 non-null   int64  
     24  발생위치Y_UTMK    4065 non-null   int64  
     25  경도            4065 non-null   float64
     26  위도            4065 non-null   float64
    dtypes: float64(2), int64(10), object(15)
    memory usage: 857.6+ KB
    


```python
# 요일별 교통사고 시각화

temp = data['요일'].value_counts()
```


```python
y= temp[['월','화','수','목','금','토','일']]
x= y.index
plt.ylim(500,620)
plt.bar(x,y)
plt.show()
```

    C:\Users\SMHRD\anaconda3\lib\site-packages\matplotlib\backends\backend_agg.py:238: RuntimeWarning: Glyph 50900 missing from current font.
      font.set_text(s, 0.0, flags=flags)
    C:\Users\SMHRD\anaconda3\lib\site-packages\matplotlib\backends\backend_agg.py:238: RuntimeWarning: Glyph 54868 missing from current font.
      font.set_text(s, 0.0, flags=flags)
    C:\Users\SMHRD\anaconda3\lib\site-packages\matplotlib\backends\backend_agg.py:238: RuntimeWarning: Glyph 49688 missing from current font.
      font.set_text(s, 0.0, flags=flags)
    C:\Users\SMHRD\anaconda3\lib\site-packages\matplotlib\backends\backend_agg.py:238: RuntimeWarning: Glyph 47785 missing from current font.
      font.set_text(s, 0.0, flags=flags)
    C:\Users\SMHRD\anaconda3\lib\site-packages\matplotlib\backends\backend_agg.py:238: RuntimeWarning: Glyph 44552 missing from current font.
      font.set_text(s, 0.0, flags=flags)
    C:\Users\SMHRD\anaconda3\lib\site-packages\matplotlib\backends\backend_agg.py:238: RuntimeWarning: Glyph 53664 missing from current font.
      font.set_text(s, 0.0, flags=flags)
    C:\Users\SMHRD\anaconda3\lib\site-packages\matplotlib\backends\backend_agg.py:238: RuntimeWarning: Glyph 51068 missing from current font.
      font.set_text(s, 0.0, flags=flags)
    C:\Users\SMHRD\anaconda3\lib\site-packages\matplotlib\backends\backend_agg.py:201: RuntimeWarning: Glyph 50900 missing from current font.
      font.set_text(s, 0, flags=flags)
    C:\Users\SMHRD\anaconda3\lib\site-packages\matplotlib\backends\backend_agg.py:201: RuntimeWarning: Glyph 54868 missing from current font.
      font.set_text(s, 0, flags=flags)
    C:\Users\SMHRD\anaconda3\lib\site-packages\matplotlib\backends\backend_agg.py:201: RuntimeWarning: Glyph 49688 missing from current font.
      font.set_text(s, 0, flags=flags)
    C:\Users\SMHRD\anaconda3\lib\site-packages\matplotlib\backends\backend_agg.py:201: RuntimeWarning: Glyph 47785 missing from current font.
      font.set_text(s, 0, flags=flags)
    C:\Users\SMHRD\anaconda3\lib\site-packages\matplotlib\backends\backend_agg.py:201: RuntimeWarning: Glyph 44552 missing from current font.
      font.set_text(s, 0, flags=flags)
    C:\Users\SMHRD\anaconda3\lib\site-packages\matplotlib\backends\backend_agg.py:201: RuntimeWarning: Glyph 53664 missing from current font.
      font.set_text(s, 0, flags=flags)
    C:\Users\SMHRD\anaconda3\lib\site-packages\matplotlib\backends\backend_agg.py:201: RuntimeWarning: Glyph 51068 missing from current font.
      font.set_text(s, 0, flags=flags)
    


    
![png](output_27_1.png)
    


### 한글 지원 폰트 설정


```python
from matplotlib import rc
rc('font', family = 'Malgun Gothic')
```


```python
y= temp[['월','화','수','목','금','토','일']]
x= y.index
plt.ylim(500,620)
plt.bar(x,y)
plt.xlabel('요일')
plt.ylabel('사고 건수')
plt.title('요일별 사망교통수 건수')
plt.show()
```


    
![png](output_30_0.png)
    



```python
data['요일'].value_counts()
```




    화    608
    월    603
    금    603
    토    596
    목    586
    수    565
    일    504
    Name: 요일, dtype: int64




```python
# 요일별 사망자 수
tp=data[['요일','사망자수']].groupby('요일').sum()
```


```python
pd.set_option('display.max_columns',30) #30대신 None : 전부다 보겠다. 컬럼에는 해볼만 한데 '행'에는 하지말것!
```


```python
# 차대차 사건 중 죽거나 다친 사람이 많은 발생지 시도를 알아보고 시각화
# 1. 차대차 사건 중
# 2. (1)죽거나 다친 사람(사상자)이 많은 (2)발생지 시도
# 3. 시각화
acc = data[data['사고유형_대분류'] == '차대차']
```


```python
acc
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
      <th>발생년</th>
      <th>발생년월일시</th>
      <th>발생분</th>
      <th>주야</th>
      <th>요일</th>
      <th>사망자수</th>
      <th>사상자수</th>
      <th>중상자수</th>
      <th>경상자수</th>
      <th>부상신고자수</th>
      <th>발생지시도</th>
      <th>발생지시군구</th>
      <th>사고유형_대분류</th>
      <th>사고유형_중분류</th>
      <th>사고유형</th>
      <th>법규위반_대분류</th>
      <th>법규위반</th>
      <th>도로형태_대분류</th>
      <th>도로형태</th>
      <th>당사자종별_1당_대분류</th>
      <th>당사자종별_1당</th>
      <th>당사자종별_2당_대분류</th>
      <th>당사자종별_2당</th>
      <th>발생위치X_UTMK</th>
      <th>발생위치Y_UTMK</th>
      <th>경도</th>
      <th>위도</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2017</td>
      <td>2017010101</td>
      <td>15</td>
      <td>야간</td>
      <td>일</td>
      <td>1</td>
      <td>2</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>전남</td>
      <td>장성군</td>
      <td>차대차</td>
      <td>기타</td>
      <td>기타</td>
      <td>운전자법규위반</td>
      <td>안전운전 의무 불이행</td>
      <td>단일로</td>
      <td>기타단일로</td>
      <td>승용차</td>
      <td>승용차</td>
      <td>승용차</td>
      <td>승용차</td>
      <td>933501</td>
      <td>1700129</td>
      <td>126.768634</td>
      <td>35.294464</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2017</td>
      <td>2017010102</td>
      <td>43</td>
      <td>야간</td>
      <td>일</td>
      <td>1</td>
      <td>2</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>충남</td>
      <td>홍성군</td>
      <td>차대차</td>
      <td>추돌</td>
      <td>추돌</td>
      <td>운전자법규위반</td>
      <td>안전운전 의무 불이행</td>
      <td>단일로</td>
      <td>기타단일로</td>
      <td>승용차</td>
      <td>승용차</td>
      <td>승용차</td>
      <td>승용차</td>
      <td>916497</td>
      <td>1842880</td>
      <td>126.566631</td>
      <td>36.580069</td>
    </tr>
    <tr>
      <th>8</th>
      <td>2017</td>
      <td>2017010118</td>
      <td>33</td>
      <td>야간</td>
      <td>일</td>
      <td>1</td>
      <td>3</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>제주</td>
      <td>서귀포시</td>
      <td>차대차</td>
      <td>측면충돌</td>
      <td>측면충돌</td>
      <td>운전자법규위반</td>
      <td>안전운전 의무 불이행</td>
      <td>단일로</td>
      <td>기타단일로</td>
      <td>승용차</td>
      <td>승용차</td>
      <td>화물차</td>
      <td>화물차</td>
      <td>922514</td>
      <td>1476665</td>
      <td>126.667913</td>
      <td>33.278582</td>
    </tr>
    <tr>
      <th>9</th>
      <td>2017</td>
      <td>2017010120</td>
      <td>0</td>
      <td>야간</td>
      <td>일</td>
      <td>1</td>
      <td>7</td>
      <td>4</td>
      <td>2</td>
      <td>0</td>
      <td>충남</td>
      <td>공주시</td>
      <td>차대차</td>
      <td>기타</td>
      <td>기타</td>
      <td>운전자법규위반</td>
      <td>안전운전 의무 불이행</td>
      <td>단일로</td>
      <td>기타단일로</td>
      <td>승용차</td>
      <td>승용차</td>
      <td>승용차</td>
      <td>승용차</td>
      <td>962530</td>
      <td>1823895</td>
      <td>127.082074</td>
      <td>36.411838</td>
    </tr>
    <tr>
      <th>17</th>
      <td>2017</td>
      <td>2017010209</td>
      <td>0</td>
      <td>주간</td>
      <td>월</td>
      <td>1</td>
      <td>2</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>경북</td>
      <td>청송군</td>
      <td>차대차</td>
      <td>측면충돌</td>
      <td>측면충돌</td>
      <td>운전자법규위반</td>
      <td>중앙선 침범</td>
      <td>단일로</td>
      <td>기타단일로</td>
      <td>승용차</td>
      <td>승용차</td>
      <td>승용차</td>
      <td>승용차</td>
      <td>1134705</td>
      <td>1810932</td>
      <td>128.999992</td>
      <td>36.286293</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>4050</th>
      <td>2017</td>
      <td>2017123009</td>
      <td>58</td>
      <td>주간</td>
      <td>토</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>경남</td>
      <td>하동군</td>
      <td>차대차</td>
      <td>정면충돌</td>
      <td>정면충돌</td>
      <td>운전자법규위반</td>
      <td>중앙선 침범</td>
      <td>단일로</td>
      <td>기타단일로</td>
      <td>승용차</td>
      <td>승용차</td>
      <td>건설기계</td>
      <td>건설기계</td>
      <td>1030259</td>
      <td>1674021</td>
      <td>127.831844</td>
      <td>35.060801</td>
    </tr>
    <tr>
      <th>4055</th>
      <td>2017</td>
      <td>2017123023</td>
      <td>50</td>
      <td>야간</td>
      <td>토</td>
      <td>1</td>
      <td>6</td>
      <td>2</td>
      <td>3</td>
      <td>0</td>
      <td>광주</td>
      <td>동구</td>
      <td>차대차</td>
      <td>정면충돌</td>
      <td>정면충돌</td>
      <td>운전자법규위반</td>
      <td>중앙선 침범</td>
      <td>단일로</td>
      <td>기타단일로</td>
      <td>승용차</td>
      <td>승용차</td>
      <td>승용차</td>
      <td>승용차</td>
      <td>948703</td>
      <td>1679181</td>
      <td>126.937322</td>
      <td>35.106089</td>
    </tr>
    <tr>
      <th>4058</th>
      <td>2017</td>
      <td>2017123112</td>
      <td>10</td>
      <td>주간</td>
      <td>일</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>경북</td>
      <td>경산시</td>
      <td>차대차</td>
      <td>기타</td>
      <td>기타</td>
      <td>운전자법규위반</td>
      <td>교차로 통행방법 위반</td>
      <td>교차로</td>
      <td>교차로부근</td>
      <td>이륜차</td>
      <td>이륜차</td>
      <td>승합차</td>
      <td>승합차</td>
      <td>1111054</td>
      <td>1758873</td>
      <td>128.729654</td>
      <td>35.820218</td>
    </tr>
    <tr>
      <th>4060</th>
      <td>2017</td>
      <td>2017123118</td>
      <td>10</td>
      <td>야간</td>
      <td>일</td>
      <td>1</td>
      <td>4</td>
      <td>1</td>
      <td>0</td>
      <td>2</td>
      <td>경남</td>
      <td>사천시</td>
      <td>차대차</td>
      <td>추돌</td>
      <td>추돌</td>
      <td>운전자법규위반</td>
      <td>안전운전 의무 불이행</td>
      <td>단일로</td>
      <td>기타단일로</td>
      <td>화물차</td>
      <td>화물차</td>
      <td>화물차</td>
      <td>화물차</td>
      <td>1044531</td>
      <td>1682838</td>
      <td>127.988833</td>
      <td>35.139774</td>
    </tr>
    <tr>
      <th>4063</th>
      <td>2017</td>
      <td>2017123120</td>
      <td>40</td>
      <td>야간</td>
      <td>일</td>
      <td>1</td>
      <td>11</td>
      <td>1</td>
      <td>9</td>
      <td>0</td>
      <td>경기</td>
      <td>동두천시</td>
      <td>차대차</td>
      <td>정면충돌</td>
      <td>정면충돌</td>
      <td>운전자법규위반</td>
      <td>중앙선 침범</td>
      <td>단일로</td>
      <td>기타단일로</td>
      <td>승용차</td>
      <td>승용차</td>
      <td>승용차</td>
      <td>승용차</td>
      <td>961004</td>
      <td>1987481</td>
      <td>127.056525</td>
      <td>37.886331</td>
    </tr>
  </tbody>
</table>
<p>1642 rows × 27 columns</p>
</div>




```python
#(1)죽거나 다친 사람(사상자)이 많은 (2)발생지 시도
acc['발생지시도'].value_counts()
```




    경기    330
    충남    163
    경북    156
    경남    146
    전남    134
    전북    133
    서울    112
    충북     95
    강원     80
    대구     67
    부산     53
    광주     42
    인천     41
    제주     27
    대전     27
    울산     26
    세종     10
    Name: 발생지시도, dtype: int64




```python
acc[['사상자수','발생지시도']]
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
      <th>사상자수</th>
      <th>발생지시도</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2</td>
      <td>전남</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>충남</td>
    </tr>
    <tr>
      <th>8</th>
      <td>3</td>
      <td>제주</td>
    </tr>
    <tr>
      <th>9</th>
      <td>7</td>
      <td>충남</td>
    </tr>
    <tr>
      <th>17</th>
      <td>2</td>
      <td>경북</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>4050</th>
      <td>1</td>
      <td>경남</td>
    </tr>
    <tr>
      <th>4055</th>
      <td>6</td>
      <td>광주</td>
    </tr>
    <tr>
      <th>4058</th>
      <td>1</td>
      <td>경북</td>
    </tr>
    <tr>
      <th>4060</th>
      <td>4</td>
      <td>경남</td>
    </tr>
    <tr>
      <th>4063</th>
      <td>11</td>
      <td>경기</td>
    </tr>
  </tbody>
</table>
<p>1642 rows × 2 columns</p>
</div>




```python
acc.loc[:,['사상자수','발생지시도']]
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
      <th>사상자수</th>
      <th>발생지시도</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2</td>
      <td>전남</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>충남</td>
    </tr>
    <tr>
      <th>8</th>
      <td>3</td>
      <td>제주</td>
    </tr>
    <tr>
      <th>9</th>
      <td>7</td>
      <td>충남</td>
    </tr>
    <tr>
      <th>17</th>
      <td>2</td>
      <td>경북</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>4050</th>
      <td>1</td>
      <td>경남</td>
    </tr>
    <tr>
      <th>4055</th>
      <td>6</td>
      <td>광주</td>
    </tr>
    <tr>
      <th>4058</th>
      <td>1</td>
      <td>경북</td>
    </tr>
    <tr>
      <th>4060</th>
      <td>4</td>
      <td>경남</td>
    </tr>
    <tr>
      <th>4063</th>
      <td>11</td>
      <td>경기</td>
    </tr>
  </tbody>
</table>
<p>1642 rows × 2 columns</p>
</div>




```python
acc_result = acc.loc[:,['사상자수','발생지시도']].groupby('발생지시도').sum()
acc_result
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
      <th>사상자수</th>
    </tr>
    <tr>
      <th>발생지시도</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>강원</th>
      <td>214</td>
    </tr>
    <tr>
      <th>경기</th>
      <td>824</td>
    </tr>
    <tr>
      <th>경남</th>
      <td>248</td>
    </tr>
    <tr>
      <th>경북</th>
      <td>287</td>
    </tr>
    <tr>
      <th>광주</th>
      <td>87</td>
    </tr>
    <tr>
      <th>대구</th>
      <td>115</td>
    </tr>
    <tr>
      <th>대전</th>
      <td>61</td>
    </tr>
    <tr>
      <th>부산</th>
      <td>107</td>
    </tr>
    <tr>
      <th>서울</th>
      <td>197</td>
    </tr>
    <tr>
      <th>세종</th>
      <td>17</td>
    </tr>
    <tr>
      <th>울산</th>
      <td>73</td>
    </tr>
    <tr>
      <th>인천</th>
      <td>66</td>
    </tr>
    <tr>
      <th>전남</th>
      <td>298</td>
    </tr>
    <tr>
      <th>전북</th>
      <td>244</td>
    </tr>
    <tr>
      <th>제주</th>
      <td>50</td>
    </tr>
    <tr>
      <th>충남</th>
      <td>351</td>
    </tr>
    <tr>
      <th>충북</th>
      <td>261</td>
    </tr>
  </tbody>
</table>
</div>




```python
# x,y축으로 사용할 값 저장

x= acc_result.index
y= acc_result['사상자수'].values

```




    array([214, 824, 248, 287,  87, 115,  61, 107, 197,  17,  73,  66, 298,
           244,  50, 351, 261], dtype=int64)




```python
plt.figure(figsize=(20,5))
plt.bar(x,y)
plt.xlabel('지역')
plt.ylabel('사상자수')
plt.title('차vs차 교통사고의 사상자 수')
plt.show()
```


    
![png](output_41_0.png)
    



```python
acc.columns
```




    Index(['발생년', '발생년월일시', '발생분', '주야', '요일', '사망자수', '사상자수', '중상자수', '경상자수',
           '부상신고자수', '발생지시도', '발생지시군구', '사고유형_대분류', '사고유형_중분류', '사고유형', '법규위반_대분류',
           '법규위반', '도로형태_대분류', '도로형태', '당사자종별_1당_대분류', '당사자종별_1당', '당사자종별_2당_대분류',
           '당사자종별_2당', '발생위치X_UTMK', '발생위치Y_UTMK', '경도', '위도'],
          dtype='object')




```python

```


```python

```


```python
x=data['요일'][data['사망자수'] != 0].value_counts().index
y=data['요일'][data['사망자수'] != 0].value_counts().values
plt.figure(figsize=(10,5))
plt.bar(x,y)
plt.xlabel('요일')
plt.ylabel('사망자수')
plt.title('요일별 사망자 수')
plt.show()
```


    
![png](output_45_0.png)
    



```python
data.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 4065 entries, 0 to 4064
    Data columns (total 27 columns):
     #   Column        Non-Null Count  Dtype  
    ---  ------        --------------  -----  
     0   발생년           4065 non-null   int64  
     1   발생년월일시        4065 non-null   int64  
     2   발생분           4065 non-null   int64  
     3   주야            4065 non-null   object 
     4   요일            4065 non-null   object 
     5   사망자수          4065 non-null   int64  
     6   사상자수          4065 non-null   int64  
     7   중상자수          4065 non-null   int64  
     8   경상자수          4065 non-null   int64  
     9   부상신고자수        4065 non-null   int64  
     10  발생지시도         4065 non-null   object 
     11  발생지시군구        4065 non-null   object 
     12  사고유형_대분류      4065 non-null   object 
     13  사고유형_중분류      4065 non-null   object 
     14  사고유형          4065 non-null   object 
     15  법규위반_대분류      4065 non-null   object 
     16  법규위반          4065 non-null   object 
     17  도로형태_대분류      4065 non-null   object 
     18  도로형태          4065 non-null   object 
     19  당사자종별_1당_대분류  4065 non-null   object 
     20  당사자종별_1당      4065 non-null   object 
     21  당사자종별_2당_대분류  4065 non-null   object 
     22  당사자종별_2당      4065 non-null   object 
     23  발생위치X_UTMK    4065 non-null   int64  
     24  발생위치Y_UTMK    4065 non-null   int64  
     25  경도            4065 non-null   float64
     26  위도            4065 non-null   float64
    dtypes: float64(2), int64(10), object(15)
    memory usage: 857.6+ KB
    
