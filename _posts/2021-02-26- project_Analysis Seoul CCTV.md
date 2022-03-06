---
layout: single
title:  Project 01. Analysis Seoul CCTV
categories: Project_zb
---


# 01.Analysis Seoul CCTV

## 1. 데이터 읽기


```python
import pandas as pd
```


```python

CCTV_Seoul = pd.read_csv('01. Seoul_CCTV.csv', encoding='utf-8')
```

read_csv 로 csv 파일을 불러온다.  
경로를 정확하게 지정해야함에 유의하자.  
encoding = 'utf-8'은 한글이 잘 불러와 지지 않을때 사용한다.


```python
CCTV_Seoul.head()
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
      <th>기관명</th>
      <th>소계</th>
      <th>2013년도 이전</th>
      <th>2014년</th>
      <th>2015년</th>
      <th>2016년</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>강남구</td>
      <td>3238</td>
      <td>1292</td>
      <td>430</td>
      <td>584</td>
      <td>932</td>
    </tr>
    <tr>
      <th>1</th>
      <td>강동구</td>
      <td>1010</td>
      <td>379</td>
      <td>99</td>
      <td>155</td>
      <td>377</td>
    </tr>
    <tr>
      <th>2</th>
      <td>강북구</td>
      <td>831</td>
      <td>369</td>
      <td>120</td>
      <td>138</td>
      <td>204</td>
    </tr>
    <tr>
      <th>3</th>
      <td>강서구</td>
      <td>911</td>
      <td>388</td>
      <td>258</td>
      <td>184</td>
      <td>81</td>
    </tr>
    <tr>
      <th>4</th>
      <td>관악구</td>
      <td>2109</td>
      <td>846</td>
      <td>260</td>
      <td>390</td>
      <td>613</td>
    </tr>
  </tbody>
</table>
</div>



head() 는 엑셀 파일중 상단 5개만 꺼내는 함수이다.  
head(3) 이렇게 할 경우 위에서 부터 3개를 꺼낸다.


```python
CCTV_Seoul.tail()
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
      <th>기관명</th>
      <th>소계</th>
      <th>2013년도 이전</th>
      <th>2014년</th>
      <th>2015년</th>
      <th>2016년</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>20</th>
      <td>용산구</td>
      <td>2096</td>
      <td>1368</td>
      <td>218</td>
      <td>112</td>
      <td>398</td>
    </tr>
    <tr>
      <th>21</th>
      <td>은평구</td>
      <td>2108</td>
      <td>1138</td>
      <td>224</td>
      <td>278</td>
      <td>468</td>
    </tr>
    <tr>
      <th>22</th>
      <td>종로구</td>
      <td>1619</td>
      <td>464</td>
      <td>314</td>
      <td>211</td>
      <td>630</td>
    </tr>
    <tr>
      <th>23</th>
      <td>중구</td>
      <td>1023</td>
      <td>413</td>
      <td>190</td>
      <td>72</td>
      <td>348</td>
    </tr>
    <tr>
      <th>24</th>
      <td>중랑구</td>
      <td>916</td>
      <td>509</td>
      <td>121</td>
      <td>177</td>
      <td>109</td>
    </tr>
  </tbody>
</table>
</div>



tail()은 하위 5개를 꺼내는 함수이다.
tail(3) 이렇게 할 경우 마찬가지로 하위 3개를 꺼낸다.


```python
CCTV_Seoul.columns
```




    Index(['기관명', '소계', '2013년도 이전', '2014년', '2015년', '2016년'], dtype='object')



.colums 는 컬럼을 리스트 형태로 반환하는 함수이다.


```python
CCTV_Seoul.columns[0]
```




    '기관명'




```python
CCTV_Seoul.rename(
    columns={
        CCTV_Seoul.columns[0]: '구별'
        }, inplace=True
    )
```

.rename = 파일명을 다시 설정  
첫번째 컬럼을 기관명에서 구별로 다시 설정해 주었다.  
inplace = True 를 해줘야 바뀐게 계속 적용이 된다.


```python
CCTV_Seoul.head()
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
      <th>구별</th>
      <th>소계</th>
      <th>2013년도 이전</th>
      <th>2014년</th>
      <th>2015년</th>
      <th>2016년</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>강남구</td>
      <td>3238</td>
      <td>1292</td>
      <td>430</td>
      <td>584</td>
      <td>932</td>
    </tr>
    <tr>
      <th>1</th>
      <td>강동구</td>
      <td>1010</td>
      <td>379</td>
      <td>99</td>
      <td>155</td>
      <td>377</td>
    </tr>
    <tr>
      <th>2</th>
      <td>강북구</td>
      <td>831</td>
      <td>369</td>
      <td>120</td>
      <td>138</td>
      <td>204</td>
    </tr>
    <tr>
      <th>3</th>
      <td>강서구</td>
      <td>911</td>
      <td>388</td>
      <td>258</td>
      <td>184</td>
      <td>81</td>
    </tr>
    <tr>
      <th>4</th>
      <td>관악구</td>
      <td>2109</td>
      <td>846</td>
      <td>260</td>
      <td>390</td>
      <td>613</td>
    </tr>
  </tbody>
</table>
</div>




```python
pop_Seoul = pd.read_excel(
    '01. Seoul_Population.xls'
)
```

.read_excel 함수를 이용해서 엑셀 파일을 불러온다.


```python
pop_Seoul.head()
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
      <th>기간</th>
      <th>자치구</th>
      <th>세대</th>
      <th>인구</th>
      <th>인구.1</th>
      <th>인구.2</th>
      <th>인구.3</th>
      <th>인구.4</th>
      <th>인구.5</th>
      <th>인구.6</th>
      <th>인구.7</th>
      <th>인구.8</th>
      <th>세대당인구</th>
      <th>65세이상고령자</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>기간</td>
      <td>자치구</td>
      <td>세대</td>
      <td>합계</td>
      <td>합계</td>
      <td>합계</td>
      <td>한국인</td>
      <td>한국인</td>
      <td>한국인</td>
      <td>등록외국인</td>
      <td>등록외국인</td>
      <td>등록외국인</td>
      <td>세대당인구</td>
      <td>65세이상고령자</td>
    </tr>
    <tr>
      <th>1</th>
      <td>기간</td>
      <td>자치구</td>
      <td>세대</td>
      <td>계</td>
      <td>남자</td>
      <td>여자</td>
      <td>계</td>
      <td>남자</td>
      <td>여자</td>
      <td>계</td>
      <td>남자</td>
      <td>여자</td>
      <td>세대당인구</td>
      <td>65세이상고령자</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2017</td>
      <td>합계</td>
      <td>4220082</td>
      <td>10124579</td>
      <td>4957857</td>
      <td>5166722</td>
      <td>9857426</td>
      <td>4830206</td>
      <td>5027220</td>
      <td>267153</td>
      <td>127651</td>
      <td>139502</td>
      <td>2.34</td>
      <td>1365126</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2017</td>
      <td>종로구</td>
      <td>73594</td>
      <td>164257</td>
      <td>80094</td>
      <td>84163</td>
      <td>154770</td>
      <td>75967</td>
      <td>78803</td>
      <td>9487</td>
      <td>4127</td>
      <td>5360</td>
      <td>2.1</td>
      <td>26182</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2017</td>
      <td>중구</td>
      <td>60412</td>
      <td>134593</td>
      <td>66337</td>
      <td>68256</td>
      <td>125709</td>
      <td>62253</td>
      <td>63456</td>
      <td>8884</td>
      <td>4084</td>
      <td>4800</td>
      <td>2.08</td>
      <td>21384</td>
    </tr>
  </tbody>
</table>
</div>




```python
pop_Seoul = pd.read_excel(
    '01. Seoul_Population.xls', header=2, usecols='B,D,G,J,N'
)
```

header=2 헤더중에서 2번째부터 불러 오겠다.  
usecos= 원하는 라인만 쓰겠다.


```python
pop_Seoul.head()
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
      <th>자치구</th>
      <th>계</th>
      <th>계.1</th>
      <th>계.2</th>
      <th>65세이상고령자</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>합계</td>
      <td>10124579</td>
      <td>9857426</td>
      <td>267153</td>
      <td>1365126</td>
    </tr>
    <tr>
      <th>1</th>
      <td>종로구</td>
      <td>164257</td>
      <td>154770</td>
      <td>9487</td>
      <td>26182</td>
    </tr>
    <tr>
      <th>2</th>
      <td>중구</td>
      <td>134593</td>
      <td>125709</td>
      <td>8884</td>
      <td>21384</td>
    </tr>
    <tr>
      <th>3</th>
      <td>용산구</td>
      <td>244444</td>
      <td>229161</td>
      <td>15283</td>
      <td>36882</td>
    </tr>
    <tr>
      <th>4</th>
      <td>성동구</td>
      <td>312711</td>
      <td>304808</td>
      <td>7903</td>
      <td>41273</td>
    </tr>
  </tbody>
</table>
</div>




```python
pop_Seoul.rename(
    columns={
        pop_Seoul.columns[0]: '구별',
        pop_Seoul.columns[1]: '인구수',
        pop_Seoul.columns[2]: '한국인',
        pop_Seoul.columns[3]: '외국인',
        pop_Seoul.columns[4]: '고령자',
    }
)
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
      <th>구별</th>
      <th>인구수</th>
      <th>한국인</th>
      <th>외국인</th>
      <th>고령자</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>합계</td>
      <td>10124579</td>
      <td>9857426</td>
      <td>267153</td>
      <td>1365126</td>
    </tr>
    <tr>
      <th>1</th>
      <td>종로구</td>
      <td>164257</td>
      <td>154770</td>
      <td>9487</td>
      <td>26182</td>
    </tr>
    <tr>
      <th>2</th>
      <td>중구</td>
      <td>134593</td>
      <td>125709</td>
      <td>8884</td>
      <td>21384</td>
    </tr>
    <tr>
      <th>3</th>
      <td>용산구</td>
      <td>244444</td>
      <td>229161</td>
      <td>15283</td>
      <td>36882</td>
    </tr>
    <tr>
      <th>4</th>
      <td>성동구</td>
      <td>312711</td>
      <td>304808</td>
      <td>7903</td>
      <td>41273</td>
    </tr>
    <tr>
      <th>5</th>
      <td>광진구</td>
      <td>372298</td>
      <td>357703</td>
      <td>14595</td>
      <td>43953</td>
    </tr>
    <tr>
      <th>6</th>
      <td>동대문구</td>
      <td>366011</td>
      <td>350647</td>
      <td>15364</td>
      <td>55718</td>
    </tr>
    <tr>
      <th>7</th>
      <td>중랑구</td>
      <td>412780</td>
      <td>408226</td>
      <td>4554</td>
      <td>59262</td>
    </tr>
    <tr>
      <th>8</th>
      <td>성북구</td>
      <td>455407</td>
      <td>444055</td>
      <td>11352</td>
      <td>66251</td>
    </tr>
    <tr>
      <th>9</th>
      <td>강북구</td>
      <td>328002</td>
      <td>324479</td>
      <td>3523</td>
      <td>56530</td>
    </tr>
    <tr>
      <th>10</th>
      <td>도봉구</td>
      <td>346234</td>
      <td>344166</td>
      <td>2068</td>
      <td>53488</td>
    </tr>
    <tr>
      <th>11</th>
      <td>노원구</td>
      <td>558075</td>
      <td>554403</td>
      <td>3672</td>
      <td>74243</td>
    </tr>
    <tr>
      <th>12</th>
      <td>은평구</td>
      <td>491202</td>
      <td>486794</td>
      <td>4408</td>
      <td>74559</td>
    </tr>
    <tr>
      <th>13</th>
      <td>서대문구</td>
      <td>325028</td>
      <td>312800</td>
      <td>12228</td>
      <td>49266</td>
    </tr>
    <tr>
      <th>14</th>
      <td>마포구</td>
      <td>385783</td>
      <td>374915</td>
      <td>10868</td>
      <td>49615</td>
    </tr>
    <tr>
      <th>15</th>
      <td>양천구</td>
      <td>475018</td>
      <td>471154</td>
      <td>3864</td>
      <td>55234</td>
    </tr>
    <tr>
      <th>16</th>
      <td>강서구</td>
      <td>608255</td>
      <td>601691</td>
      <td>6564</td>
      <td>76032</td>
    </tr>
    <tr>
      <th>17</th>
      <td>구로구</td>
      <td>441559</td>
      <td>410742</td>
      <td>30817</td>
      <td>58794</td>
    </tr>
    <tr>
      <th>18</th>
      <td>금천구</td>
      <td>253491</td>
      <td>235154</td>
      <td>18337</td>
      <td>34170</td>
    </tr>
    <tr>
      <th>19</th>
      <td>영등포구</td>
      <td>402024</td>
      <td>368550</td>
      <td>33474</td>
      <td>53981</td>
    </tr>
    <tr>
      <th>20</th>
      <td>동작구</td>
      <td>408493</td>
      <td>396217</td>
      <td>12276</td>
      <td>57255</td>
    </tr>
    <tr>
      <th>21</th>
      <td>관악구</td>
      <td>520929</td>
      <td>503297</td>
      <td>17632</td>
      <td>70046</td>
    </tr>
    <tr>
      <th>22</th>
      <td>서초구</td>
      <td>445401</td>
      <td>441102</td>
      <td>4299</td>
      <td>53205</td>
    </tr>
    <tr>
      <th>23</th>
      <td>강남구</td>
      <td>561052</td>
      <td>556164</td>
      <td>4888</td>
      <td>65060</td>
    </tr>
    <tr>
      <th>24</th>
      <td>송파구</td>
      <td>671173</td>
      <td>664496</td>
      <td>6677</td>
      <td>76582</td>
    </tr>
    <tr>
      <th>25</th>
      <td>강동구</td>
      <td>440359</td>
      <td>436223</td>
      <td>4136</td>
      <td>56161</td>
    </tr>
  </tbody>
</table>
</div>



## pandas 기초
- Python에서 R 만큼의 강력한 데이터 핸들링 성능을 제공하는 모듈
- 단일 프로세스에서는 최대 효율
- 코딩 가능하고 으용 가능한 엑셀로 받아들여도 됨
- 누군가 스테로이드를 맞은 엑셀로 표현함

#### Series
- dex와 value로 이루어져 있습니다.  
- 한 가지 데이터 타입만 가질 수 있습니다.


```python
import pandas as pd
import numpy as np
```

- pandas는 통상 pd
- numpy는 통상 np


```python
pd.Series()
```

    C:\Users\jcc96\AppData\Local\Temp/ipykernel_4552/2031691219.py:1: FutureWarning: The default dtype for empty Series will be 'object' instead of 'float64' in a future version. Specify a dtype explicitly to silence this warning.
      pd.Series()
    




    Series([], dtype: float64)



위와 같이 어떻게 작성해야할지 모를땐 그냥 쳐보면 밑에 오류에서 파악할 수 있다.  
리스트 형태이고, 플롯 값이 들어감을 알 수있다.


```python
pd.Series([1, 2, 3, 4])
```




    0    1
    1    2
    2    3
    3    4
    dtype: int64



int형을 플롯형으로 바꿔줘야 할것 같으므로 진행해본다


```python
pd.Series([1, 2, 3, 4], dtype=float64)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    ~\AppData\Local\Temp/ipykernel_4552/1502664684.py in <module>
    ----> 1 pd.Series([1, 2, 3, 4], dtype=float64)
    

    NameError: name 'float64' is not defined


float64가 정의되있지 않다고 한다.  
해결법을 모르니 구글에 pandas.Series 를 검색하여 가이드를 확인한다


```python
pd.Series([1, 2, 3, 4], dtype=np.float64)
```




    0    1.0
    1    2.0
    2    3.0
    3    4.0
    dtype: float64




```python
pd.Series([1, 2, 3, 4], dtype=str)
```




    0    1
    1    2
    2    3
    3    4
    dtype: object



주피터 pandas에서 object는 파이썬에서 str과 같은 의미이다


```python
pd.Series(np.array([1, 2, 3]))
```




    0    1
    1    2
    2    3
    dtype: int32




```python
pd.Series({'Key': 'Value'})
```




    Key    Value
    dtype: object




```python
data = pd.Series([1, 2, 3, 4, '5'])
data
```




    0    1
    1    2
    2    3
    3    4
    4    5
    dtype: object



대부분이 int지만 출력물은 object 이다.


```python
#짝수를 찾고 싶다.
data%2
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    ~\anaconda3\envs\ds_study\lib\site-packages\pandas\core\ops\array_ops.py in _na_arithmetic_op(left, right, op, is_cmp)
        162     try:
    --> 163         result = func(left, right)
        164     except TypeError:
    

    ~\anaconda3\envs\ds_study\lib\site-packages\pandas\core\computation\expressions.py in evaluate(op, a, b, use_numexpr)
        239             return _evaluate(op, op_str, a, b)  # type: ignore[misc]
    --> 240     return _evaluate_standard(op, op_str, a, b)
        241 
    

    ~\anaconda3\envs\ds_study\lib\site-packages\pandas\core\computation\expressions.py in _evaluate_standard(op, op_str, a, b)
         68         _store_test_result(False)
    ---> 69     return op(a, b)
         70 
    

    TypeError: not all arguments converted during string formatting

    
    During handling of the above exception, another exception occurred:
    

    TypeError                                 Traceback (most recent call last)

    ~\AppData\Local\Temp/ipykernel_4552/831588745.py in <module>
          1 #짝수를 찾고 싶다.
    ----> 2 data%2
    

    ~\anaconda3\envs\ds_study\lib\site-packages\pandas\core\ops\common.py in new_method(self, other)
         68         other = item_from_zerodim(other)
         69 
    ---> 70         return method(self, other)
         71 
         72     return new_method
    

    ~\anaconda3\envs\ds_study\lib\site-packages\pandas\core\arraylike.py in __mod__(self, other)
        138     @unpack_zerodim_and_defer("__mod__")
        139     def __mod__(self, other):
    --> 140         return self._arith_method(other, operator.mod)
        141 
        142     @unpack_zerodim_and_defer("__rmod__")
    

    ~\anaconda3\envs\ds_study\lib\site-packages\pandas\core\series.py in _arith_method(self, other, op)
       5637     def _arith_method(self, other, op):
       5638         self, other = ops.align_method_SERIES(self, other)
    -> 5639         return base.IndexOpsMixin._arith_method(self, other, op)
       5640 
       5641 
    

    ~\anaconda3\envs\ds_study\lib\site-packages\pandas\core\base.py in _arith_method(self, other, op)
       1293 
       1294         with np.errstate(all="ignore"):
    -> 1295             result = ops.arithmetic_op(lvalues, rvalues, op)
       1296 
       1297         return self._construct_result(result, name=res_name)
    

    ~\anaconda3\envs\ds_study\lib\site-packages\pandas\core\ops\array_ops.py in arithmetic_op(left, right, op)
        220         _bool_arith_check(op, left, right)
        221 
    --> 222         res_values = _na_arithmetic_op(left, right, op)
        223 
        224     return res_values
    

    ~\anaconda3\envs\ds_study\lib\site-packages\pandas\core\ops\array_ops.py in _na_arithmetic_op(left, right, op, is_cmp)
        168             # Don't do this for comparisons, as that will handle complex numbers
        169             #  incorrectly, see GH#32047
    --> 170             result = _masked_arith_op(left, right, op)
        171         else:
        172             raise
    

    ~\anaconda3\envs\ds_study\lib\site-packages\pandas\core\ops\array_ops.py in _masked_arith_op(x, y, op)
        125 
        126         if mask.any():
    --> 127             result[mask] = op(xrav[mask], y)
        128 
        129     np.putmask(result, ~mask, np.nan)
    

    TypeError: not all arguments converted during string formatting


not all arguments converted during string formatting 를 읽어보면 str이 문제가 됨을 알 수 있다.

### 날짜 데이터


```python
dates = pd.date_range('20210101', periods=6)
dates
```




    DatetimeIndex(['2021-01-01', '2021-01-02', '2021-01-03', '2021-01-04',
                   '2021-01-05', '2021-01-06'],
                  dtype='datetime64[ns]', freq='D')



### DataFrame
- pd.Series()
    - index, value
- pd.DataFrame()
    - index, value, column


```python
# 표준정규분포에서 샘플링한 난수 생성
data = np.random.randn(6,4)
data
```




    array([[ 0.54961592,  1.42094603, -1.05839241,  0.9109797 ],
           [ 1.22761118,  0.79608411,  0.59279598, -0.20091472],
           [-0.08129009,  0.85022078, -0.41851623, -0.20551821],
           [ 0.14996783,  0.53368343,  0.16853839, -0.99076167],
           [ 2.52669411,  0.89396024, -0.10031101,  0.00913617],
           [ 0.10605774, -0.13516601,  0.37750192, -0.85430128]])




```python
df = pd.DataFrame(data, index=dates, columns=['A', 'B', 'C', 'D'])
df
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-01</th>
      <td>0.549616</td>
      <td>1.420946</td>
      <td>-1.058392</td>
      <td>0.910980</td>
    </tr>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>0.796084</td>
      <td>0.592796</td>
      <td>-0.200915</td>
    </tr>
    <tr>
      <th>2021-01-03</th>
      <td>-0.081290</td>
      <td>0.850221</td>
      <td>-0.418516</td>
      <td>-0.205518</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.149968</td>
      <td>0.533683</td>
      <td>0.168538</td>
      <td>-0.990762</td>
    </tr>
    <tr>
      <th>2021-01-05</th>
      <td>2.526694</td>
      <td>0.893960</td>
      <td>-0.100311</td>
      <td>0.009136</td>
    </tr>
    <tr>
      <th>2021-01-06</th>
      <td>0.106058</td>
      <td>-0.135166</td>
      <td>0.377502</td>
      <td>-0.854301</td>
    </tr>
  </tbody>
</table>
</div>



### 데이터 프레임 정보 탐색

- df.head()


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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-01</th>
      <td>0.549616</td>
      <td>1.420946</td>
      <td>-1.058392</td>
      <td>0.910980</td>
    </tr>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>0.796084</td>
      <td>0.592796</td>
      <td>-0.200915</td>
    </tr>
    <tr>
      <th>2021-01-03</th>
      <td>-0.081290</td>
      <td>0.850221</td>
      <td>-0.418516</td>
      <td>-0.205518</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.149968</td>
      <td>0.533683</td>
      <td>0.168538</td>
      <td>-0.990762</td>
    </tr>
    <tr>
      <th>2021-01-05</th>
      <td>2.526694</td>
      <td>0.893960</td>
      <td>-0.100311</td>
      <td>0.009136</td>
    </tr>
  </tbody>
</table>
</div>



- df.tail


```python
df.tail()
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>0.796084</td>
      <td>0.592796</td>
      <td>-0.200915</td>
    </tr>
    <tr>
      <th>2021-01-03</th>
      <td>-0.081290</td>
      <td>0.850221</td>
      <td>-0.418516</td>
      <td>-0.205518</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.149968</td>
      <td>0.533683</td>
      <td>0.168538</td>
      <td>-0.990762</td>
    </tr>
    <tr>
      <th>2021-01-05</th>
      <td>2.526694</td>
      <td>0.893960</td>
      <td>-0.100311</td>
      <td>0.009136</td>
    </tr>
    <tr>
      <th>2021-01-06</th>
      <td>0.106058</td>
      <td>-0.135166</td>
      <td>0.377502</td>
      <td>-0.854301</td>
    </tr>
  </tbody>
</table>
</div>



- df.index


```python
df.index
```




    DatetimeIndex(['2021-01-01', '2021-01-02', '2021-01-03', '2021-01-04',
                   '2021-01-05', '2021-01-06'],
                  dtype='datetime64[ns]', freq='D')




```python
df.columns
```




    Index(['A', 'B', 'C', 'D'], dtype='object')




```python
df.values
```




    array([[ 0.54961592,  1.42094603, -1.05839241,  0.9109797 ],
           [ 1.22761118,  0.79608411,  0.59279598, -0.20091472],
           [-0.08129009,  0.85022078, -0.41851623, -0.20551821],
           [ 0.14996783,  0.53368343,  0.16853839, -0.99076167],
           [ 2.52669411,  0.89396024, -0.10031101,  0.00913617],
           [ 0.10605774, -0.13516601,  0.37750192, -0.85430128]])



head() / tail() 은 괄호가 붙는데 매소드이 이기 때문이고,  
index / columns / values 는 변수이기 때문에 그냥 쓰는것이다.

- df.info() : 데이터 프레임의 기본 정보 확인


```python
df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    DatetimeIndex: 6 entries, 2021-01-01 to 2021-01-06
    Freq: D
    Data columns (total 4 columns):
     #   Column  Non-Null Count  Dtype  
    ---  ------  --------------  -----  
     0   A       6 non-null      float64
     1   B       6 non-null      float64
     2   C       6 non-null      float64
     3   D       6 non-null      float64
    dtypes: float64(4)
    memory usage: 240.0 bytes
    

- df.describe() : 데이터 프레임의 기술통계 정보 확인


```python
df.describe()
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>6.000000</td>
      <td>6.000000</td>
      <td>6.000000</td>
      <td>6.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>0.746443</td>
      <td>0.726621</td>
      <td>-0.073064</td>
      <td>-0.221897</td>
    </tr>
    <tr>
      <th>std</th>
      <td>0.988997</td>
      <td>0.511878</td>
      <td>0.599283</td>
      <td>0.682434</td>
    </tr>
    <tr>
      <th>min</th>
      <td>-0.081290</td>
      <td>-0.135166</td>
      <td>-1.058392</td>
      <td>-0.990762</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>0.117035</td>
      <td>0.599284</td>
      <td>-0.338965</td>
      <td>-0.692106</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>0.349792</td>
      <td>0.823152</td>
      <td>0.034114</td>
      <td>-0.203216</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>1.058112</td>
      <td>0.883025</td>
      <td>0.325261</td>
      <td>-0.043377</td>
    </tr>
    <tr>
      <th>max</th>
      <td>2.526694</td>
      <td>1.420946</td>
      <td>0.592796</td>
      <td>0.910980</td>
    </tr>
  </tbody>
</table>
</div>



### 데이터 정렬
- sort_values()
- 특정 컬럼(열)을 기준으로 데이터를 정렬합니다.


```python
df
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-01</th>
      <td>0.549616</td>
      <td>1.420946</td>
      <td>-1.058392</td>
      <td>0.910980</td>
    </tr>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>0.796084</td>
      <td>0.592796</td>
      <td>-0.200915</td>
    </tr>
    <tr>
      <th>2021-01-03</th>
      <td>-0.081290</td>
      <td>0.850221</td>
      <td>-0.418516</td>
      <td>-0.205518</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.149968</td>
      <td>0.533683</td>
      <td>0.168538</td>
      <td>-0.990762</td>
    </tr>
    <tr>
      <th>2021-01-05</th>
      <td>2.526694</td>
      <td>0.893960</td>
      <td>-0.100311</td>
      <td>0.009136</td>
    </tr>
    <tr>
      <th>2021-01-06</th>
      <td>0.106058</td>
      <td>-0.135166</td>
      <td>0.377502</td>
      <td>-0.854301</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.sort_values(by='B', ascending=False, inplace=True)
```


```python
df
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-01</th>
      <td>0.549616</td>
      <td>1.420946</td>
      <td>-1.058392</td>
      <td>0.910980</td>
    </tr>
    <tr>
      <th>2021-01-05</th>
      <td>2.526694</td>
      <td>0.893960</td>
      <td>-0.100311</td>
      <td>0.009136</td>
    </tr>
    <tr>
      <th>2021-01-03</th>
      <td>-0.081290</td>
      <td>0.850221</td>
      <td>-0.418516</td>
      <td>-0.205518</td>
    </tr>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>0.796084</td>
      <td>0.592796</td>
      <td>-0.200915</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.149968</td>
      <td>0.533683</td>
      <td>0.168538</td>
      <td>-0.990762</td>
    </tr>
    <tr>
      <th>2021-01-06</th>
      <td>0.106058</td>
      <td>-0.135166</td>
      <td>0.377502</td>
      <td>-0.854301</td>
    </tr>
  </tbody>
</table>
</div>



ascending=False : 내림차순 정렬  
inplace=True : 수정값 저장

### 데이터 선택


```python
df
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-01</th>
      <td>0.549616</td>
      <td>1.420946</td>
      <td>-1.058392</td>
      <td>0.910980</td>
    </tr>
    <tr>
      <th>2021-01-05</th>
      <td>2.526694</td>
      <td>0.893960</td>
      <td>-0.100311</td>
      <td>0.009136</td>
    </tr>
    <tr>
      <th>2021-01-03</th>
      <td>-0.081290</td>
      <td>0.850221</td>
      <td>-0.418516</td>
      <td>-0.205518</td>
    </tr>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>0.796084</td>
      <td>0.592796</td>
      <td>-0.200915</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.149968</td>
      <td>0.533683</td>
      <td>0.168538</td>
      <td>-0.990762</td>
    </tr>
    <tr>
      <th>2021-01-06</th>
      <td>0.106058</td>
      <td>-0.135166</td>
      <td>0.377502</td>
      <td>-0.854301</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 한 개 컬럼 선택
df['A']
```




    2021-01-01    0.549616
    2021-01-05    2.526694
    2021-01-03   -0.081290
    2021-01-02    1.227611
    2021-01-04    0.149968
    2021-01-06    0.106058
    Name: A, dtype: float64




```python
type(df['A'])
```




    pandas.core.series.Series




```python
# 두개이상 컬럼 선택
df[['A', 'B']]
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
      <th>A</th>
      <th>B</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-01</th>
      <td>0.549616</td>
      <td>1.420946</td>
    </tr>
    <tr>
      <th>2021-01-05</th>
      <td>2.526694</td>
      <td>0.893960</td>
    </tr>
    <tr>
      <th>2021-01-03</th>
      <td>-0.081290</td>
      <td>0.850221</td>
    </tr>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>0.796084</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.149968</td>
      <td>0.533683</td>
    </tr>
    <tr>
      <th>2021-01-06</th>
      <td>0.106058</td>
      <td>-0.135166</td>
    </tr>
  </tbody>
</table>
</div>



두개 이상의 경우 리스트에 담아서 해줘야 한다

### offset index
- [n:m] : n부터 m-1 까지
- 인덱스나 컬럼의 이름으로 slice 하는 경우는 끝을 포함합니다.


```python
df
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-01</th>
      <td>0.549616</td>
      <td>1.420946</td>
      <td>-1.058392</td>
      <td>0.910980</td>
    </tr>
    <tr>
      <th>2021-01-05</th>
      <td>2.526694</td>
      <td>0.893960</td>
      <td>-0.100311</td>
      <td>0.009136</td>
    </tr>
    <tr>
      <th>2021-01-03</th>
      <td>-0.081290</td>
      <td>0.850221</td>
      <td>-0.418516</td>
      <td>-0.205518</td>
    </tr>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>0.796084</td>
      <td>0.592796</td>
      <td>-0.200915</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.149968</td>
      <td>0.533683</td>
      <td>0.168538</td>
      <td>-0.990762</td>
    </tr>
    <tr>
      <th>2021-01-06</th>
      <td>0.106058</td>
      <td>-0.135166</td>
      <td>0.377502</td>
      <td>-0.854301</td>
    </tr>
  </tbody>
</table>
</div>




```python
df[0:3]
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-01</th>
      <td>0.549616</td>
      <td>1.420946</td>
      <td>-1.058392</td>
      <td>0.910980</td>
    </tr>
    <tr>
      <th>2021-01-05</th>
      <td>2.526694</td>
      <td>0.893960</td>
      <td>-0.100311</td>
      <td>0.009136</td>
    </tr>
    <tr>
      <th>2021-01-03</th>
      <td>-0.081290</td>
      <td>0.850221</td>
      <td>-0.418516</td>
      <td>-0.205518</td>
    </tr>
  </tbody>
</table>
</div>




```python
df['20210101':'20210104']
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-01</th>
      <td>0.549616</td>
      <td>1.420946</td>
      <td>-1.058392</td>
      <td>0.910980</td>
    </tr>
    <tr>
      <th>2021-01-03</th>
      <td>-0.081290</td>
      <td>0.850221</td>
      <td>-0.418516</td>
      <td>-0.205518</td>
    </tr>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>0.796084</td>
      <td>0.592796</td>
      <td>-0.200915</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.149968</td>
      <td>0.533683</td>
      <td>0.168538</td>
      <td>-0.990762</td>
    </tr>
  </tbody>
</table>
</div>



- loc : location
- index 이름으로 특정 행, 열을 선택합니다.


```python
df
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-01</th>
      <td>0.549616</td>
      <td>1.420946</td>
      <td>-1.058392</td>
      <td>0.910980</td>
    </tr>
    <tr>
      <th>2021-01-05</th>
      <td>2.526694</td>
      <td>0.893960</td>
      <td>-0.100311</td>
      <td>0.009136</td>
    </tr>
    <tr>
      <th>2021-01-03</th>
      <td>-0.081290</td>
      <td>0.850221</td>
      <td>-0.418516</td>
      <td>-0.205518</td>
    </tr>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>0.796084</td>
      <td>0.592796</td>
      <td>-0.200915</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.149968</td>
      <td>0.533683</td>
      <td>0.168538</td>
      <td>-0.990762</td>
    </tr>
    <tr>
      <th>2021-01-06</th>
      <td>0.106058</td>
      <td>-0.135166</td>
      <td>0.377502</td>
      <td>-0.854301</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.loc[:, ['A', 'B']]
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
      <th>A</th>
      <th>B</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-01</th>
      <td>0.549616</td>
      <td>1.420946</td>
    </tr>
    <tr>
      <th>2021-01-05</th>
      <td>2.526694</td>
      <td>0.893960</td>
    </tr>
    <tr>
      <th>2021-01-03</th>
      <td>-0.081290</td>
      <td>0.850221</td>
    </tr>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>0.796084</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.149968</td>
      <td>0.533683</td>
    </tr>
    <tr>
      <th>2021-01-06</th>
      <td>0.106058</td>
      <td>-0.135166</td>
    </tr>
  </tbody>
</table>
</div>



: 이거는 앞에 인덱스는 전부 가져오라는 것이다.  
['A', 'B'] 대괄호 안에 의미는 A, B 만 컬럼으로 가져와라 이다.


```python
df.loc['20210102':'20210104', ['A','D']]
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
      <th>A</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-03</th>
      <td>-0.081290</td>
      <td>-0.205518</td>
    </tr>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>-0.200915</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.149968</td>
      <td>-0.990762</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.loc['20210102':'20210104', 'A':'D']
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-03</th>
      <td>-0.081290</td>
      <td>0.850221</td>
      <td>-0.418516</td>
      <td>-0.205518</td>
    </tr>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>0.796084</td>
      <td>0.592796</td>
      <td>-0.200915</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.149968</td>
      <td>0.533683</td>
      <td>0.168538</td>
      <td>-0.990762</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.loc['20210102', ['A','B']]
```




    A    1.227611
    B    0.796084
    Name: 2021-01-02 00:00:00, dtype: float64



- iloc : inter location  
    - 컴퓨터가 인식하는 인덱스 값으로 선택 


```python
df
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-01</th>
      <td>0.549616</td>
      <td>1.420946</td>
      <td>-1.058392</td>
      <td>0.910980</td>
    </tr>
    <tr>
      <th>2021-01-05</th>
      <td>2.526694</td>
      <td>0.893960</td>
      <td>-0.100311</td>
      <td>0.009136</td>
    </tr>
    <tr>
      <th>2021-01-03</th>
      <td>-0.081290</td>
      <td>0.850221</td>
      <td>-0.418516</td>
      <td>-0.205518</td>
    </tr>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>0.796084</td>
      <td>0.592796</td>
      <td>-0.200915</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.149968</td>
      <td>0.533683</td>
      <td>0.168538</td>
      <td>-0.990762</td>
    </tr>
    <tr>
      <th>2021-01-06</th>
      <td>0.106058</td>
      <td>-0.135166</td>
      <td>0.377502</td>
      <td>-0.854301</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.iloc[3]
```




    A    1.227611
    B    0.796084
    C    0.592796
    D   -0.200915
    Name: 2021-01-02 00:00:00, dtype: float64




```python
df.iloc[3,2]
```




    0.592795984077853




```python
df.iloc[3:5, 0:2]
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
      <th>A</th>
      <th>B</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>0.796084</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.149968</td>
      <td>0.533683</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.iloc[[1,2, 4], [0,2]]
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
      <th>A</th>
      <th>C</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-05</th>
      <td>2.526694</td>
      <td>-0.100311</td>
    </tr>
    <tr>
      <th>2021-01-03</th>
      <td>-0.081290</td>
      <td>-0.418516</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.149968</td>
      <td>0.168538</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.iloc[:, 1:3]
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
      <th>B</th>
      <th>C</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-01</th>
      <td>1.420946</td>
      <td>-1.058392</td>
    </tr>
    <tr>
      <th>2021-01-05</th>
      <td>0.893960</td>
      <td>-0.100311</td>
    </tr>
    <tr>
      <th>2021-01-03</th>
      <td>0.850221</td>
      <td>-0.418516</td>
    </tr>
    <tr>
      <th>2021-01-02</th>
      <td>0.796084</td>
      <td>0.592796</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.533683</td>
      <td>0.168538</td>
    </tr>
    <tr>
      <th>2021-01-06</th>
      <td>-0.135166</td>
      <td>0.377502</td>
    </tr>
  </tbody>
</table>
</div>



### condition


```python
df
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-01</th>
      <td>0.549616</td>
      <td>1.420946</td>
      <td>-1.058392</td>
      <td>0.910980</td>
    </tr>
    <tr>
      <th>2021-01-05</th>
      <td>2.526694</td>
      <td>0.893960</td>
      <td>-0.100311</td>
      <td>0.009136</td>
    </tr>
    <tr>
      <th>2021-01-03</th>
      <td>-0.081290</td>
      <td>0.850221</td>
      <td>-0.418516</td>
      <td>-0.205518</td>
    </tr>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>0.796084</td>
      <td>0.592796</td>
      <td>-0.200915</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.149968</td>
      <td>0.533683</td>
      <td>0.168538</td>
      <td>-0.990762</td>
    </tr>
    <tr>
      <th>2021-01-06</th>
      <td>0.106058</td>
      <td>-0.135166</td>
      <td>0.377502</td>
      <td>-0.854301</td>
    </tr>
  </tbody>
</table>
</div>




```python
# A 컬럼에서 0보다 큰 숫자(양수)만 선택

df['A'] > 0
```




    2021-01-01     True
    2021-01-05     True
    2021-01-03    False
    2021-01-02     True
    2021-01-04     True
    2021-01-06     True
    Name: A, dtype: bool




```python
df[df['A'] > 0]
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-01</th>
      <td>0.549616</td>
      <td>1.420946</td>
      <td>-1.058392</td>
      <td>0.910980</td>
    </tr>
    <tr>
      <th>2021-01-05</th>
      <td>2.526694</td>
      <td>0.893960</td>
      <td>-0.100311</td>
      <td>0.009136</td>
    </tr>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>0.796084</td>
      <td>0.592796</td>
      <td>-0.200915</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.149968</td>
      <td>0.533683</td>
      <td>0.168538</td>
      <td>-0.990762</td>
    </tr>
    <tr>
      <th>2021-01-06</th>
      <td>0.106058</td>
      <td>-0.135166</td>
      <td>0.377502</td>
      <td>-0.854301</td>
    </tr>
  </tbody>
</table>
</div>




```python
df[df > 0]
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-01</th>
      <td>0.549616</td>
      <td>1.420946</td>
      <td>NaN</td>
      <td>0.910980</td>
    </tr>
    <tr>
      <th>2021-01-05</th>
      <td>2.526694</td>
      <td>0.893960</td>
      <td>NaN</td>
      <td>0.009136</td>
    </tr>
    <tr>
      <th>2021-01-03</th>
      <td>NaN</td>
      <td>0.850221</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>0.796084</td>
      <td>0.592796</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.149968</td>
      <td>0.533683</td>
      <td>0.168538</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2021-01-06</th>
      <td>0.106058</td>
      <td>NaN</td>
      <td>0.377502</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



- NaN : Not a Number

### 컬럼추가
- 기존 컬럼이 없으면 추가
- 기존 컬럼이 있으면 수정


```python
df
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-01</th>
      <td>0.549616</td>
      <td>1.420946</td>
      <td>-1.058392</td>
      <td>0.910980</td>
    </tr>
    <tr>
      <th>2021-01-05</th>
      <td>2.526694</td>
      <td>0.893960</td>
      <td>-0.100311</td>
      <td>0.009136</td>
    </tr>
    <tr>
      <th>2021-01-03</th>
      <td>-0.081290</td>
      <td>0.850221</td>
      <td>-0.418516</td>
      <td>-0.205518</td>
    </tr>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>0.796084</td>
      <td>0.592796</td>
      <td>-0.200915</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.149968</td>
      <td>0.533683</td>
      <td>0.168538</td>
      <td>-0.990762</td>
    </tr>
    <tr>
      <th>2021-01-06</th>
      <td>0.106058</td>
      <td>-0.135166</td>
      <td>0.377502</td>
      <td>-0.854301</td>
    </tr>
  </tbody>
</table>
</div>




```python
df['E'] = ['one', 'one', 'two', 'three', 'four', 'five']
```


```python
df
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
      <th>E</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-01</th>
      <td>0.549616</td>
      <td>1.420946</td>
      <td>-1.058392</td>
      <td>0.910980</td>
      <td>one</td>
    </tr>
    <tr>
      <th>2021-01-05</th>
      <td>2.526694</td>
      <td>0.893960</td>
      <td>-0.100311</td>
      <td>0.009136</td>
      <td>one</td>
    </tr>
    <tr>
      <th>2021-01-03</th>
      <td>-0.081290</td>
      <td>0.850221</td>
      <td>-0.418516</td>
      <td>-0.205518</td>
      <td>two</td>
    </tr>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>0.796084</td>
      <td>0.592796</td>
      <td>-0.200915</td>
      <td>tree</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.149968</td>
      <td>0.533683</td>
      <td>0.168538</td>
      <td>-0.990762</td>
      <td>four</td>
    </tr>
    <tr>
      <th>2021-01-06</th>
      <td>0.106058</td>
      <td>-0.135166</td>
      <td>0.377502</td>
      <td>-0.854301</td>
      <td>five</td>
    </tr>
  </tbody>
</table>
</div>



- isin()
- 특정 요소가 있는지 확인


```python
df['E'].isin(['two'])
```




    2021-01-01    False
    2021-01-05    False
    2021-01-03     True
    2021-01-02    False
    2021-01-04    False
    2021-01-06    False
    Name: E, dtype: bool




```python
df['E'].isin(['two', 'five'])
```




    2021-01-01    False
    2021-01-05    False
    2021-01-03     True
    2021-01-02    False
    2021-01-04    False
    2021-01-06     True
    Name: E, dtype: bool




```python
df[df['E'].isin(['two', 'five', 'three'])]
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
      <th>E</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-03</th>
      <td>-0.081290</td>
      <td>0.850221</td>
      <td>-0.418516</td>
      <td>-0.205518</td>
      <td>two</td>
    </tr>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>0.796084</td>
      <td>0.592796</td>
      <td>-0.200915</td>
      <td>three</td>
    </tr>
    <tr>
      <th>2021-01-06</th>
      <td>0.106058</td>
      <td>-0.135166</td>
      <td>0.377502</td>
      <td>-0.854301</td>
      <td>five</td>
    </tr>
  </tbody>
</table>
</div>



### 특정 컬럼 제거
- del
- drop


```python
df
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
      <th>E</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-01</th>
      <td>0.549616</td>
      <td>1.420946</td>
      <td>-1.058392</td>
      <td>0.910980</td>
      <td>one</td>
    </tr>
    <tr>
      <th>2021-01-05</th>
      <td>2.526694</td>
      <td>0.893960</td>
      <td>-0.100311</td>
      <td>0.009136</td>
      <td>one</td>
    </tr>
    <tr>
      <th>2021-01-03</th>
      <td>-0.081290</td>
      <td>0.850221</td>
      <td>-0.418516</td>
      <td>-0.205518</td>
      <td>two</td>
    </tr>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>0.796084</td>
      <td>0.592796</td>
      <td>-0.200915</td>
      <td>three</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.149968</td>
      <td>0.533683</td>
      <td>0.168538</td>
      <td>-0.990762</td>
      <td>four</td>
    </tr>
    <tr>
      <th>2021-01-06</th>
      <td>0.106058</td>
      <td>-0.135166</td>
      <td>0.377502</td>
      <td>-0.854301</td>
      <td>five</td>
    </tr>
  </tbody>
</table>
</div>




```python
del df['E']
df
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-01</th>
      <td>0.549616</td>
      <td>1.420946</td>
      <td>-1.058392</td>
      <td>0.910980</td>
    </tr>
    <tr>
      <th>2021-01-05</th>
      <td>2.526694</td>
      <td>0.893960</td>
      <td>-0.100311</td>
      <td>0.009136</td>
    </tr>
    <tr>
      <th>2021-01-03</th>
      <td>-0.081290</td>
      <td>0.850221</td>
      <td>-0.418516</td>
      <td>-0.205518</td>
    </tr>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>0.796084</td>
      <td>0.592796</td>
      <td>-0.200915</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.149968</td>
      <td>0.533683</td>
      <td>0.168538</td>
      <td>-0.990762</td>
    </tr>
    <tr>
      <th>2021-01-06</th>
      <td>0.106058</td>
      <td>-0.135166</td>
      <td>0.377502</td>
      <td>-0.854301</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.drop(['D'], axis=1) # axis = 0 가로, asix = 1 세로
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-01</th>
      <td>0.549616</td>
      <td>1.420946</td>
      <td>-1.058392</td>
    </tr>
    <tr>
      <th>2021-01-05</th>
      <td>2.526694</td>
      <td>0.893960</td>
      <td>-0.100311</td>
    </tr>
    <tr>
      <th>2021-01-03</th>
      <td>-0.081290</td>
      <td>0.850221</td>
      <td>-0.418516</td>
    </tr>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>0.796084</td>
      <td>0.592796</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.149968</td>
      <td>0.533683</td>
      <td>0.168538</td>
    </tr>
    <tr>
      <th>2021-01-06</th>
      <td>0.106058</td>
      <td>-0.135166</td>
      <td>0.377502</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.drop(['20210104'])
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-01</th>
      <td>0.549616</td>
      <td>1.420946</td>
      <td>-1.058392</td>
      <td>0.910980</td>
    </tr>
    <tr>
      <th>2021-01-05</th>
      <td>2.526694</td>
      <td>0.893960</td>
      <td>-0.100311</td>
      <td>0.009136</td>
    </tr>
    <tr>
      <th>2021-01-03</th>
      <td>-0.081290</td>
      <td>0.850221</td>
      <td>-0.418516</td>
      <td>-0.205518</td>
    </tr>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>0.796084</td>
      <td>0.592796</td>
      <td>-0.200915</td>
    </tr>
    <tr>
      <th>2021-01-06</th>
      <td>0.106058</td>
      <td>-0.135166</td>
      <td>0.377502</td>
      <td>-0.854301</td>
    </tr>
  </tbody>
</table>
</div>



### apply()


```python
df
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-01</th>
      <td>0.549616</td>
      <td>1.420946</td>
      <td>-1.058392</td>
      <td>0.910980</td>
    </tr>
    <tr>
      <th>2021-01-05</th>
      <td>2.526694</td>
      <td>0.893960</td>
      <td>-0.100311</td>
      <td>0.009136</td>
    </tr>
    <tr>
      <th>2021-01-03</th>
      <td>-0.081290</td>
      <td>0.850221</td>
      <td>-0.418516</td>
      <td>-0.205518</td>
    </tr>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>0.796084</td>
      <td>0.592796</td>
      <td>-0.200915</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.149968</td>
      <td>0.533683</td>
      <td>0.168538</td>
      <td>-0.990762</td>
    </tr>
    <tr>
      <th>2021-01-06</th>
      <td>0.106058</td>
      <td>-0.135166</td>
      <td>0.377502</td>
      <td>-0.854301</td>
    </tr>
  </tbody>
</table>
</div>




```python
df['A'].apply('sum')
```




    4.478656676266542




```python
df['A'].apply('mean')
```




    0.746442779377757




```python
df['A'].apply('min'), df['A'].apply('max')
```




    (-0.08129008930424873, 2.5266941068572555)




```python
df[['A', 'B']].apply('sum')
```




    A    4.478657
    B    4.359729
    dtype: float64




```python
df['A'].apply(np.sum)
```




    2021-01-01    0.549616
    2021-01-05    2.526694
    2021-01-03   -0.081290
    2021-01-02    1.227611
    2021-01-04    0.149968
    2021-01-06    0.106058
    Name: A, dtype: float64




```python
df['A'].apply(np.mean)
```




    2021-01-01    0.549616
    2021-01-05    2.526694
    2021-01-03   -0.081290
    2021-01-02    1.227611
    2021-01-04    0.149968
    2021-01-06    0.106058
    Name: A, dtype: float64




```python
df
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2021-01-01</th>
      <td>0.549616</td>
      <td>1.420946</td>
      <td>-1.058392</td>
      <td>0.910980</td>
    </tr>
    <tr>
      <th>2021-01-05</th>
      <td>2.526694</td>
      <td>0.893960</td>
      <td>-0.100311</td>
      <td>0.009136</td>
    </tr>
    <tr>
      <th>2021-01-03</th>
      <td>-0.081290</td>
      <td>0.850221</td>
      <td>-0.418516</td>
      <td>-0.205518</td>
    </tr>
    <tr>
      <th>2021-01-02</th>
      <td>1.227611</td>
      <td>0.796084</td>
      <td>0.592796</td>
      <td>-0.200915</td>
    </tr>
    <tr>
      <th>2021-01-04</th>
      <td>0.149968</td>
      <td>0.533683</td>
      <td>0.168538</td>
      <td>-0.990762</td>
    </tr>
    <tr>
      <th>2021-01-06</th>
      <td>0.106058</td>
      <td>-0.135166</td>
      <td>0.377502</td>
      <td>-0.854301</td>
    </tr>
  </tbody>
</table>
</div>




```python
def plusminus(num):
    return 'Plus' if num > 0 else 'minus'
    
```


```python
df['A'].apply(plusminus)
```




    2021-01-01     Plus
    2021-01-05     Plus
    2021-01-03    minus
    2021-01-02     Plus
    2021-01-04     Plus
    2021-01-06     Plus
    Name: A, dtype: object




```python
df['A'].apply(lambda num: 'plus' if num > 0 else 'minus')
```




    2021-01-01     plus
    2021-01-05     plus
    2021-01-03    minus
    2021-01-02     plus
    2021-01-04     plus
    2021-01-06     plus
    Name: A, dtype: object



---

## 2.cctv 데이터 훑어보기


```python
CCTV_Seoul.head()
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
      <th>구별</th>
      <th>소계</th>
      <th>2013년도 이전</th>
      <th>2014년</th>
      <th>2015년</th>
      <th>2016년</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>강남구</td>
      <td>3238</td>
      <td>1292</td>
      <td>430</td>
      <td>584</td>
      <td>932</td>
    </tr>
    <tr>
      <th>1</th>
      <td>강동구</td>
      <td>1010</td>
      <td>379</td>
      <td>99</td>
      <td>155</td>
      <td>377</td>
    </tr>
    <tr>
      <th>2</th>
      <td>강북구</td>
      <td>831</td>
      <td>369</td>
      <td>120</td>
      <td>138</td>
      <td>204</td>
    </tr>
    <tr>
      <th>3</th>
      <td>강서구</td>
      <td>911</td>
      <td>388</td>
      <td>258</td>
      <td>184</td>
      <td>81</td>
    </tr>
    <tr>
      <th>4</th>
      <td>관악구</td>
      <td>2109</td>
      <td>846</td>
      <td>260</td>
      <td>390</td>
      <td>613</td>
    </tr>
  </tbody>
</table>
</div>




```python
CCTV_Seoul.tail()
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
      <th>구별</th>
      <th>소계</th>
      <th>2013년도 이전</th>
      <th>2014년</th>
      <th>2015년</th>
      <th>2016년</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>20</th>
      <td>용산구</td>
      <td>2096</td>
      <td>1368</td>
      <td>218</td>
      <td>112</td>
      <td>398</td>
    </tr>
    <tr>
      <th>21</th>
      <td>은평구</td>
      <td>2108</td>
      <td>1138</td>
      <td>224</td>
      <td>278</td>
      <td>468</td>
    </tr>
    <tr>
      <th>22</th>
      <td>종로구</td>
      <td>1619</td>
      <td>464</td>
      <td>314</td>
      <td>211</td>
      <td>630</td>
    </tr>
    <tr>
      <th>23</th>
      <td>중구</td>
      <td>1023</td>
      <td>413</td>
      <td>190</td>
      <td>72</td>
      <td>348</td>
    </tr>
    <tr>
      <th>24</th>
      <td>중랑구</td>
      <td>916</td>
      <td>509</td>
      <td>121</td>
      <td>177</td>
      <td>109</td>
    </tr>
  </tbody>
</table>
</div>




```python
CCTV_Seoul.sort_values(by='소계',ascending=True).head(5)
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
      <th>구별</th>
      <th>소계</th>
      <th>2013년도 이전</th>
      <th>2014년</th>
      <th>2015년</th>
      <th>2016년</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>9</th>
      <td>도봉구</td>
      <td>825</td>
      <td>238</td>
      <td>159</td>
      <td>42</td>
      <td>386</td>
    </tr>
    <tr>
      <th>2</th>
      <td>강북구</td>
      <td>831</td>
      <td>369</td>
      <td>120</td>
      <td>138</td>
      <td>204</td>
    </tr>
    <tr>
      <th>5</th>
      <td>광진구</td>
      <td>878</td>
      <td>573</td>
      <td>78</td>
      <td>53</td>
      <td>174</td>
    </tr>
    <tr>
      <th>3</th>
      <td>강서구</td>
      <td>911</td>
      <td>388</td>
      <td>258</td>
      <td>184</td>
      <td>81</td>
    </tr>
    <tr>
      <th>24</th>
      <td>중랑구</td>
      <td>916</td>
      <td>509</td>
      <td>121</td>
      <td>177</td>
      <td>109</td>
    </tr>
  </tbody>
</table>
</div>




```python
CCTV_Seoul.sort_values(by='소계',ascending=False).head(5)
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
      <th>구별</th>
      <th>소계</th>
      <th>2013년도 이전</th>
      <th>2014년</th>
      <th>2015년</th>
      <th>2016년</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>강남구</td>
      <td>3238</td>
      <td>1292</td>
      <td>430</td>
      <td>584</td>
      <td>932</td>
    </tr>
    <tr>
      <th>18</th>
      <td>양천구</td>
      <td>2482</td>
      <td>1843</td>
      <td>142</td>
      <td>30</td>
      <td>467</td>
    </tr>
    <tr>
      <th>14</th>
      <td>서초구</td>
      <td>2297</td>
      <td>1406</td>
      <td>157</td>
      <td>336</td>
      <td>398</td>
    </tr>
    <tr>
      <th>4</th>
      <td>관악구</td>
      <td>2109</td>
      <td>846</td>
      <td>260</td>
      <td>390</td>
      <td>613</td>
    </tr>
    <tr>
      <th>21</th>
      <td>은평구</td>
      <td>2108</td>
      <td>1138</td>
      <td>224</td>
      <td>278</td>
      <td>468</td>
    </tr>
  </tbody>
</table>
</div>




```python
CCTV_Seoul['최근증가율'] = (
    (CCTV_Seoul['2016년'] + CCTV_Seoul['2015년'] + CCTV_Seoul['2014년']) / CCTV_Seoul['2013년도 이전'] *100
)
CCTV_Seoul.sort_values(by='최근증가율', ascending=False).head(5)
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
      <th>구별</th>
      <th>소계</th>
      <th>2013년도 이전</th>
      <th>2014년</th>
      <th>2015년</th>
      <th>2016년</th>
      <th>최근증가율</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>22</th>
      <td>종로구</td>
      <td>1619</td>
      <td>464</td>
      <td>314</td>
      <td>211</td>
      <td>630</td>
      <td>248.922414</td>
    </tr>
    <tr>
      <th>9</th>
      <td>도봉구</td>
      <td>825</td>
      <td>238</td>
      <td>159</td>
      <td>42</td>
      <td>386</td>
      <td>246.638655</td>
    </tr>
    <tr>
      <th>12</th>
      <td>마포구</td>
      <td>980</td>
      <td>314</td>
      <td>118</td>
      <td>169</td>
      <td>379</td>
      <td>212.101911</td>
    </tr>
    <tr>
      <th>8</th>
      <td>노원구</td>
      <td>1566</td>
      <td>542</td>
      <td>57</td>
      <td>451</td>
      <td>516</td>
      <td>188.929889</td>
    </tr>
    <tr>
      <th>1</th>
      <td>강동구</td>
      <td>1010</td>
      <td>379</td>
      <td>99</td>
      <td>155</td>
      <td>377</td>
      <td>166.490765</td>
    </tr>
  </tbody>
</table>
</div>



## 3.인구현황 데이터 훑어보기


```python
pop_Seoul.head()
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
      <th>자치구</th>
      <th>계</th>
      <th>계.1</th>
      <th>계.2</th>
      <th>65세이상고령자</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>종로구</td>
      <td>164257</td>
      <td>154770</td>
      <td>9487</td>
      <td>26182</td>
    </tr>
    <tr>
      <th>2</th>
      <td>중구</td>
      <td>134593</td>
      <td>125709</td>
      <td>8884</td>
      <td>21384</td>
    </tr>
    <tr>
      <th>3</th>
      <td>용산구</td>
      <td>244444</td>
      <td>229161</td>
      <td>15283</td>
      <td>36882</td>
    </tr>
    <tr>
      <th>4</th>
      <td>성동구</td>
      <td>312711</td>
      <td>304808</td>
      <td>7903</td>
      <td>41273</td>
    </tr>
    <tr>
      <th>5</th>
      <td>광진구</td>
      <td>372298</td>
      <td>357703</td>
      <td>14595</td>
      <td>43953</td>
    </tr>
  </tbody>
</table>
</div>




```python
pop_Seoul.tail()
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
      <th>자치구</th>
      <th>계</th>
      <th>계.1</th>
      <th>계.2</th>
      <th>65세이상고령자</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>21</th>
      <td>관악구</td>
      <td>520929</td>
      <td>503297</td>
      <td>17632</td>
      <td>70046</td>
    </tr>
    <tr>
      <th>22</th>
      <td>서초구</td>
      <td>445401</td>
      <td>441102</td>
      <td>4299</td>
      <td>53205</td>
    </tr>
    <tr>
      <th>23</th>
      <td>강남구</td>
      <td>561052</td>
      <td>556164</td>
      <td>4888</td>
      <td>65060</td>
    </tr>
    <tr>
      <th>24</th>
      <td>송파구</td>
      <td>671173</td>
      <td>664496</td>
      <td>6677</td>
      <td>76582</td>
    </tr>
    <tr>
      <th>25</th>
      <td>강동구</td>
      <td>440359</td>
      <td>436223</td>
      <td>4136</td>
      <td>56161</td>
    </tr>
  </tbody>
</table>
</div>




```python
pop_Seoul.drop([1], axis=0, inplace=True)
pop_Seoul.head()
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
      <th>자치구</th>
      <th>계</th>
      <th>계.1</th>
      <th>계.2</th>
      <th>65세이상고령자</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2</th>
      <td>중구</td>
      <td>134593</td>
      <td>125709</td>
      <td>8884</td>
      <td>21384</td>
    </tr>
    <tr>
      <th>3</th>
      <td>용산구</td>
      <td>244444</td>
      <td>229161</td>
      <td>15283</td>
      <td>36882</td>
    </tr>
    <tr>
      <th>4</th>
      <td>성동구</td>
      <td>312711</td>
      <td>304808</td>
      <td>7903</td>
      <td>41273</td>
    </tr>
    <tr>
      <th>5</th>
      <td>광진구</td>
      <td>372298</td>
      <td>357703</td>
      <td>14595</td>
      <td>43953</td>
    </tr>
    <tr>
      <th>6</th>
      <td>동대문구</td>
      <td>366011</td>
      <td>350647</td>
      <td>15364</td>
      <td>55718</td>
    </tr>
  </tbody>
</table>
</div>




```python
pop_Seoul['자치구'].unique()
```




    array(['중구', '용산구', '성동구', '광진구', '동대문구', '중랑구', '성북구', '강북구', '도봉구',
           '노원구', '은평구', '서대문구', '마포구', '양천구', '강서구', '구로구', '금천구', '영등포구',
           '동작구', '관악구', '서초구', '강남구', '송파구', '강동구'], dtype=object)




```python
len(pop_Seoul['자치구'].unique())
```




    24




```python
# 외국인 비율, 고령자 비율

pop_Seoul['외국인비율'] = pop_Seoul['외국인'] / pop_Seoul['인구수'] *100
pop_Seoul['고령자비율'] = pop_Seoul['고령자'] / pop_Seoul['인구수'] *100
pop_Seoul.head()
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
      <th>구별</th>
      <th>인구수</th>
      <th>한국인</th>
      <th>외국인</th>
      <th>고령자</th>
      <th>외국인비율</th>
      <th>고령자비율</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2</th>
      <td>중구</td>
      <td>134593</td>
      <td>125709</td>
      <td>8884</td>
      <td>21384</td>
      <td>6.600640</td>
      <td>15.887899</td>
    </tr>
    <tr>
      <th>3</th>
      <td>용산구</td>
      <td>244444</td>
      <td>229161</td>
      <td>15283</td>
      <td>36882</td>
      <td>6.252148</td>
      <td>15.088118</td>
    </tr>
    <tr>
      <th>4</th>
      <td>성동구</td>
      <td>312711</td>
      <td>304808</td>
      <td>7903</td>
      <td>41273</td>
      <td>2.527254</td>
      <td>13.198448</td>
    </tr>
    <tr>
      <th>5</th>
      <td>광진구</td>
      <td>372298</td>
      <td>357703</td>
      <td>14595</td>
      <td>43953</td>
      <td>3.920247</td>
      <td>11.805865</td>
    </tr>
    <tr>
      <th>6</th>
      <td>동대문구</td>
      <td>366011</td>
      <td>350647</td>
      <td>15364</td>
      <td>55718</td>
      <td>4.197688</td>
      <td>15.223040</td>
    </tr>
  </tbody>
</table>
</div>




```python
pop_Seoul.sort_values(['외국인비율'], ascending=False).head()
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
      <th>자치구</th>
      <th>계</th>
      <th>계.1</th>
      <th>계.2</th>
      <th>65세이상고령자</th>
      <th>외국인비율</th>
      <th>고령자비율</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>10</th>
      <td>도봉구</td>
      <td>346234</td>
      <td>344166</td>
      <td>2068</td>
      <td>53488</td>
      <td>99.402716</td>
      <td>0.597284</td>
    </tr>
    <tr>
      <th>11</th>
      <td>노원구</td>
      <td>558075</td>
      <td>554403</td>
      <td>3672</td>
      <td>74243</td>
      <td>99.342024</td>
      <td>0.657976</td>
    </tr>
    <tr>
      <th>15</th>
      <td>양천구</td>
      <td>475018</td>
      <td>471154</td>
      <td>3864</td>
      <td>55234</td>
      <td>99.186557</td>
      <td>0.813443</td>
    </tr>
    <tr>
      <th>23</th>
      <td>강남구</td>
      <td>561052</td>
      <td>556164</td>
      <td>4888</td>
      <td>65060</td>
      <td>99.128780</td>
      <td>0.871220</td>
    </tr>
    <tr>
      <th>12</th>
      <td>은평구</td>
      <td>491202</td>
      <td>486794</td>
      <td>4408</td>
      <td>74559</td>
      <td>99.102610</td>
      <td>0.897390</td>
    </tr>
  </tbody>
</table>
</div>




```python
pop_Seoul.rename(
    columns={
        pop_Seoul.columns[0]: '구별',
        pop_Seoul.columns[1]: '인구수',
        pop_Seoul.columns[2]: '한국인',
        pop_Seoul.columns[3]: '외국인',
        pop_Seoul.columns[4]: '고령자'
    }, inplace=True 
)

pop_Seoul.head()
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
      <th>구별</th>
      <th>인구수</th>
      <th>한국인</th>
      <th>외국인</th>
      <th>고령자</th>
      <th>외국인비율</th>
      <th>고령자비율</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2</th>
      <td>중구</td>
      <td>134593</td>
      <td>125709</td>
      <td>8884</td>
      <td>21384</td>
      <td>93.399360</td>
      <td>6.600640</td>
    </tr>
    <tr>
      <th>3</th>
      <td>용산구</td>
      <td>244444</td>
      <td>229161</td>
      <td>15283</td>
      <td>36882</td>
      <td>93.747852</td>
      <td>6.252148</td>
    </tr>
    <tr>
      <th>4</th>
      <td>성동구</td>
      <td>312711</td>
      <td>304808</td>
      <td>7903</td>
      <td>41273</td>
      <td>97.472746</td>
      <td>2.527254</td>
    </tr>
    <tr>
      <th>5</th>
      <td>광진구</td>
      <td>372298</td>
      <td>357703</td>
      <td>14595</td>
      <td>43953</td>
      <td>96.079753</td>
      <td>3.920247</td>
    </tr>
    <tr>
      <th>6</th>
      <td>동대문구</td>
      <td>366011</td>
      <td>350647</td>
      <td>15364</td>
      <td>55718</td>
      <td>95.802312</td>
      <td>4.197688</td>
    </tr>
  </tbody>
</table>
</div>



## 4.두 데이터 합치기

---

### pandas에서 데이터 프레임을 병합하는 방법
- pd.concat()
- pd.merge()
- pd.join()



```python
pd.merge(left, right)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    ~\AppData\Local\Temp/ipykernel_4552/302817838.py in <module>
    ----> 1 pd.merge(left, right)
    

    NameError: name 'left' is not defined



```python
#딕셔너리 안에 리스트 형태

left = pd.DataFrame({
        'key' : ['K0', 'K4', 'K2', 'K3'],
        'A' : ['A0', 'A1', 'A2', 'A3',],
        'B' : ['B0', 'B1', 'B2', 'B3']
    
})
left
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
      <th>key</th>
      <th>A</th>
      <th>B</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>K0</td>
      <td>A0</td>
      <td>B0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>K4</td>
      <td>A1</td>
      <td>B1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>K2</td>
      <td>A2</td>
      <td>B2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>K3</td>
      <td>A3</td>
      <td>B3</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 리스트 안의 딕셔너리 형태

right = pd.DataFrame([
    {'key':'K0', 'C' : 'C0', 'D':'D0' },
    {'key':'K1', 'C' : 'C1', 'D':'D1' },
    {'key':'K2', 'C' : 'C2', 'D':'D2' },
    {'key':'K3', 'C' : 'C3', 'D':'D3' }
])
right
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
      <th>key</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>K0</td>
      <td>C0</td>
      <td>D0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>K1</td>
      <td>C1</td>
      <td>D1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>K2</td>
      <td>C2</td>
      <td>D2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>K3</td>
      <td>C3</td>
      <td>D3</td>
    </tr>
  </tbody>
</table>
</div>



### pd.merge()
- 두 데이터 프레임에서 컬럼이나 인덱스를 기준으로 잡고 병합하는 방법
- 기준이 되는 컬럼이나 인덱스를 키값이라고 합니다.
- 기준이 되는 키값은 두 데이터 프레임에 모두 포함되어 있어야 합니다.


```python
pd.merge(left, right, on='key')

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
      <th>key</th>
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>K0</td>
      <td>A0</td>
      <td>B0</td>
      <td>C0</td>
      <td>D0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>K2</td>
      <td>A2</td>
      <td>B2</td>
      <td>C2</td>
      <td>D2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>K3</td>
      <td>A3</td>
      <td>B3</td>
      <td>C3</td>
      <td>D3</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.merge(left, right, how='left' ,on='key')

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
      <th>key</th>
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>K0</td>
      <td>A0</td>
      <td>B0</td>
      <td>C0</td>
      <td>D0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>K4</td>
      <td>A1</td>
      <td>B1</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>K2</td>
      <td>A2</td>
      <td>B2</td>
      <td>C2</td>
      <td>D2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>K3</td>
      <td>A3</td>
      <td>B3</td>
      <td>C3</td>
      <td>D3</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.merge(left, right, how='right' ,on='key')

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
      <th>key</th>
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>K0</td>
      <td>A0</td>
      <td>B0</td>
      <td>C0</td>
      <td>D0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>K1</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>C1</td>
      <td>D1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>K2</td>
      <td>A2</td>
      <td>B2</td>
      <td>C2</td>
      <td>D2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>K3</td>
      <td>A3</td>
      <td>B3</td>
      <td>C3</td>
      <td>D3</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.merge(left, right, how='outer' ,on='key')

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
      <th>key</th>
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>K0</td>
      <td>A0</td>
      <td>B0</td>
      <td>C0</td>
      <td>D0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>K4</td>
      <td>A1</td>
      <td>B1</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>K2</td>
      <td>A2</td>
      <td>B2</td>
      <td>C2</td>
      <td>D2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>K3</td>
      <td>A3</td>
      <td>B3</td>
      <td>C3</td>
      <td>D3</td>
    </tr>
    <tr>
      <th>4</th>
      <td>K1</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>C1</td>
      <td>D1</td>
    </tr>
  </tbody>
</table>
</div>



---


```python
CCTV_Seoul.head(1)
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
      <th>구별</th>
      <th>소계</th>
      <th>2013년도 이전</th>
      <th>2014년</th>
      <th>2015년</th>
      <th>2016년</th>
      <th>최근증가율</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>강남구</td>
      <td>3238</td>
      <td>1292</td>
      <td>430</td>
      <td>584</td>
      <td>932</td>
      <td>150.619195</td>
    </tr>
  </tbody>
</table>
</div>




```python
pop_Seoul.head(1)
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
      <th>구별</th>
      <th>인구수</th>
      <th>한국인</th>
      <th>외국인</th>
      <th>고령자</th>
      <th>외국인비율</th>
      <th>고령자비율</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2</th>
      <td>중구</td>
      <td>134593</td>
      <td>125709</td>
      <td>8884</td>
      <td>21384</td>
      <td>6.60064</td>
      <td>15.887899</td>
    </tr>
  </tbody>
</table>
</div>




```python
data_result = pd.merge(CCTV_Seoul, pop_Seoul, on='구별')
data_result.head()
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
      <th>구별</th>
      <th>소계</th>
      <th>2013년도 이전</th>
      <th>2014년</th>
      <th>2015년</th>
      <th>2016년</th>
      <th>최근증가율</th>
      <th>인구수</th>
      <th>한국인</th>
      <th>외국인</th>
      <th>고령자</th>
      <th>외국인비율</th>
      <th>고령자비율</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>강남구</td>
      <td>3238</td>
      <td>1292</td>
      <td>430</td>
      <td>584</td>
      <td>932</td>
      <td>150.619195</td>
      <td>561052</td>
      <td>556164</td>
      <td>4888</td>
      <td>65060</td>
      <td>0.871220</td>
      <td>11.596073</td>
    </tr>
    <tr>
      <th>1</th>
      <td>강동구</td>
      <td>1010</td>
      <td>379</td>
      <td>99</td>
      <td>155</td>
      <td>377</td>
      <td>166.490765</td>
      <td>440359</td>
      <td>436223</td>
      <td>4136</td>
      <td>56161</td>
      <td>0.939234</td>
      <td>12.753458</td>
    </tr>
    <tr>
      <th>2</th>
      <td>강북구</td>
      <td>831</td>
      <td>369</td>
      <td>120</td>
      <td>138</td>
      <td>204</td>
      <td>125.203252</td>
      <td>328002</td>
      <td>324479</td>
      <td>3523</td>
      <td>56530</td>
      <td>1.074079</td>
      <td>17.234651</td>
    </tr>
    <tr>
      <th>3</th>
      <td>강서구</td>
      <td>911</td>
      <td>388</td>
      <td>258</td>
      <td>184</td>
      <td>81</td>
      <td>134.793814</td>
      <td>608255</td>
      <td>601691</td>
      <td>6564</td>
      <td>76032</td>
      <td>1.079153</td>
      <td>12.500021</td>
    </tr>
    <tr>
      <th>4</th>
      <td>관악구</td>
      <td>2109</td>
      <td>846</td>
      <td>260</td>
      <td>390</td>
      <td>613</td>
      <td>149.290780</td>
      <td>520929</td>
      <td>503297</td>
      <td>17632</td>
      <td>70046</td>
      <td>3.384722</td>
      <td>13.446362</td>
    </tr>
  </tbody>
</table>
</div>



### 년도별 데이터 컬럼 삭제
- del
- drop()


```python
del data_result['2013년도 이전']
data_result.head()
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
      <th>구별</th>
      <th>소계</th>
      <th>2014년</th>
      <th>2015년</th>
      <th>2016년</th>
      <th>최근증가율</th>
      <th>인구수</th>
      <th>한국인</th>
      <th>외국인</th>
      <th>고령자</th>
      <th>외국인비율</th>
      <th>고령자비율</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>강남구</td>
      <td>3238</td>
      <td>430</td>
      <td>584</td>
      <td>932</td>
      <td>150.619195</td>
      <td>561052</td>
      <td>556164</td>
      <td>4888</td>
      <td>65060</td>
      <td>0.871220</td>
      <td>11.596073</td>
    </tr>
    <tr>
      <th>1</th>
      <td>강동구</td>
      <td>1010</td>
      <td>99</td>
      <td>155</td>
      <td>377</td>
      <td>166.490765</td>
      <td>440359</td>
      <td>436223</td>
      <td>4136</td>
      <td>56161</td>
      <td>0.939234</td>
      <td>12.753458</td>
    </tr>
    <tr>
      <th>2</th>
      <td>강북구</td>
      <td>831</td>
      <td>120</td>
      <td>138</td>
      <td>204</td>
      <td>125.203252</td>
      <td>328002</td>
      <td>324479</td>
      <td>3523</td>
      <td>56530</td>
      <td>1.074079</td>
      <td>17.234651</td>
    </tr>
    <tr>
      <th>3</th>
      <td>강서구</td>
      <td>911</td>
      <td>258</td>
      <td>184</td>
      <td>81</td>
      <td>134.793814</td>
      <td>608255</td>
      <td>601691</td>
      <td>6564</td>
      <td>76032</td>
      <td>1.079153</td>
      <td>12.500021</td>
    </tr>
    <tr>
      <th>4</th>
      <td>관악구</td>
      <td>2109</td>
      <td>260</td>
      <td>390</td>
      <td>613</td>
      <td>149.290780</td>
      <td>520929</td>
      <td>503297</td>
      <td>17632</td>
      <td>70046</td>
      <td>3.384722</td>
      <td>13.446362</td>
    </tr>
  </tbody>
</table>
</div>




```python
del data_result['2014년']

```


```python
data_result.head(3)
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
      <th>구별</th>
      <th>소계</th>
      <th>2015년</th>
      <th>2016년</th>
      <th>최근증가율</th>
      <th>인구수</th>
      <th>한국인</th>
      <th>외국인</th>
      <th>고령자</th>
      <th>외국인비율</th>
      <th>고령자비율</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>강남구</td>
      <td>3238</td>
      <td>584</td>
      <td>932</td>
      <td>150.619195</td>
      <td>561052</td>
      <td>556164</td>
      <td>4888</td>
      <td>65060</td>
      <td>0.871220</td>
      <td>11.596073</td>
    </tr>
    <tr>
      <th>1</th>
      <td>강동구</td>
      <td>1010</td>
      <td>155</td>
      <td>377</td>
      <td>166.490765</td>
      <td>440359</td>
      <td>436223</td>
      <td>4136</td>
      <td>56161</td>
      <td>0.939234</td>
      <td>12.753458</td>
    </tr>
    <tr>
      <th>2</th>
      <td>강북구</td>
      <td>831</td>
      <td>138</td>
      <td>204</td>
      <td>125.203252</td>
      <td>328002</td>
      <td>324479</td>
      <td>3523</td>
      <td>56530</td>
      <td>1.074079</td>
      <td>17.234651</td>
    </tr>
  </tbody>
</table>
</div>




```python
data_result.drop(['2015년', '2016년'], axis=1, inplace=True)
```


```python
data_result.head()
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
      <th>구별</th>
      <th>소계</th>
      <th>최근증가율</th>
      <th>인구수</th>
      <th>한국인</th>
      <th>외국인</th>
      <th>고령자</th>
      <th>외국인비율</th>
      <th>고령자비율</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>강남구</td>
      <td>3238</td>
      <td>150.619195</td>
      <td>561052</td>
      <td>556164</td>
      <td>4888</td>
      <td>65060</td>
      <td>0.871220</td>
      <td>11.596073</td>
    </tr>
    <tr>
      <th>1</th>
      <td>강동구</td>
      <td>1010</td>
      <td>166.490765</td>
      <td>440359</td>
      <td>436223</td>
      <td>4136</td>
      <td>56161</td>
      <td>0.939234</td>
      <td>12.753458</td>
    </tr>
    <tr>
      <th>2</th>
      <td>강북구</td>
      <td>831</td>
      <td>125.203252</td>
      <td>328002</td>
      <td>324479</td>
      <td>3523</td>
      <td>56530</td>
      <td>1.074079</td>
      <td>17.234651</td>
    </tr>
    <tr>
      <th>3</th>
      <td>강서구</td>
      <td>911</td>
      <td>134.793814</td>
      <td>608255</td>
      <td>601691</td>
      <td>6564</td>
      <td>76032</td>
      <td>1.079153</td>
      <td>12.500021</td>
    </tr>
    <tr>
      <th>4</th>
      <td>관악구</td>
      <td>2109</td>
      <td>149.290780</td>
      <td>520929</td>
      <td>503297</td>
      <td>17632</td>
      <td>70046</td>
      <td>3.384722</td>
      <td>13.446362</td>
    </tr>
  </tbody>
</table>
</div>



### 인덱스 변경
- set_index()
- 선택한 컬럼을 데이터 프레임의 인덱스로 지정


```python
data_result.set_index('구별', inplace=True)
data_result.head()
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
      <th>소계</th>
      <th>최근증가율</th>
      <th>인구수</th>
      <th>한국인</th>
      <th>외국인</th>
      <th>고령자</th>
      <th>외국인비율</th>
      <th>고령자비율</th>
    </tr>
    <tr>
      <th>구별</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>강남구</th>
      <td>3238</td>
      <td>150.619195</td>
      <td>561052</td>
      <td>556164</td>
      <td>4888</td>
      <td>65060</td>
      <td>0.871220</td>
      <td>11.596073</td>
    </tr>
    <tr>
      <th>강동구</th>
      <td>1010</td>
      <td>166.490765</td>
      <td>440359</td>
      <td>436223</td>
      <td>4136</td>
      <td>56161</td>
      <td>0.939234</td>
      <td>12.753458</td>
    </tr>
    <tr>
      <th>강북구</th>
      <td>831</td>
      <td>125.203252</td>
      <td>328002</td>
      <td>324479</td>
      <td>3523</td>
      <td>56530</td>
      <td>1.074079</td>
      <td>17.234651</td>
    </tr>
    <tr>
      <th>강서구</th>
      <td>911</td>
      <td>134.793814</td>
      <td>608255</td>
      <td>601691</td>
      <td>6564</td>
      <td>76032</td>
      <td>1.079153</td>
      <td>12.500021</td>
    </tr>
    <tr>
      <th>관악구</th>
      <td>2109</td>
      <td>149.290780</td>
      <td>520929</td>
      <td>503297</td>
      <td>17632</td>
      <td>70046</td>
      <td>3.384722</td>
      <td>13.446362</td>
    </tr>
  </tbody>
</table>
</div>



### 상관계수
- corr()
- correlation 의 약자입니다.
- 상관계수가 0.2 이상인 데이터를 비교


```python
data_result.corr()
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
      <th>소계</th>
      <th>최근증가율</th>
      <th>인구수</th>
      <th>한국인</th>
      <th>외국인</th>
      <th>고령자</th>
      <th>외국인비율</th>
      <th>고령자비율</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>소계</th>
      <td>1.000000</td>
      <td>-0.311987</td>
      <td>0.267334</td>
      <td>0.261189</td>
      <td>0.031542</td>
      <td>0.194263</td>
      <td>-0.055409</td>
      <td>-0.289987</td>
    </tr>
    <tr>
      <th>최근증가율</th>
      <td>-0.311987</td>
      <td>1.000000</td>
      <td>0.089811</td>
      <td>0.099062</td>
      <td>-0.159121</td>
      <td>0.126772</td>
      <td>-0.168722</td>
      <td>0.075324</td>
    </tr>
    <tr>
      <th>인구수</th>
      <td>0.267334</td>
      <td>0.089811</td>
      <td>1.000000</td>
      <td>0.997859</td>
      <td>-0.194693</td>
      <td>0.925172</td>
      <td>-0.571380</td>
      <td>-0.596381</td>
    </tr>
    <tr>
      <th>한국인</th>
      <td>0.261189</td>
      <td>0.099062</td>
      <td>0.997859</td>
      <td>1.000000</td>
      <td>-0.258419</td>
      <td>0.924846</td>
      <td>-0.620668</td>
      <td>-0.586506</td>
    </tr>
    <tr>
      <th>외국인</th>
      <td>0.031542</td>
      <td>-0.159121</td>
      <td>-0.194693</td>
      <td>-0.258419</td>
      <td>1.000000</td>
      <td>-0.204951</td>
      <td>0.868861</td>
      <td>-0.012851</td>
    </tr>
    <tr>
      <th>고령자</th>
      <td>0.194263</td>
      <td>0.126772</td>
      <td>0.925172</td>
      <td>0.924846</td>
      <td>-0.204951</td>
      <td>1.000000</td>
      <td>-0.593068</td>
      <td>-0.267379</td>
    </tr>
    <tr>
      <th>외국인비율</th>
      <td>-0.055409</td>
      <td>-0.168722</td>
      <td>-0.571380</td>
      <td>-0.620668</td>
      <td>0.868861</td>
      <td>-0.593068</td>
      <td>1.000000</td>
      <td>0.190727</td>
    </tr>
    <tr>
      <th>고령자비율</th>
      <td>-0.289987</td>
      <td>0.075324</td>
      <td>-0.596381</td>
      <td>-0.586506</td>
      <td>-0.012851</td>
      <td>-0.267379</td>
      <td>0.190727</td>
      <td>1.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
data_result.info()
```

    <class 'pandas.core.frame.DataFrame'>
    Index: 24 entries, 강남구 to 중랑구
    Data columns (total 8 columns):
     #   Column  Non-Null Count  Dtype  
    ---  ------  --------------  -----  
     0   소계      24 non-null     int64  
     1   최근증가율   24 non-null     float64
     2   인구수     24 non-null     int64  
     3   한국인     24 non-null     int64  
     4   외국인     24 non-null     int64  
     5   고령자     24 non-null     int64  
     6   외국인비율   24 non-null     float64
     7   고령자비율   24 non-null     float64
    dtypes: float64(3), int64(5)
    memory usage: 1.7+ KB
    

corr() 는 문자열 같은게 들어가 있으면 연산이 되지 않는다.


```python
data_result['CCTV비율'] = data_result['소계'] / data_result['인구수']
data_result['CCTV비율'] = data_result['CCTV비율'] * 100
```


```python
data_result.head()
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
      <th>소계</th>
      <th>최근증가율</th>
      <th>인구수</th>
      <th>한국인</th>
      <th>외국인</th>
      <th>고령자</th>
      <th>외국인비율</th>
      <th>고령자비율</th>
      <th>CCTV비율</th>
    </tr>
    <tr>
      <th>구별</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>강남구</th>
      <td>3238</td>
      <td>150.619195</td>
      <td>561052</td>
      <td>556164</td>
      <td>4888</td>
      <td>65060</td>
      <td>0.871220</td>
      <td>11.596073</td>
      <td>0.577130</td>
    </tr>
    <tr>
      <th>강동구</th>
      <td>1010</td>
      <td>166.490765</td>
      <td>440359</td>
      <td>436223</td>
      <td>4136</td>
      <td>56161</td>
      <td>0.939234</td>
      <td>12.753458</td>
      <td>0.229358</td>
    </tr>
    <tr>
      <th>강북구</th>
      <td>831</td>
      <td>125.203252</td>
      <td>328002</td>
      <td>324479</td>
      <td>3523</td>
      <td>56530</td>
      <td>1.074079</td>
      <td>17.234651</td>
      <td>0.253352</td>
    </tr>
    <tr>
      <th>강서구</th>
      <td>911</td>
      <td>134.793814</td>
      <td>608255</td>
      <td>601691</td>
      <td>6564</td>
      <td>76032</td>
      <td>1.079153</td>
      <td>12.500021</td>
      <td>0.149773</td>
    </tr>
    <tr>
      <th>관악구</th>
      <td>2109</td>
      <td>149.290780</td>
      <td>520929</td>
      <td>503297</td>
      <td>17632</td>
      <td>70046</td>
      <td>3.384722</td>
      <td>13.446362</td>
      <td>0.404854</td>
    </tr>
  </tbody>
</table>
</div>




```python
data_result.sort_values(by='CCTV비율', ascending=False).head()
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
      <th>소계</th>
      <th>최근증가율</th>
      <th>인구수</th>
      <th>한국인</th>
      <th>외국인</th>
      <th>고령자</th>
      <th>외국인비율</th>
      <th>고령자비율</th>
      <th>CCTV비율</th>
    </tr>
    <tr>
      <th>구별</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>용산구</th>
      <td>2096</td>
      <td>53.216374</td>
      <td>244444</td>
      <td>229161</td>
      <td>15283</td>
      <td>36882</td>
      <td>6.252148</td>
      <td>15.088118</td>
      <td>0.857456</td>
    </tr>
    <tr>
      <th>중구</th>
      <td>1023</td>
      <td>147.699758</td>
      <td>134593</td>
      <td>125709</td>
      <td>8884</td>
      <td>21384</td>
      <td>6.600640</td>
      <td>15.887899</td>
      <td>0.760069</td>
    </tr>
    <tr>
      <th>강남구</th>
      <td>3238</td>
      <td>150.619195</td>
      <td>561052</td>
      <td>556164</td>
      <td>4888</td>
      <td>65060</td>
      <td>0.871220</td>
      <td>11.596073</td>
      <td>0.577130</td>
    </tr>
    <tr>
      <th>금천구</th>
      <td>1348</td>
      <td>100.000000</td>
      <td>253491</td>
      <td>235154</td>
      <td>18337</td>
      <td>34170</td>
      <td>7.233787</td>
      <td>13.479769</td>
      <td>0.531774</td>
    </tr>
    <tr>
      <th>양천구</th>
      <td>2482</td>
      <td>34.671731</td>
      <td>475018</td>
      <td>471154</td>
      <td>3864</td>
      <td>55234</td>
      <td>0.813443</td>
      <td>11.627770</td>
      <td>0.522507</td>
    </tr>
  </tbody>
</table>
</div>



---

# matplotib 기초


```python
import matplotlib.pyplot as plt
from matplotlib import rc

rc('font', family='Aerial Unicode MS') #Windows : Malgu Gothic
# $matpoltlib inline
get_ipython().run_line_magic('matplotlib', 'inline')
```

import matplotlib.pyplot as plt  : matplotib에서 pyplot을 불러오는건데 matlab 의 시각화 툴이라고 생각하면 된다.  
get_ipython().run_line_magic('matplotlib', 'inline') : 이 설정을 해줘야 밑에 그래프처럼 나타낼수가 있다.

### matplotlib 그래프 기본 형태
- plt.figure(figsize=(10,6))  
- plt.plot()  
- plt.show  


```python
plt.figure(figsize=(10,6))
plt.plot([0,1,2,3,4,5,6,7,8,9], [1,1,2,3,4,2,3,5,-1,3])
plt.show()
```

    findfont: Font family ['Aerial Unicode MS'] not found. Falling back to DejaVu Sans.
    


    
![png](output_171_1.png)
    


### 예제1: 그래프 기초

### 삼각함수 그리기
- np.arange(a,b,s): a부터 b까지 s의 간격
- np.sin(value)


```python
import numpy as np

t = np.arange(0, 12, 0.01)
y = np.sin(t)
```


```python
plt.figure(figsize=(10,6))
plt.plot(t, np.sin(t))
plt.plot(t, np.cos(t))
plt.show()
```


    
![png](output_175_0.png)
    


- 1. 격자무늬 추가
- 2. 그래프 제목 추가
- 3. x축, y축 제목 추가
- 4. 주황색, 파란색 선 데이터 의미 구분


```python
plt.figure(figsize=(10,6))
plt.plot(t, np.sin(t), label = 'sin')
plt.plot(t, np.cos(t), label = 'cos')
plt.grid(True) #격자무늬
# plt.legend(labels=['sin','cos']) #범례 이렇게도 가능
plt.legend(loc = 'lower left') 
plt.title('Example of sinewave')
plt.xlabel('time')
plt.ylabel('amlitude') #진폭
plt.show()
```


    
![png](output_177_0.png)
    



```python
def drawGraph():
    
    plt.figure(figsize=(10,6))
    plt.plot(t, np.sin(t), label = 'sin')
    plt.plot(t, np.cos(t), label = 'cos')
    plt.grid(True) #격자무늬
    # plt.legend(labels=['sin','cos']) #범례 이렇게도 가능
    plt.legend(loc = 'lower left') 
    plt.title('Example of sinewave')
    plt.xlabel('time')
    plt.ylabel('Amplitude') #진폭
    plt.show()
```


```python
drawGraph()
```


    
![png](output_179_0.png)
    


### 예제2: 그래프 커스텀


```python
t = np.arange(0, 5, 0.5)
t
```




    array([0. , 0.5, 1. , 1.5, 2. , 2.5, 3. , 3.5, 4. , 4.5])




```python
plt.figure(figsize=(10,6))
plt.plot(t,t, "r--")
plt.plot(t,t ** 2, "bs")
plt.plot(t,t ** 3, "g^")
plt.show
```




    <function matplotlib.pyplot.show(close=None, block=None)>




    
![png](output_182_1.png)
    



```python
#t = [0,1,2,3,4,5,6]
t = list(range(0,7))
y = [1,4,5,8,9,5,3]
```


```python
def drawGraph():
    plt.figure(figsize=(10,6))
    plt.plot(
        t,
        y,
        color='green',
        linestyle='dashed',
        marker='o',
        markerfacecolor='blue',
        markersize=15,
    )

    plt.xlim([-0.5, 6.5])
    plt.ylim([0.5,9.5])
    plt.show()
    
drawGraph()
```


    
![png](output_184_0.png)
    


### 예제3: scatter plot


```python
t = np.array(range(0,10))
y = np.array([9,8,7,9,8,3,2,4,3,4])

```


```python
def drawGraph():
        
    plt.figure(figsize=(10,6))
    plt.scatter(t,y)
    plt.show

drawGraph()
```


    
![png](output_187_0.png)
    



```python
colormap = t

def drawGraph():
    
    plt.figure(figsize=(20, 6))
    plt.scatter(t, y, s=50, c=colormap, marker='>')
    plt.colorbar()
    plt.show()
    
drawGraph()
```


    
![png](output_188_0.png)
    


### 예제4: pandas에서 plot그리기
- matplotlib 을 가져와서 사용합니다


```python
data_result.head()
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
      <th>소계</th>
      <th>최근증가율</th>
      <th>인구수</th>
      <th>한국인</th>
      <th>외국인</th>
      <th>고령자</th>
      <th>외국인비율</th>
      <th>고령자비율</th>
      <th>CCTV비율</th>
    </tr>
    <tr>
      <th>구별</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>강남구</th>
      <td>3238</td>
      <td>150.619195</td>
      <td>561052</td>
      <td>556164</td>
      <td>4888</td>
      <td>65060</td>
      <td>0.871220</td>
      <td>11.596073</td>
      <td>0.577130</td>
    </tr>
    <tr>
      <th>강동구</th>
      <td>1010</td>
      <td>166.490765</td>
      <td>440359</td>
      <td>436223</td>
      <td>4136</td>
      <td>56161</td>
      <td>0.939234</td>
      <td>12.753458</td>
      <td>0.229358</td>
    </tr>
    <tr>
      <th>강북구</th>
      <td>831</td>
      <td>125.203252</td>
      <td>328002</td>
      <td>324479</td>
      <td>3523</td>
      <td>56530</td>
      <td>1.074079</td>
      <td>17.234651</td>
      <td>0.253352</td>
    </tr>
    <tr>
      <th>강서구</th>
      <td>911</td>
      <td>134.793814</td>
      <td>608255</td>
      <td>601691</td>
      <td>6564</td>
      <td>76032</td>
      <td>1.079153</td>
      <td>12.500021</td>
      <td>0.149773</td>
    </tr>
    <tr>
      <th>관악구</th>
      <td>2109</td>
      <td>149.290780</td>
      <td>520929</td>
      <td>503297</td>
      <td>17632</td>
      <td>70046</td>
      <td>3.384722</td>
      <td>13.446362</td>
      <td>0.404854</td>
    </tr>
  </tbody>
</table>
</div>




```python
data_result['인구수'].plot(kind='bar', figsize=(10, 10))
```




    <AxesSubplot:xlabel='구별'>



    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 44053 (\N{HANGUL SYLLABLE GANG}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 45224 (\N{HANGUL SYLLABLE NAM}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 44396 (\N{HANGUL SYLLABLE GU}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 46041 (\N{HANGUL SYLLABLE DONG}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 48513 (\N{HANGUL SYLLABLE BUG}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 49436 (\N{HANGUL SYLLABLE SEO}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 44288 (\N{HANGUL SYLLABLE GWAN}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 50501 (\N{HANGUL SYLLABLE AG}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 44305 (\N{HANGUL SYLLABLE GWANG}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 51652 (\N{HANGUL SYLLABLE JIN}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 47196 (\N{HANGUL SYLLABLE RO}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 44552 (\N{HANGUL SYLLABLE GEUM}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 52380 (\N{HANGUL SYLLABLE CEON}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 45432 (\N{HANGUL SYLLABLE NO}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 50896 (\N{HANGUL SYLLABLE WEON}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 46020 (\N{HANGUL SYLLABLE DO}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 48393 (\N{HANGUL SYLLABLE BONG}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 45824 (\N{HANGUL SYLLABLE DAE}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 47928 (\N{HANGUL SYLLABLE MUN}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 51089 (\N{HANGUL SYLLABLE JAG}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 47560 (\N{HANGUL SYLLABLE MA}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 54252 (\N{HANGUL SYLLABLE PO}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 52488 (\N{HANGUL SYLLABLE CO}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 49457 (\N{HANGUL SYLLABLE SEONG}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 49569 (\N{HANGUL SYLLABLE SONG}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 54028 (\N{HANGUL SYLLABLE PA}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 50577 (\N{HANGUL SYLLABLE YANG}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 50689 (\N{HANGUL SYLLABLE YEONG}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 46321 (\N{HANGUL SYLLABLE DEUNG}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 50857 (\N{HANGUL SYLLABLE YONG}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 49328 (\N{HANGUL SYLLABLE SAN}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 51008 (\N{HANGUL SYLLABLE EUN}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 54217 (\N{HANGUL SYLLABLE PYEONG}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 51473 (\N{HANGUL SYLLABLE JUNG}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 46993 (\N{HANGUL SYLLABLE RANG}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\IPython\core\pylabtools.py:151: UserWarning: Glyph 48324 (\N{HANGUL SYLLABLE BYEOL}) missing from current font.
      fig.canvas.print_figure(bytes_io, **kw)
    


    
![png](output_191_2.png)
    



```python
data_result['인구수'].plot(kind='barh', figsize=(10, 10))
```




    <AxesSubplot:ylabel='구별'>




    
![png](output_192_1.png)
    


---


```python
import matplotlib.pyplot as plt
# import matplotlib as apl

plt.rcParams['axes.unicode_minus'] = False # 마이너스 부호 때문에 한글이 깨질 수 가 있어 주는 설정
rc('font', family='Malgun Gothic')
# %matplotlib inline
get_ipython().run_line_magic('matplotlib', 'inline')
```


```python
data_result.head()
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
      <th>소계</th>
      <th>최근증가율</th>
      <th>인구수</th>
      <th>한국인</th>
      <th>외국인</th>
      <th>고령자</th>
      <th>외국인비율</th>
      <th>고령자비율</th>
      <th>CCTV비율</th>
    </tr>
    <tr>
      <th>구별</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>강남구</th>
      <td>3238</td>
      <td>150.619195</td>
      <td>561052</td>
      <td>556164</td>
      <td>4888</td>
      <td>65060</td>
      <td>0.871220</td>
      <td>11.596073</td>
      <td>0.577130</td>
    </tr>
    <tr>
      <th>강동구</th>
      <td>1010</td>
      <td>166.490765</td>
      <td>440359</td>
      <td>436223</td>
      <td>4136</td>
      <td>56161</td>
      <td>0.939234</td>
      <td>12.753458</td>
      <td>0.229358</td>
    </tr>
    <tr>
      <th>강북구</th>
      <td>831</td>
      <td>125.203252</td>
      <td>328002</td>
      <td>324479</td>
      <td>3523</td>
      <td>56530</td>
      <td>1.074079</td>
      <td>17.234651</td>
      <td>0.253352</td>
    </tr>
    <tr>
      <th>강서구</th>
      <td>911</td>
      <td>134.793814</td>
      <td>608255</td>
      <td>601691</td>
      <td>6564</td>
      <td>76032</td>
      <td>1.079153</td>
      <td>12.500021</td>
      <td>0.149773</td>
    </tr>
    <tr>
      <th>관악구</th>
      <td>2109</td>
      <td>149.290780</td>
      <td>520929</td>
      <td>503297</td>
      <td>17632</td>
      <td>70046</td>
      <td>3.384722</td>
      <td>13.446362</td>
      <td>0.404854</td>
    </tr>
  </tbody>
</table>
</div>



### 소계 컬럼 시각화


```python
data_result['소계'].plot(kind='barh', grid=True, figsize=(10,10));
```


    
![png](output_197_0.png)
    


; 세미콜론을 찍으면 깔끔하게 그래프만 출력된다.


```python
def drawGraph():
    data_result['소계'].sort_values().plot(
        kind='barh', grid=True, title='가장 CCTV가 많은 구', figsize=(10,10));
drawGraph()
```


    
![png](output_199_0.png)
    



```python
data_result.head()
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
      <th>소계</th>
      <th>최근증가율</th>
      <th>인구수</th>
      <th>한국인</th>
      <th>외국인</th>
      <th>고령자</th>
      <th>외국인비율</th>
      <th>고령자비율</th>
      <th>CCTV비율</th>
    </tr>
    <tr>
      <th>구별</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>강남구</th>
      <td>3238</td>
      <td>150.619195</td>
      <td>561052</td>
      <td>556164</td>
      <td>4888</td>
      <td>65060</td>
      <td>0.871220</td>
      <td>11.596073</td>
      <td>0.577130</td>
    </tr>
    <tr>
      <th>강동구</th>
      <td>1010</td>
      <td>166.490765</td>
      <td>440359</td>
      <td>436223</td>
      <td>4136</td>
      <td>56161</td>
      <td>0.939234</td>
      <td>12.753458</td>
      <td>0.229358</td>
    </tr>
    <tr>
      <th>강북구</th>
      <td>831</td>
      <td>125.203252</td>
      <td>328002</td>
      <td>324479</td>
      <td>3523</td>
      <td>56530</td>
      <td>1.074079</td>
      <td>17.234651</td>
      <td>0.253352</td>
    </tr>
    <tr>
      <th>강서구</th>
      <td>911</td>
      <td>134.793814</td>
      <td>608255</td>
      <td>601691</td>
      <td>6564</td>
      <td>76032</td>
      <td>1.079153</td>
      <td>12.500021</td>
      <td>0.149773</td>
    </tr>
    <tr>
      <th>관악구</th>
      <td>2109</td>
      <td>149.290780</td>
      <td>520929</td>
      <td>503297</td>
      <td>17632</td>
      <td>70046</td>
      <td>3.384722</td>
      <td>13.446362</td>
      <td>0.404854</td>
    </tr>
  </tbody>
</table>
</div>




```python
def drawGraph():
    data_result['CCTV비율'].sort_values().plot(
        kind='barh', grid=True, title='가장 CCTV가 많은 구', figsize=(10,10));
drawGraph()
# Data Frame Plot 검색하면 더 자세한 데이터 설명을 알 수 있다.
```


    
![png](output_201_0.png)
    


## 6. 데이터의 경향 표시


```python
data_result.head()
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
      <th>소계</th>
      <th>최근증가율</th>
      <th>인구수</th>
      <th>한국인</th>
      <th>외국인</th>
      <th>고령자</th>
      <th>외국인비율</th>
      <th>고령자비율</th>
      <th>CCTV비율</th>
    </tr>
    <tr>
      <th>구별</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>강남구</th>
      <td>3238</td>
      <td>150.619195</td>
      <td>561052</td>
      <td>556164</td>
      <td>4888</td>
      <td>65060</td>
      <td>0.871220</td>
      <td>11.596073</td>
      <td>0.577130</td>
    </tr>
    <tr>
      <th>강동구</th>
      <td>1010</td>
      <td>166.490765</td>
      <td>440359</td>
      <td>436223</td>
      <td>4136</td>
      <td>56161</td>
      <td>0.939234</td>
      <td>12.753458</td>
      <td>0.229358</td>
    </tr>
    <tr>
      <th>강북구</th>
      <td>831</td>
      <td>125.203252</td>
      <td>328002</td>
      <td>324479</td>
      <td>3523</td>
      <td>56530</td>
      <td>1.074079</td>
      <td>17.234651</td>
      <td>0.253352</td>
    </tr>
    <tr>
      <th>강서구</th>
      <td>911</td>
      <td>134.793814</td>
      <td>608255</td>
      <td>601691</td>
      <td>6564</td>
      <td>76032</td>
      <td>1.079153</td>
      <td>12.500021</td>
      <td>0.149773</td>
    </tr>
    <tr>
      <th>관악구</th>
      <td>2109</td>
      <td>149.290780</td>
      <td>520929</td>
      <td>503297</td>
      <td>17632</td>
      <td>70046</td>
      <td>3.384722</td>
      <td>13.446362</td>
      <td>0.404854</td>
    </tr>
  </tbody>
</table>
</div>



### 인구수와 소계 컬럼으로 scatter plot 그리기


```python
def drawGraph():
    
    plt.figure(figsize=(14,10))
    plt.scatter(data_result['인구수'], data_result['소계'], s=50)
    plt.xlabel('인구수')
    plt.ylabel("CCTV")
    plt.grid(True)
    plt.show()

drawGraph()
```


    
![png](output_205_0.png)
    


#### Numpy를 이용한 1차 직선 만들기
- np.polyfit(): 직선을 구성하기 위한 계수를 계산
- np.poly1d(): polyfit 으로 찾은 계수로 파이썬에서 사용할 수 있는 함수로 만들어주는 기능


```python
import numpy as np

```


```python
fp1 = np.polyfit(data_result['인구수'], data_result['소계'], 1)
fp1
```




    array([1.38596837e-03, 9.35804531e+02])




```python
f1 = np.poly1d(fp1)
f1
```




    poly1d([1.38596837e-03, 9.35804531e+02])




```python
f1(400000)
```




    1490.191879351763



- 인구가 40만인 구에서 서울시의 전체 경향에 맞는 적당한 CCTV 수는?


```python
fx = np.linspace(100000, 700000, 100)
fx
```




    array([100000.        , 106060.60606061, 112121.21212121, 118181.81818182,
           124242.42424242, 130303.03030303, 136363.63636364, 142424.24242424,
           148484.84848485, 154545.45454545, 160606.06060606, 166666.66666667,
           172727.27272727, 178787.87878788, 184848.48484848, 190909.09090909,
           196969.6969697 , 203030.3030303 , 209090.90909091, 215151.51515152,
           221212.12121212, 227272.72727273, 233333.33333333, 239393.93939394,
           245454.54545455, 251515.15151515, 257575.75757576, 263636.36363636,
           269696.96969697, 275757.57575758, 281818.18181818, 287878.78787879,
           293939.39393939, 300000.        , 306060.60606061, 312121.21212121,
           318181.81818182, 324242.42424242, 330303.03030303, 336363.63636364,
           342424.24242424, 348484.84848485, 354545.45454545, 360606.06060606,
           366666.66666667, 372727.27272727, 378787.87878788, 384848.48484848,
           390909.09090909, 396969.6969697 , 403030.3030303 , 409090.90909091,
           415151.51515152, 421212.12121212, 427272.72727273, 433333.33333333,
           439393.93939394, 445454.54545455, 451515.15151515, 457575.75757576,
           463636.36363636, 469696.96969697, 475757.57575758, 481818.18181818,
           487878.78787879, 493939.39393939, 500000.        , 506060.60606061,
           512121.21212121, 518181.81818182, 524242.42424242, 530303.03030303,
           536363.63636364, 542424.24242424, 548484.84848485, 554545.45454545,
           560606.06060606, 566666.66666667, 572727.27272727, 578787.87878788,
           584848.48484848, 590909.09090909, 596969.6969697 , 603030.3030303 ,
           609090.90909091, 615151.51515152, 621212.12121212, 627272.72727273,
           633333.33333333, 639393.93939394, 645454.54545455, 651515.15151515,
           657575.75757576, 663636.36363636, 669696.96969697, 675757.57575758,
           681818.18181818, 687878.78787879, 693939.39393939, 700000.        ])



- 경향선을 그리기 위한 X 데이터 생성  
- np.linspace(a,b,n): a부터 b까지 n개의 등간격 데이터 생성


```python
def drawGraph():
    
    plt.figure(figsize=(14,10))
    plt.scatter(data_result['인구수'], data_result['소계'], s=50)
    plt.plot(fx, f1(fx), ls='dashed', lw=3, color='g')
    plt.xlabel('인구수')
    plt.ylabel("CCTV")
    plt.grid(True)
    plt.show()

drawGraph()
```


    
![png](output_214_0.png)
    


### 7. 강조하고 싶은 데이터를 시각화해보자

### 그래프 다듬기
#### 경향과의 오차 만들기
- 경향(trend)과의 오차를 만들자
- 경향은 f1 함수에 해당 인구를 입력
- f1(data_result['인구수'])


```python
fp1 = np.polyfit(data_result['인구수'], data_result['소계'],1)
f1 = np.poly1d(fp1)
fx = np.linspace(100000, 700000, 100)
```


```python
data_result.head(3)
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
      <th>소계</th>
      <th>최근증가율</th>
      <th>인구수</th>
      <th>한국인</th>
      <th>외국인</th>
      <th>고령자</th>
      <th>외국인비율</th>
      <th>고령자비율</th>
      <th>CCTV비율</th>
    </tr>
    <tr>
      <th>구별</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>강남구</th>
      <td>3238</td>
      <td>150.619195</td>
      <td>561052</td>
      <td>556164</td>
      <td>4888</td>
      <td>65060</td>
      <td>0.871220</td>
      <td>11.596073</td>
      <td>0.577130</td>
    </tr>
    <tr>
      <th>강동구</th>
      <td>1010</td>
      <td>166.490765</td>
      <td>440359</td>
      <td>436223</td>
      <td>4136</td>
      <td>56161</td>
      <td>0.939234</td>
      <td>12.753458</td>
      <td>0.229358</td>
    </tr>
    <tr>
      <th>강북구</th>
      <td>831</td>
      <td>125.203252</td>
      <td>328002</td>
      <td>324479</td>
      <td>3523</td>
      <td>56530</td>
      <td>1.074079</td>
      <td>17.234651</td>
      <td>0.253352</td>
    </tr>
  </tbody>
</table>
</div>




```python
data_result['오차'] = data_result['소계'] - f1(data_result['인구수'])
```


```python
data_result.head(1)
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
      <th>소계</th>
      <th>최근증가율</th>
      <th>인구수</th>
      <th>한국인</th>
      <th>외국인</th>
      <th>고령자</th>
      <th>외국인비율</th>
      <th>고령자비율</th>
      <th>CCTV비율</th>
      <th>오차</th>
    </tr>
    <tr>
      <th>구별</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>강남구</th>
      <td>3238</td>
      <td>150.619195</td>
      <td>561052</td>
      <td>556164</td>
      <td>4888</td>
      <td>65060</td>
      <td>0.87122</td>
      <td>11.596073</td>
      <td>0.57713</td>
      <td>1524.595142</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 경향과 비교해서 데이터의 오차가 너무 나는 데이터를 계산

df_sort_f = data_result.sort_values(by='오차', ascending=False) #내림차순
df_sort_t = data_result.sort_values(by='오차', ascending=True) #오름차순
```


```python
# 경향 대비 CCTV를 많이 가진 구
df_sort_f.head()
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
      <th>소계</th>
      <th>최근증가율</th>
      <th>인구수</th>
      <th>한국인</th>
      <th>외국인</th>
      <th>고령자</th>
      <th>외국인비율</th>
      <th>고령자비율</th>
      <th>CCTV비율</th>
      <th>오차</th>
    </tr>
    <tr>
      <th>구별</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>강남구</th>
      <td>3238</td>
      <td>150.619195</td>
      <td>561052</td>
      <td>556164</td>
      <td>4888</td>
      <td>65060</td>
      <td>0.871220</td>
      <td>11.596073</td>
      <td>0.577130</td>
      <td>1524.595142</td>
    </tr>
    <tr>
      <th>양천구</th>
      <td>2482</td>
      <td>34.671731</td>
      <td>475018</td>
      <td>471154</td>
      <td>3864</td>
      <td>55234</td>
      <td>0.813443</td>
      <td>11.627770</td>
      <td>0.522507</td>
      <td>887.835545</td>
    </tr>
    <tr>
      <th>용산구</th>
      <td>2096</td>
      <td>53.216374</td>
      <td>244444</td>
      <td>229161</td>
      <td>15283</td>
      <td>36882</td>
      <td>6.252148</td>
      <td>15.088118</td>
      <td>0.857456</td>
      <td>821.403817</td>
    </tr>
    <tr>
      <th>서초구</th>
      <td>2297</td>
      <td>63.371266</td>
      <td>445401</td>
      <td>441102</td>
      <td>4299</td>
      <td>53205</td>
      <td>0.965198</td>
      <td>11.945415</td>
      <td>0.515715</td>
      <td>743.883771</td>
    </tr>
    <tr>
      <th>은평구</th>
      <td>2108</td>
      <td>85.237258</td>
      <td>491202</td>
      <td>486794</td>
      <td>4408</td>
      <td>74559</td>
      <td>0.897390</td>
      <td>15.178888</td>
      <td>0.429151</td>
      <td>491.405033</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 경향 대비 CCTV를 적게 가진 구
df_sort_t.head()
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
      <th>소계</th>
      <th>최근증가율</th>
      <th>인구수</th>
      <th>한국인</th>
      <th>외국인</th>
      <th>고령자</th>
      <th>외국인비율</th>
      <th>고령자비율</th>
      <th>CCTV비율</th>
      <th>오차</th>
    </tr>
    <tr>
      <th>구별</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>강서구</th>
      <td>911</td>
      <td>134.793814</td>
      <td>608255</td>
      <td>601691</td>
      <td>6564</td>
      <td>76032</td>
      <td>1.079153</td>
      <td>12.500021</td>
      <td>0.149773</td>
      <td>-867.826723</td>
    </tr>
    <tr>
      <th>송파구</th>
      <td>1081</td>
      <td>104.347826</td>
      <td>671173</td>
      <td>664496</td>
      <td>6677</td>
      <td>76582</td>
      <td>0.994825</td>
      <td>11.410173</td>
      <td>0.161061</td>
      <td>-785.029081</td>
    </tr>
    <tr>
      <th>중랑구</th>
      <td>916</td>
      <td>79.960707</td>
      <td>412780</td>
      <td>408226</td>
      <td>4554</td>
      <td>59262</td>
      <td>1.103251</td>
      <td>14.356800</td>
      <td>0.221910</td>
      <td>-591.904555</td>
    </tr>
    <tr>
      <th>도봉구</th>
      <td>825</td>
      <td>246.638655</td>
      <td>346234</td>
      <td>344166</td>
      <td>2068</td>
      <td>53488</td>
      <td>0.597284</td>
      <td>15.448512</td>
      <td>0.238278</td>
      <td>-590.673904</td>
    </tr>
    <tr>
      <th>광진구</th>
      <td>878</td>
      <td>53.228621</td>
      <td>372298</td>
      <td>357703</td>
      <td>14595</td>
      <td>43953</td>
      <td>3.920247</td>
      <td>11.805865</td>
      <td>0.235833</td>
      <td>-573.797784</td>
    </tr>
  </tbody>
</table>
</div>




```python
from matplotlib.colors import ListedColormap

# colormap 을 사용자 정의 (user define)로 세팅

color_step = ['#e74c3c', '#2ecc71', '#95a9a6', '#2ecc88', '#3498db', '#3498db']
my_cmap = ListedColormap(color_step)

```


```python
def drawGraph():
    
    plt.figure(figsize=(14,10))
    plt.scatter(data_result['인구수'], data_result['소계'], s=50, c=data_result['오차'], cmap=my_cmap )
    plt.plot(fx, f1(fx), ls='dashed', lw=3, color='g')
    
    for n in range(5):
        # 상위 5개
         plt.text(
             df_sort_f['인구수'][n]*1.02, # x 좌표
             df_sort_f['소계'][n]*0.98, # y 좌표
             df_sort_f.index[n],  # title
             fontsize=15
        )
        # 하위 5개
         plt.text(
             df_sort_t['인구수'][n]*1.02, # x 좌표
             df_sort_t['소계'][n]*0.98, # y 좌표
             df_sort_t.index[n],  # title
             fontsize=15
        )
    plt.xlabel('인구수')
    plt.ylabel("CCTV")
    plt.colorbar()
    plt.grid(True)
    plt.show()

drawGraph()
```


    
![png](output_225_0.png)
    



```python
df_sort_f.head()
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
      <th>소계</th>
      <th>최근증가율</th>
      <th>인구수</th>
      <th>한국인</th>
      <th>외국인</th>
      <th>고령자</th>
      <th>외국인비율</th>
      <th>고령자비율</th>
      <th>CCTV비율</th>
      <th>오차</th>
    </tr>
    <tr>
      <th>구별</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>강남구</th>
      <td>3238</td>
      <td>150.619195</td>
      <td>561052</td>
      <td>556164</td>
      <td>4888</td>
      <td>65060</td>
      <td>0.871220</td>
      <td>11.596073</td>
      <td>0.577130</td>
      <td>1524.595142</td>
    </tr>
    <tr>
      <th>양천구</th>
      <td>2482</td>
      <td>34.671731</td>
      <td>475018</td>
      <td>471154</td>
      <td>3864</td>
      <td>55234</td>
      <td>0.813443</td>
      <td>11.627770</td>
      <td>0.522507</td>
      <td>887.835545</td>
    </tr>
    <tr>
      <th>용산구</th>
      <td>2096</td>
      <td>53.216374</td>
      <td>244444</td>
      <td>229161</td>
      <td>15283</td>
      <td>36882</td>
      <td>6.252148</td>
      <td>15.088118</td>
      <td>0.857456</td>
      <td>821.403817</td>
    </tr>
    <tr>
      <th>서초구</th>
      <td>2297</td>
      <td>63.371266</td>
      <td>445401</td>
      <td>441102</td>
      <td>4299</td>
      <td>53205</td>
      <td>0.965198</td>
      <td>11.945415</td>
      <td>0.515715</td>
      <td>743.883771</td>
    </tr>
    <tr>
      <th>은평구</th>
      <td>2108</td>
      <td>85.237258</td>
      <td>491202</td>
      <td>486794</td>
      <td>4408</td>
      <td>74559</td>
      <td>0.897390</td>
      <td>15.178888</td>
      <td>0.429151</td>
      <td>491.405033</td>
    </tr>
  </tbody>
</table>
</div>




```python
data_result['인구수'][0]
```




    561052




```python
data_result['소계'][0]
```




    3238




```python
data_result.index[0]
```




    '강남구'




```python
data_result.to_csv("../solution/01. CCTV_result.csv", sep=",", encoding="utf-8")
```


```python

```
