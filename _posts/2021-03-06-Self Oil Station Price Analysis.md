---
layout: single
title:  Project 04. Self oil Station Price Anlysis
categories: Project_zb
---

# 04. Self Oil Station Price Analysis

## 1. 셀레니움 설치
- 윈도우, mac(intell)
    - conda install selenium
    - pip install selenium
- chromedriver


```python
pip install selenium
```

    Requirement already satisfied: selenium in c:\users\jcc96\anaconda3\envs\ds_study\lib\site-packages (4.1.2)
    Requirement already satisfied: urllib3[secure,socks]~=1.26 in c:\users\jcc96\anaconda3\envs\ds_study\lib\site-packages (from selenium) (1.26.8)
    Requirement already satisfied: trio-websocket~=0.9 in c:\users\jcc96\anaconda3\envs\ds_study\lib\site-packages (from selenium) (0.9.2)
    Requirement already satisfied: trio~=0.17 in c:\users\jcc96\anaconda3\envs\ds_study\lib\site-packages (from selenium) (0.20.0)
    Requirement already satisfied: outcome in c:\users\jcc96\anaconda3\envs\ds_study\lib\site-packages (from trio~=0.17->selenium) (1.1.0)
    Requirement already satisfied: attrs>=19.2.0 in c:\users\jcc96\anaconda3\envs\ds_study\lib\site-packages (from trio~=0.17->selenium) (21.4.0)
    Requirement already satisfied: sniffio in c:\users\jcc96\anaconda3\envs\ds_study\lib\site-packages (from trio~=0.17->selenium) (1.2.0)
    Requirement already satisfied: async-generator>=1.9 in c:\users\jcc96\anaconda3\envs\ds_study\lib\site-packages (from trio~=0.17->selenium) (1.10)
    Requirement already satisfied: cffi>=1.14 in c:\users\jcc96\anaconda3\envs\ds_study\lib\site-packages (from trio~=0.17->selenium) (1.15.0)
    Requirement already satisfied: sortedcontainers in c:\users\jcc96\anaconda3\envs\ds_study\lib\site-packages (from trio~=0.17->selenium) (2.4.0)
    Requirement already satisfied: idna in c:\users\jcc96\anaconda3\envs\ds_study\lib\site-packages (from trio~=0.17->selenium) (3.3)
    Requirement already satisfied: pycparser in c:\users\jcc96\anaconda3\envs\ds_study\lib\site-packages (from cffi>=1.14->trio~=0.17->selenium) (2.21)
    Requirement already satisfied: wsproto>=0.14 in c:\users\jcc96\anaconda3\envs\ds_study\lib\site-packages (from trio-websocket~=0.9->selenium) (1.1.0)
    Requirement already satisfied: PySocks!=1.5.7,<2.0,>=1.5.6 in c:\users\jcc96\anaconda3\envs\ds_study\lib\site-packages (from urllib3[secure,socks]~=1.26->selenium) (1.7.1)
    Requirement already satisfied: certifi in c:\users\jcc96\anaconda3\envs\ds_study\lib\site-packages (from urllib3[secure,socks]~=1.26->selenium) (2021.10.8)
    Requirement already satisfied: cryptography>=1.3.4 in c:\users\jcc96\anaconda3\envs\ds_study\lib\site-packages (from urllib3[secure,socks]~=1.26->selenium) (36.0.1)
    Requirement already satisfied: pyOpenSSL>=0.14 in c:\users\jcc96\anaconda3\envs\ds_study\lib\site-packages (from urllib3[secure,socks]~=1.26->selenium) (22.0.0)
    Requirement already satisfied: h11<1,>=0.9.0 in c:\users\jcc96\anaconda3\envs\ds_study\lib\site-packages (from wsproto>=0.14->trio-websocket~=0.9->selenium) (0.13.0)
    Note: you may need to restart the kernel to use updated packages.
    


```python
!pip list : grep sele
```

    Package              Version
    -------------------- ------------
    argon2-cffi          21.3.0
    argon2-cffi-bindings 21.2.0
    async-generator      1.10
    attrs                21.4.0
    backcall             0.2.0
    beautifulsoup4       4.10.0
    bleach               4.1.0
    Bottleneck           1.3.2
    branca               0.4.2
    brotlipy             0.7.0
    certifi              2021.10.8
    cffi                 1.15.0
    charset-normalizer   2.0.12
    colorama             0.4.4
    cryptography         36.0.1
    cycler               0.11.0
    debugpy              1.5.1
    decorator            5.1.1
    defusedxml           0.7.1
    entrypoints          0.3
    et-xmlfile           1.1.0
    folium               0.12.1.post1
    fonttools            4.25.0
    googlemaps           2.5.1
    h11                  0.13.0
    idna                 3.3
    importlib-metadata   4.8.2
    ipykernel            6.4.1
    ipython              7.31.1
    ipython-genutils     0.2.0
    ipywidgets           7.6.5
    jedi                 0.18.1
    Jinja2               3.0.2
    joblib               1.1.0
    jsonschema           3.2.0
    jupyter              1.0.0
    jupyter-client       7.1.2
    jupyter-console      6.4.0
    jupyter-core         4.9.1
    jupyterlab-pygments  0.1.2
    jupyterlab-widgets   1.0.0
    kiwisolver           1.3.2
    MarkupSafe           2.0.1
    matplotlib           3.5.0
    matplotlib-inline    0.1.2
    mistune              0.8.4
    mkl-fft              1.3.1
    mkl-random           1.2.2
    mkl-service          2.4.0
    munkres              1.1.4
    nbclient             0.5.11
    nbconvert            6.1.0
    nbformat             5.1.3
    nest-asyncio         1.5.1
    notebook             6.4.8
    numexpr              2.8.1
    numpy                1.21.5
    olefile              0.46
    openpyxl             3.0.9
    outcome              1.1.0
    packaging            21.3
    pandas               1.4.1
    pandocfilters        1.5.0
    parso                0.8.3
    pickleshare          0.7.5
    Pillow               8.4.0
    pip                  21.2.2
    prometheus-client    0.13.1
    prompt-toolkit       3.0.20
    pycparser            2.21
    Pygments             2.11.2
    pyOpenSSL            22.0.0
    pyparsing            3.0.4
    pyrsistent           0.18.0
    PySocks              1.7.1
    python-dateutil      2.8.2
    pytz                 2021.3
    pywin32              302
    pywinpty             2.0.2
    pyzmq                22.3.0
    qtconsole            5.2.2
    QtPy                 1.11.2
    requests             2.27.1
    scikit-learn         1.0.2
    scipy                1.7.3
    seaborn              0.11.2
    selenium             4.1.2
    Send2Trash           1.8.0
    setuptools           58.0.4
    sip                  4.19.13
    six                  1.16.0
    sniffio              1.2.0
    sortedcontainers     2.4.0
    soupsieve            2.3.1
    terminado            0.13.1
    testpath             0.5.0
    threadpoolctl        2.2.0
    tornado              6.1
    traitlets            5.1.1
    trio                 0.20.0
    trio-websocket       0.9.2
    typing-extensions    3.10.0.2
    urllib3              1.26.8
    wcwidth              0.2.5
    webencodings         0.5.1
    wheel                0.37.1
    widgetsnbextension   3.5.2
    win-inet-pton        1.1.0
    wincertstore         0.2
    wsproto              1.1.0
    xlrd                 2.0.1
    zipp                 3.7.0
    


```python
from selenium import webdriver
```


```python
driver = webdriver.Chrome('../driver/chromedriver.exe')
driver.get('https://www.naver.com')  # 네이버창 호출
```

    C:\Users\jcc96\AppData\Local\Temp/ipykernel_58012/1193016497.py:1: DeprecationWarning: executable_path has been deprecated, please pass in a Service object
      driver = webdriver.Chrome('../driver/chromedriver.exe')
    

## 2. 셀프 주유소가 정말 저렴하나요? - 데이터 확보하기 위한 작업
- https://www.opinet.co.kr/searRgSelect.do
- 사이트 구조 확인
- 목표 데이터
    - 브랜드
    - 가격
    - 셀프 주유 여부
    - 위치

## 3. 셀레니움으로 접근


```python
from selenium import webdriver
url = "https://www.opinet.co.kr/searRgSelect.do"
driver = webdriver.Chrome('../driver/chromedriver.exe')
driver.get(url)
```

    C:\Users\jcc96\AppData\Local\Temp/ipykernel_65764/1154099016.py:3: DeprecationWarning: executable_path has been deprecated, please pass in a Service object
      driver = webdriver.Chrome('../driver/chromedriver.exe')
    


```python
driver.get(url)  # 위에걸 실행하고 창을 켜놨을때는 작동하는데, 창을 끄고 하면 작동이 안됨. 왜지??
```

- 문제
    - 1. 해당 URL로 한 번에 접근이 안됩니다.
    - 2. 메인 페이지로 접속이 되고, 팝업창이 하나 나옵니다.


```python
# 팝업창으로 화면 전환 
driver.switch_to_window(driver.window_handles[-1]) # 팝업창이 안떠서 실행 안된듯
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    ~\AppData\Local\Temp/ipykernel_65764/1397624048.py in <module>
          1 # 팝업창 화면 전환 후 닫아주기
    ----> 2 driver.switch_to_window(driver.window_handles[-1]) # 팝업창이 안떠서 실행 안된듯
    

    AttributeError: 'WebDriver' object has no attribute 'switch_to_window'



```python
# 팝업창 닫아주기
driver.close()
```


```python
메인화면 창으로 전환
driver.switch_to_window(driver.window_handles[-1])
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    ~\AppData\Local\Temp/ipykernel_65764/3023539272.py in <module>
    ----> 1 driver.switch_to_window(driver.window_handles[-1])
    

    AttributeError: 'WebDriver' object has no attribute 'switch_to_window'



```python
# 접근 url 다시 요청
driver.get(url)
```


    ---------------------------------------------------------------------------

    InvalidSessionIdException                 Traceback (most recent call last)

    ~\AppData\Local\Temp/ipykernel_65764/4053521376.py in <module>
    ----> 1 driver.get(url)
    

    ~\anaconda3\envs\ds_study\lib\site-packages\selenium\webdriver\remote\webdriver.py in get(self, url)
        435         Loads a web page in the current browser session.
        436         """
    --> 437         self.execute(Command.GET, {'url': url})
        438 
        439     @property
    

    ~\anaconda3\envs\ds_study\lib\site-packages\selenium\webdriver\remote\webdriver.py in execute(self, driver_command, params)
        423         response = self.command_executor.execute(driver_command, params)
        424         if response:
    --> 425             self.error_handler.check_response(response)
        426             response['value'] = self._unwrap_value(
        427                 response.get('value', None))
    

    ~\anaconda3\envs\ds_study\lib\site-packages\selenium\webdriver\remote\errorhandler.py in check_response(self, response)
        245                 alert_text = value['alert'].get('text')
        246             raise exception_class(message, screen, stacktrace, alert_text)  # type: ignore[call-arg]  # mypy is not smart enough here
    --> 247         raise exception_class(message, screen, stacktrace)
        248 
        249     def _value_or_default(self, obj: Mapping[_KT, _VT], key: _KT, default: _VT) -> _VT:
    

    InvalidSessionIdException: Message: invalid session id
    Stacktrace:
    Backtrace:
    	Ordinal0 [0x012669A3+2582947]
    	Ordinal0 [0x011FA6D1+2139857]
    	Ordinal0 [0x010F3960+1063264]
    	Ordinal0 [0x01114BF0+1199088]
    	Ordinal0 [0x01138440+1344576]
    	Ordinal0 [0x01136358+1336152]
    	Ordinal0 [0x01135EF8+1335032]
    	Ordinal0 [0x010D5357+938839]
    	Ordinal0 [0x010D58D3+940243]
    	Ordinal0 [0x010D5C1A+941082]
    	GetHandleVerifier [0x0140BE02+1675858]
    	GetHandleVerifier [0x014C036C+2414524]
    	GetHandleVerifier [0x012FBB01+560977]
    	GetHandleVerifier [0x012FA8D3+556323]
    	Ordinal0 [0x0120020E+2163214]
    	Ordinal0 [0x010D50D5+938197]
    	Ordinal0 [0x010D4AA8+936616]
    	GetHandleVerifier [0x014E807C+2577612]
    	BaseThreadInitThunk [0x75CBFA29+25]
    	RtlGetAppContainerNamedObjectPath [0x77DF7A9E+286]
    	RtlGetAppContainerNamedObjectPath [0x77DF7A6E+238]
    



```python
import time
from selenium import webdriver

def main_get():
    url = "https://www.opinet.co.kr/searRgSelect.do"
    driver = webdriver.Chrome('../driver/chromedriver.exe')
    driver.get(url)

    time.sleep(3) # 3초 기다림
    driver.get(url)
    
```


```python
main_get() # 왜 멋대로 닫히는거지?
```

    C:\Users\jcc96\AppData\Local\Temp/ipykernel_65764/3960915183.py:6: DeprecationWarning: executable_path has been deprecated, please pass in a Service object
      driver = webdriver.Chrome('../driver/chromedriver.exe')
    


```python

url = "https://www.opinet.co.kr/searRgSelect.do"
driver = webdriver.Chrome('../driver/chromedriver.exe')
driver.get(url)

time.sleep(3) # 3초 기다림
driver.get(url)
```

    C:\Users\jcc96\AppData\Local\Temp/ipykernel_65764/797040737.py:2: DeprecationWarning: executable_path has been deprecated, please pass in a Service object
      driver = webdriver.Chrome('../driver/chromedriver.exe')
    


```python
# 지역: 시/도

sido_list_raw = driver.find_element_by_id('SIDO_NM0')
sido_list_raw.text
```

    C:\Users\jcc96\AppData\Local\Temp/ipykernel_65764/1433453196.py:3: DeprecationWarning: find_element_by_* commands are deprecated. Please use find_element() instead
      sido_list_raw = driver.find_element_by_id('SIDO_NM0')
    




    '            시/도\n            \n             \n              서울\n             \n             \n            \n             \n             \n              부산\n             \n            \n             \n             \n              대구\n             \n            \n             \n             \n              인천\n             \n            \n             \n             \n              광주\n             \n            \n             \n             \n              대전\n             \n            \n             \n             \n              울산\n             \n            \n             \n             \n              세종\n             \n            \n             \n             \n              경기\n             \n            \n             \n             \n              강원\n             \n            \n             \n             \n              충북\n             \n            \n             \n             \n              충남\n             \n            \n             \n             \n              전북\n             \n            \n             \n             \n              전남\n             \n            \n             \n             \n              경북\n             \n            \n             \n             \n              경남\n             \n            \n             \n             \n              제주\n             \n            \n           '




```python
len(sido_list_raw.find_elements_by_tag_name('option')) # 여러개를 고를려면 꼭 find_element 가 아닌 find_elements 를 써야한다!  /  길이 확인
sido_list = sido_list_raw.find_elements_by_tag_name('option')
len(sido_list), sido_list[1].text # 확인작업
```

    C:\Users\jcc96\anaconda3\envs\ds_study\lib\site-packages\selenium\webdriver\remote\webelement.py:359: UserWarning: find_elements_by_tag_name is deprecated. Please use find_elements(by=By.TAG_NAME, value=name) instead
      warnings.warn("find_elements_by_tag_name is deprecated. Please use find_elements(by=By.TAG_NAME, value=name) instead")
    




    (18, '서울')




```python
sido_list[1].get_attribute('value') # 속성값 가져오기
```




    '서울특별시'




```python
sido_names = []

for option in sido_list:
    sido_names.append(option.get_attribute('value'))

sido_names
```




    ['',
     '서울특별시',
     '부산광역시',
     '대구광역시',
     '인천광역시',
     '광주광역시',
     '대전광역시',
     '울산광역시',
     '세종특별자치시',
     '경기도',
     '강원도',
     '충청북도',
     '충청남도',
     '전라북도',
     '전라남도',
     '경상북도',
     '경상남도',
     '제주특별자치도']




```python
sido_names = [option.get_attribute('value') for option in sido_list] # 위에걸 한줄로 표현. 
sido_names[:5]
```




    ['', '서울특별시', '부산광역시', '대구광역시', '인천광역시']




```python
# 맨 앞에 빈칸을 제거
sido_names = sido_names[1:]
sido_names
```




    ['서울특별시',
     '부산광역시',
     '대구광역시',
     '인천광역시',
     '광주광역시',
     '대전광역시',
     '울산광역시',
     '세종특별자치시',
     '경기도',
     '강원도',
     '충청북도',
     '충청남도',
     '전라북도',
     '전라남도',
     '경상북도',
     '경상남도',
     '제주특별자치도']




```python
sido_names[0]
```




    '서울특별시'




```python
sido_list_raw.send_keys(sido_names[16]) # 17 번째 value 값인 제주도가 검색창에 들어감
```


```python
# 구

gu_list_raw = driver.find_element_by_id('SIGUNGU_NM0') # 부모 태그
gu_list = gu_list_raw.find_elements_by_tag_name('option') # 자식 태그

gu_names = [option.get_attribute('value') for option in gu_list]
gu_names
gu_names = gu_names[1:]
gu_names[:5], len(gu_names)
```

    C:\Users\jcc96\AppData\Local\Temp/ipykernel_65764/1985650961.py:3: DeprecationWarning: find_element_by_* commands are deprecated. Please use find_element() instead
      gu_list_raw = driver.find_element_by_id('SIGUNGU_NM0') # 부모 태그
    




    (['강남구', '강동구', '강북구', '강서구', '관악구'], 25)




```python
gu_list_raw.send_keys(gu_names[15])
```


```python
# 엑셀 저장

driver.find_element_by_css_selector('#glopopd_excel').click() # css 이용
```

    C:\Users\jcc96\AppData\Local\Temp/ipykernel_65764/1917593827.py:3: DeprecationWarning: find_element_by_css_selector is deprecated. Please use find_element(by=By.CSS_SELECTOR, value=css_selector) instead
      driver.find_element_by_css_selector('#glopopd_excel').click()
    


```python
driver.find_element_by_xpath('//*[@id="glopopd_excel"]/span').click() # xpath 이용
```

    C:\Users\jcc96\AppData\Local\Temp/ipykernel_65764/2882683663.py:1: DeprecationWarning: find_element_by_xpath is deprecated. Please use find_element(by=By.XPATH, value=xpath) instead
      driver.find_element_by_xpath('//*[@id="glopopd_excel"]/span').click()
    


```python
element_get_excel = driver.find_element_by_id('glopopd_excel')
element_get_excel.click()
```

    C:\Users\jcc96\AppData\Local\Temp/ipykernel_65764/3849016608.py:1: DeprecationWarning: find_element_by_* commands are deprecated. Please use find_element() instead
      element_get_excel = driver.find_element_by_id('glopopd_excel')
    


```python
pip install tqdm
```

    Collecting tqdm
      Downloading tqdm-4.63.0-py2.py3-none-any.whl (76 kB)
    Requirement already satisfied: colorama in c:\users\jcc96\anaconda3\envs\ds_study\lib\site-packages (from tqdm) (0.4.4)
    Installing collected packages: tqdm
    Successfully installed tqdm-4.63.0
    Note: you may need to restart the kernel to use updated packages.
    


```python
import time
from tqdm import tqdm_notebook # tqdm 이 깔려있지 않다고 오류가 떠서 위에서 다시 재설치하고 내려옴

for gu in tqdm_notebook(gu_names): # 반복문이 어디까지 진행됐는지 확인이 가능한 툴 tqdm
    element = driver.find_element_by_id('SIGUNGU_NM0')
    element.send_keys(gu)
    time.sleep(3)
    
    element_get_excel = driver.find_element_by_xpath('//*[@id="glopopd_excel"]/span')
    element_get_excel.click()
    time.sleep(3)
```

    C:\Users\jcc96\AppData\Local\Temp/ipykernel_65764/226032472.py:4: TqdmDeprecationWarning: This function will be removed in tqdm==5.0.0
    Please use `tqdm.notebook.tqdm` instead of `tqdm.tqdm_notebook`
      for gu in tqdm_notebook(gu_names): # 반복문이 어디까지 진행됐는지 확인이 가능한 툴 tqdm
    


      0%|          | 0/25 [00:00<?, ?it/s]


    C:\Users\jcc96\AppData\Local\Temp/ipykernel_65764/226032472.py:5: DeprecationWarning: find_element_by_* commands are deprecated. Please use find_element() instead
      element = driver.find_element_by_id('SIGUNGU_NM0')
    C:\Users\jcc96\AppData\Local\Temp/ipykernel_65764/226032472.py:9: DeprecationWarning: find_element_by_xpath is deprecated. Please use find_element(by=By.XPATH, value=xpath) instead
      element_get_excel = driver.find_element_by_xpath('//*[@id="glopopd_excel"]/span')
    


```python
# 다운로드 경로를 정해주고, 파일 이름을 각 시와 구 로 구분이 되게 rename 해서 저장해주면 좋을 것 같다.
```


```python
driver.close()
```

## 4. 데이터 정리하기


```python
import pandas as pd
from glob import glob
```


```python
# 파일 목록 한 번에 가져오기
glob('../data/지역_*.xls') # 지역_ 가 포함되어있는 엑셀파일 전부 호출

# 순서가 뒤죽박죽으로 읽는데 어떤식으로 읽어오는거지?
```




    ['../data\\지역_위치별(주유소) (1).xls',
     '../data\\지역_위치별(주유소) (10).xls',
     '../data\\지역_위치별(주유소) (11).xls',
     '../data\\지역_위치별(주유소) (12).xls',
     '../data\\지역_위치별(주유소) (13).xls',
     '../data\\지역_위치별(주유소) (14).xls',
     '../data\\지역_위치별(주유소) (15).xls',
     '../data\\지역_위치별(주유소) (16).xls',
     '../data\\지역_위치별(주유소) (17).xls',
     '../data\\지역_위치별(주유소) (18).xls',
     '../data\\지역_위치별(주유소) (19).xls',
     '../data\\지역_위치별(주유소) (2).xls',
     '../data\\지역_위치별(주유소) (20).xls',
     '../data\\지역_위치별(주유소) (21).xls',
     '../data\\지역_위치별(주유소) (22).xls',
     '../data\\지역_위치별(주유소) (23).xls',
     '../data\\지역_위치별(주유소) (24).xls',
     '../data\\지역_위치별(주유소) (3).xls',
     '../data\\지역_위치별(주유소) (4).xls',
     '../data\\지역_위치별(주유소) (5).xls',
     '../data\\지역_위치별(주유소) (6).xls',
     '../data\\지역_위치별(주유소) (7).xls',
     '../data\\지역_위치별(주유소) (8).xls',
     '../data\\지역_위치별(주유소) (9).xls',
     '../data\\지역_위치별(주유소).xls']




```python
# 파일명 저장
stations_files = glob('../data/지역_*.xls')
stations_files[:5]
```




    ['../data\\지역_위치별(주유소) (1).xls',
     '../data\\지역_위치별(주유소) (10).xls',
     '../data\\지역_위치별(주유소) (11).xls',
     '../data\\지역_위치별(주유소) (12).xls',
     '../data\\지역_위치별(주유소) (13).xls']




```python
# 하나만 읽어보기
tmp = pd.read_excel(stations_files[0], header=2) # 엑셀파일을 열어보면 1,2째 줄에 내용이 없으므로 haeder = 2를 통해 3번째 줄부터 불러와야한다.
tmp.tail(2)
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
      <th>지역</th>
      <th>상호</th>
      <th>주소</th>
      <th>상표</th>
      <th>전화번호</th>
      <th>셀프여부</th>
      <th>고급휘발유</th>
      <th>휘발유</th>
      <th>경유</th>
      <th>실내등유</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>12</th>
      <td>서울특별시</td>
      <td>(주)소모에너지 성내주유소</td>
      <td>서울 강동구 올림픽로 578 (성내동)</td>
      <td>GS칼텍스</td>
      <td>02-479-3838</td>
      <td>Y</td>
      <td>-</td>
      <td>1918</td>
      <td>1758</td>
      <td>-</td>
    </tr>
    <tr>
      <th>13</th>
      <td>서울특별시</td>
      <td>광성주유소</td>
      <td>서울 강동구 올림픽로 673 (천호동)</td>
      <td>S-OIL</td>
      <td>02-470-5133</td>
      <td>N</td>
      <td>-</td>
      <td>1978</td>
      <td>1798</td>
      <td>1450</td>
    </tr>
  </tbody>
</table>
</div>




```python
tmp_raw = []

for file_name in stations_files:
    tmp = pd.read_excel(file_name, header=2)
    tmp_raw.append(tmp)

tmp_raw
```




    [       지역                    상호                            주소      상표  \
     0   서울특별시  재건에너지 재정제2주유소 고속셀프지점  서울특별시 강동구  천호대로 1246 (둔촌제2동)  현대오일뱅크   
     1   서울특별시                구천면주유소         서울 강동구 구천면로 357 (암사동)  현대오일뱅크   
     2   서울특별시         지에스칼텍스㈜ 신월주유소        서울 강동구 양재대로 1323 (성내동)   GS칼텍스   
     3   서울특별시               방아다리주유소          서울 강동구 동남로 811 (명일동)   SK에너지   
     4   서울특별시        지에스칼텍스㈜ 동서울주유소        서울 강동구 천호대로 1456 (상일동)   GS칼텍스   
     5   서울특별시       (주)퍼스트오일 코알라주유소     서울특별시 강동구  올림픽로 556 (성내동)   S-OIL   
     6   서울특별시      주)지유에너지직영 오렌지주유소          서울 강동구 성안로 102 (성내동)   SK에너지   
     7   서울특별시              sk해뜨는주유소         서울 강동구  상일로 132 (강일동)   SK에너지   
     8   서울특별시          대성석유(주)길동주유소              서울 강동구 천호대로 1168   GS칼텍스   
     9   서울특별시     현대오일뱅크㈜직영 명일셀프주유소          서울 강동구 고덕로 168 (명일동)  현대오일뱅크   
     10  서울특별시        (주)삼표에너지 고덕주유소           서울 강동구 고덕로 39 (암사동)   GS칼텍스   
     11  서울특별시               천호현대주유소           서울 강동구 천중로 67 (천호동)  현대오일뱅크   
     12  서울특별시        (주)소모에너지 성내주유소         서울 강동구 올림픽로 578 (성내동)   GS칼텍스   
     13  서울특별시                 광성주유소         서울 강동구 올림픽로 673 (천호동)   S-OIL   
     
                 전화번호 셀프여부 고급휘발유   휘발유    경유  실내등유  
     0    02-487-2030    Y     -  1769  1599     -  
     1    02-441-0536    N     -  1793  1657     -  
     2    02-475-2600    N  1958  1808  1659  1345  
     3    02-442-5145    Y     -  1810  1650  1300  
     4    02-426-5372    Y     -  1815  1660     -  
     5    02-484-1162    Y     -  1818  1658     -  
     6    02-484-6165    N     -  1822  1652  1320  
     7    02-442-7801    Y     -  1823  1643  1350  
     8    02-474-7222    N  2014  1825  1699  1400  
     9   02-3428-1739    Y  2025  1833  1663     -  
     10   02-441-3327    N  2058  1857  1698  1473  
     11   02-484-9323    N     -  1894  1712     -  
     12   02-479-3838    Y     -  1918  1758     -  
     13   02-470-5133    N     -  1978  1798  1450  ,
            지역                상호                          주소      상표  \
     0   서울특별시             풍한주유소             서울 동대문구 안암로 168   SK에너지   
     1   서울특별시          동서울고속주유소             서울 동대문구 한천로 414   SK에너지   
     2   서울특별시             삼영주유소      서울 동대문구 답십리로 258 (장안동)   SK에너지   
     3   서울특별시    (주)자연에너지 국민주유소     서울 동대문구 답십리로 223 (답십리동)  현대오일뱅크   
     4   서울특별시       대성산업㈜청량리주유소      서울 동대문구 왕산로 289 (청량리동)   GS칼텍스   
     5   서울특별시           재정제2주유소       서울 동대문구 사가정로 90 (전농동)  현대오일뱅크   
     6   서울특별시             재정주유소       서울 동대문구 전농로 121 (전농동)  현대오일뱅크   
     7   서울특별시      동일석유(주)강남주유소  서울특별시 동대문구  사가정로 103 (전농동)   SK에너지   
     8   서울특별시     대성산업(주)동마장주유소      서울 동대문구 고산자로 405 (용두동)   GS칼텍스   
     9   서울특별시   삼미상사(주)장안킹셀프주유소      서울 동대문구  한천로 100 (장안동)   SK에너지   
     10  서울특별시          (주)경동주유소       서울 동대문구 이문로 191 (이문동)   S-OIL   
     11  서울특별시  현대오일뱅크㈜직영 스피드주유소      서울 동대문구 천호대로 453 (장안동)  현대오일뱅크   
     12  서울특별시             홍능주유소       서울 동대문구 홍릉로 87 (청량리동)   S-OIL   
     13  서울특별시           오동나무주유소      서울 동대문구  한천로 81 (답십리동)   S-OIL   
     14  서울특별시             열린주유소       서울 동대문구 한천로 263 (휘경동)   S-OIL   
     15  서울특별시  (주)안국에너지 삼원셀프주유소        서울 동대문구 망우로 90 (휘경동)   SK에너지   
     16  서울특별시            배봉로주유소          서울 동대문구 서울시립대로 108  현대오일뱅크   
     17  서울특별시          (주)파랑에너지             서울 동대문구 망우로 126   GS칼텍스   
     18  서울특별시        한영주유소 (한화)        서울 동대문구 망우로 38 (휘경동)  현대오일뱅크   
     
                  전화번호 셀프여부 고급휘발유   휘발유    경유  실내등유  
     0     02-924-5189    N     -  1745  1565     -  
     1     02-969-1144    Y  1899  1745  1565     -  
     2    02-2217-2017    N     -  1748  1573  1400  
     3    02-2216-7155    N     -  1750  1575     -  
     4     02-966-9400    Y     -  1755  1585     -  
     5    02-2249-6682    Y     -  1759  1579     -  
     6   070-8256-4617    Y  1939  1759  1579     -  
     7    02-3394-5183    N     -  1767  1587  1300  
     8     02-966-5451    Y  1958  1775  1595     -  
     9    02-2242-7115    Y     -  1779  1607     -  
     10    02-965-6006    Y     -  1785  1615  1300  
     11   02-2216-5151    N  1980  1795  1617     -  
     12    02-966-9190    N     -  1797  1639  1300  
     13   02-2247-5132    N     -  1798  1638  1400  
     14   02-2215-6543    N     -  1799  1599     -  
     15   02-2244-1972    Y     -  1809  1608  1310  
     16   02-2242-0556    Y     -  1825  1625     -  
     17   02-2242-5145    Y  1985  1825  1625  1250  
     18   02-2214-9890    N     -  1990  1890  1390  ,
           지역                   상호                      주소      상표         전화번호  \
     0  서울특별시      지에스칼텍스(주) 대방주유소        서울 동작구 여의대방로 214   GS칼텍스  02-826-5145   
     1  서울특별시   현대오일뱅크㈜직영 신대방셀프주유소  서울 동작구 시흥대로 616 (신대방동)  현대오일뱅크  02-832-7926   
     2  서울특별시             창원이엔지주유소     서울 동작구 사당로 59 (상도동)  현대오일뱅크  02-825-5151   
     3  서울특별시   현대오일뱅크㈜직영 흑석동셀프주유소    서울 동작구 현충로 101 (흑석동)  현대오일뱅크  02-815-0724   
     4  서울특별시  현대오일뱅크(주)직영 사당셀프주유소    서울 동작구 동작대로 73 (사당동)  현대오일뱅크  02-521-3618   
     5  서울특별시       대성산업(주) 노량진주유소         서울 동작구 노량진로 172   GS칼텍스  02-815-2354   
     6  서울특별시       (주)성림에너지 남성주유소   서울 동작구 동작대로 135 (사당동)   GS칼텍스  02-532-0606   
     7  서울특별시    현대오일뱅크(주)직영 동작주유소    서울 동작구 상도로 403 (상도동)  현대오일뱅크  02-817-9179   
     8  서울특별시                매일주유소    서울 동작구 상도로 139 (상도동)   S-OIL  02-817-4085   
     9  서울특별시               살피재주유소          서울 동작구 상도로 334   SK에너지  02-817-2559   
     
       셀프여부 고급휘발유   휘발유    경유  실내등유  
     0    N  1936  1756  1579  1200  
     1    Y  1979  1779  1609     -  
     2    N     -  1789  1629     -  
     3    Y  1955  1799  1637     -  
     4    Y  2069  1809  1648     -  
     5    N     -  1819  1619  1250  
     6    Y     -  1819  1667     -  
     7    N  1965  1829  1669     -  
     8    Y     -  1839  1659  1300  
     9    N     -  1935  1765     -  ,
            지역               상호                        주소      상표           전화번호  \
     0   서울특별시            청원주유소    서울 마포구 월드컵북로 113 (성산동)  현대오일뱅크    02-325-5533   
     1   서울특별시        성산대교셀프주유소            서울 마포구 성산로 144  현대오일뱅크    02-323-0078   
     2   서울특별시            성산주유소  서울 마포구 월드컵북로 170 (성산제2동)   SK에너지    02-373-3314   
     3   서울특별시          마포시엠주유소      서울 마포구 월드컵북로62 (성산동)   GS칼텍스    02-336-1687   
     4   서울특별시   에스오일(주) 염리동주유소      서울 마포구 백범로 126 (염리동)   S-OIL   02-3272-5155   
     5   서울특별시         에스에스오토셀프       서울 마포구 서강로 76 (창전동)  현대오일뱅크    02-336-5185   
     6   서울특별시  (주)안국에너지 망원동주유소     서울 마포구 월드컵로 119 (망원동)   SK에너지    02-334-0917   
     7   서울특별시            용강주유소            서울 마포구 토정로 258   S-OIL  070-7795-4800   
     8   서울특별시            대흥주유소       서울 마포구 대흥로 61 (대흥동)   SK에너지   02-3273-5151   
     9   서울특별시      SK에너지 양지주유소      서울 마포구 마포대로 69 (도화동)   SK에너지    02-706-8955   
     10  서울특별시   SK에너지(주) 안국주유소       서울 마포구 양화로 33 (합정동)   SK에너지   02-3144-1197   
     11  서울특별시            마포주유소     서울 마포구 마포대로 186 (공덕동)   S-OIL    02-701-3990   
     
        셀프여부 고급휘발유   휘발유    경유  실내등유  
     0     Y  2048  1759  1599     -  
     1     Y     -  1775  1599  1298  
     2     N     -  1777  1607     -  
     3     N     -  1797  1617     -  
     4     Y     -  1819  1679     -  
     5     Y  2119  1819  1679     -  
     6     N     -  1828  1628     -  
     7     N     -  1839  1699  1350  
     8     N  2218  1849  1709  1597  
     9     N  2059  1959  1819     -  
     10    N  2089  1989  1819     -  
     11    N     -  1989  1838  1567  ,
            지역                 상호                            주소      상표  \
     0   서울특별시      (주)창원이엔지 홍제지점         서울 서대문구 통일로 455 (홍제동)  현대오일뱅크   
     1   서울특별시  현대오일뱅크(주)직영 연세주유소               서울 서대문구 연희로 184  현대오일뱅크   
     2   서울특별시         구도일주유소 두꺼비               서울 서대문구 성산로 312   S-OIL   
     3   서울특별시    (주)미래아스팔트 신우주유소         서울 서대문구 가좌로 106 (홍은동)   S-OIL   
     4   서울특별시       (주)가재울뉴타운주유소              서울 서대문구 모래내로 205  현대오일뱅크   
     5   서울특별시              남정주유소       서울 서대문구 모래내로 243 (남가좌동)   GS칼텍스   
     6   서울특별시    지에스칼텍스(주)홍제동주유소               서울 서대문구 통일로 372   GS칼텍스   
     7   서울특별시   현대오일뱅크㈜직영 독립문주유소         서울 서대문구 통일로 384 (홍제동)  현대오일뱅크   
     8   서울특별시            행촌제2주유소         서울 서대문구 성산로 490 (대신동)   SK에너지   
     9   서울특별시        중앙에너비스 동교지점          서울 서대문구 연희로 12 (창천동)   SK에너지   
     10  서울특별시   (주)안국에너지 삼보셀프주유소          서울 서대문구 연희로 78 (연희동)   SK에너지   
     11  서울특별시       삼미상사(주)서부주유소               서울 서대문구 성산로 255   SK에너지   
     12  서울특별시              연희주유소  서울 서대문구 연희로 129 (연희동 89-7번지)   SK에너지   
     13  서울특별시            문화사랑주유소         서울 서대문구 세검정로 87 (홍제동)   S-OIL   
     14  서울특별시              광호주유소         서울 서대문구 연희로 266 (홍은동)   SK에너지   
     
                  전화번호 셀프여부 고급휘발유   휘발유    경유  실내등유  
     0     02-379-0753    N     -  1745  1579  1400  
     1     02-337-8220    Y  1975  1745  1579     -  
     2     02-336-0611    Y     -  1749  1589  1450  
     3     02-304-5522    Y     -  1762  1597     -  
     4   070-8879-7864    Y     -  1763  1603     -  
     5     02-305-9828    N     -  1768  1608  1390  
     6     02-736-3708    Y  1983  1788  1623     -  
     7     02-735-0333    N  1995  1788  1638     -  
     8     02-365-5189    N  1995  1795  1615     -  
     9   070-8707-4568    Y  1995  1795  1615     -  
     10    02-336-6151    Y  1978  1798  1619     -  
     11    02-334-4919    Y     -  1799  1625     -  
     12    02-338-8045    N  2019  1808  1638     -  
     13    02-395-4300    N     -  1809  1619  1300  
     14    02-395-7236    N     -  1818  1668     -  ,
            지역                    상호                          주소      상표  \
     0   서울특별시              만남의광장주유소        서울 서초구 양재대로12길 73-71  알뜰(ex)   
     1   서울특별시        극동유화(주) 전당앞주유소     서울 서초구 남부순환로 2391 (서초동)   S-OIL   
     2   서울특별시                신반포주유소        서울 서초구 사평대로 94 (반포동)   SK에너지   
     3   서울특별시    현대오일뱅크(주)직영 팔레스주유소       서울 서초구 사평대로 136 (반포동)  현대오일뱅크   
     4   서울특별시                 한독주유소        서울 서초구 방배로 218 (방배동)   GS칼텍스   
     5   서울특별시       대성산업(주)직영 강남주유소       서울 서초구 반포대로 284 (반포동)   GS칼텍스   
     6   서울특별시        지에스칼텍스(주)선천주유소       서울 서초구 동작대로 206 (방배동)   GS칼텍스   
     7   서울특별시                 양재주유소             서울 서초구 바우뫼로 178   SK에너지   
     8   서울특별시               태봉셀프주유소        서울 서초구 태봉로 117 (우면동)   SK에너지   
     9   서울특별시               반포그린주유소      서울 서초구 서초중앙로 239 (반포동)   GS칼텍스   
     10  서울특별시        에너지플러스허브 삼방주유소       서울 서초구 사평대로 364 (서초동)   GS칼텍스   
     11  서울특별시   현대오일뱅크(주)직영 방배현대주유소       서울 서초구 동작대로 182 (방배동)  현대오일뱅크   
     12  서울특별시   현대오일뱅크(주)직영 서초제일주유소       서울 서초구 사임당로 116 (서초동)  현대오일뱅크   
     13  서울특별시     에쓰오일(주)직영 오토테크주유소    서울특별시 서초구  효령로 356 (서초동)   S-OIL   
     14  서울특별시     현대오일뱅크㈜직영 양재현대주유소                서울 서초구 마방로 6  현대오일뱅크   
     15  서울특별시        (주)대농석유 남태령주유소       서울 서초구 과천대로 838 (방배동)   SK에너지   
     16  서울특별시         (주)한미석유 서초주유소        서울 서초구 반포대로 64 (서초동)   GS칼텍스   
     17  서울특별시              서초꽃마을주유소        서울 서초구 반포대로 69 (서초동)   GS칼텍스   
     18  서울특별시          대신석유(주)대우주유소       서울 서초구 양재대로 173 (양재동)   SK에너지   
     19  서울특별시          대성석유(주)연일주유소           서울 서초구 남부순환로 2451   GS칼텍스   
     20  서울특별시               말죽거리주유소     서울 서초구 남부순환로 2650 (양재동)   GS칼텍스   
     21  서울특별시              (주)홈런주유소  서울 서초구 양재대로2길 100-30 (우면동)   S-OIL   
     22  서울특별시  대성산업(주)직영 터미널(고속)주유소       서울 서초구 신반포로 222 (반포동)   GS칼텍스   
     23  서울특별시                방배동주유소         서울 서초구 효령로 29 (방배동)   SK에너지   
     24  서울특별시       지에스칼텍스(주)남서울주유소        서울 서초구 나루터로 83 (잠원동)   GS칼텍스   
     25  서울특별시       지에스칼텍스(주)헌릉로주유소        서울 서초구 헌릉로 177 (내곡동)   GS칼텍스   
     26  서울특별시        지에스칼텍스(주)내곡주유소              서울 서초구 헌릉로 210   GS칼텍스   
     27  서울특별시                크로바주유소        서울 서초구 효령로 327 (서초동)   SK에너지   
     28  서울특별시      현대오일뱅크㈜직영 사평로주유소       서울 서초구 사평대로 350 (서초동)  현대오일뱅크   
     29  서울특별시               양재최고주유소         서울 서초구 매헌로 72 (양재동)   S-OIL   
     30  서울특별시        (주)선문에너지 중앙주유소  서울특별시 서초구  바우뫼로 219 (양재1동)   S-OIL   
     31  서울특별시            대신석유㈜서원주유소       서울 서초구 반포대로 142 (서초동)   SK에너지   
     32  서울특별시               선우상사Q엔느         서울 서초구 방배로 66 (방배동)   SK에너지   
     
                 전화번호 셀프여부 고급휘발유   휘발유    경유  실내등유  
     0    02-573-7430    Y     -  1714  1581     -  
     1   02-6080-0516    Y  1924  1783  1633     -  
     2    02-533-5151    N  1938  1783  1618  1200  
     3    02-720-0020    N  1945  1785  1623     -  
     4   02-3477-6127    N  1945  1785  1623     -  
     5    02-594-5987    Y  1925  1785  1623     -  
     6    02-592-4915    N  1946  1791  1634     -  
     7    02-577-1621    N  1968  1797  1659     -  
     8    02-571-8000    Y     -  1797  1645     -  
     9    02-532-5147    N  1961  1798  1645     -  
     10   02-536-5145    Y  1961  1798  1635     -  
     11   02-534-0051    N  1955  1809  1648  1230  
     12   02-587-6080    N  1995  1809  1658     -  
     13   02-585-5189    Y  1959  1809  1649     -  
     14   02-579-8429    N  1968  1813  1663  1350  
     15   02-587-0895    Y     -  1815  1655     -  
     16   02-582-5198    N  1976  1815  1665     -  
     17   02-523-5551    N  1979  1818  1668     -  
     18   02-572-0567    Y     -  1819  1677     -  
     19  02-3471-5151    N  1994  1825  1675  1450  
     20   02-579-9933    N     -  1825  1675  1485  
     21   02-577-5151    Y     -  1828  1678     -  
     22   02-535-3001    N  1951  1829  1699  1250  
     23   02-584-2086    N     -  1848  1687     -  
     24   02-542-1517    N  2016  1861  1712  1540  
     25   02-574-0828    Y  2018  1863  1726  1548  
     26   02-573-7878    N  2018  1863  1726  1503  
     27   02-586-8100    N  2334  1898  1698     -  
     28  02-3481-2513    N  2140  1929  1811     -  
     29  02-2057-5189    N     -  1995  1795     -  
     30   02-575-5110    N  2268  2049  1898  1480  
     31   02-599-3657    N  2198  2098  1938     -  
     32   02-581-5101    N  2598  2317  2118     -  ,
            지역                 상호                       주소      상표          전화번호  \
     0   서울특별시        (주)서울에너지 직영    서울 성동구 천호대로 324 (용답동)   S-OIL  02-3390-4338   
     1   서울특별시              정호주유소    서울 성동구 고산자로 307 (마장동)    자가상표  02-2297-9442   
     2   서울특별시  현대오일뱅크(주) 성동셀프주유소     서울 성동구 마장로 311 (마장동)  현대오일뱅크  02-2299-7333   
     3   서울특별시           KLP제2주유소     서울 성동구 동일로 249 (송정동)  현대오일뱅크   02-465-5182   
     4   서울특별시     지에스칼텍스㈜ 도루코주유소          서울 성동구 아차산로 180   GS칼텍스   02-463-6919   
     5   서울특별시             아이콘주유소    서울 성동구 고산자로 273 (도선동)   S-OIL  02-2291-5189   
     6   서울특별시    현대오일뱅크㈜직영 효진주유소           서울 성동구 동일로 129  현대오일뱅크   02-464-7252   
     7   서울특별시    SK에너지(주) 군자동주유소    서울 성동구 천호대로 446 (용답동)   SK에너지  02-2244-4945   
     8   서울특별시    kh에너지(주)성수만세주유소          서울 성동구 왕십리로 109   SK에너지   02-499-8223   
     9   서울특별시              경진주유소    서울 성동구 고산자로 348 (마장동)   SK에너지  02-2295-3331   
     10  서울특별시              삼우주유소          서울 성동구 천호대로 392   SK에너지  02-2245-8974   
     11  서울특별시     SK에너지(주) 성수주유소   서울 성동구 뚝섬로 352 (성수동1가)   SK에너지   02-467-7240   
     12  서울특별시           SK세원2주유소  서울 성동구 광나루로 184 (성수동1가)   SK에너지   02-462-5665   
     13  서울특별시              금호주유소    서울 성동구 금호로 39 (금호동4가)   GS칼텍스  02-2297-0066   
     14  서울특별시             청계로주유소  서울 성동구 청계천로 454 (하왕십리동)   SK에너지  02-2294-4225   
     15  서울특별시              동일주유소  서울 성동구 광나루로 254 (성수동2가)  현대오일뱅크   02-461-7100   
     16  서울특별시      (주)옥수하이웨이스테이션    서울 성동구 독서당로 168 (옥수동)   GS칼텍스  02-2282-5151   
     
        셀프여부 고급휘발유   휘발유    경유  실내등유  
     0     Y     -  1749  1579     -  
     1     N     -  1765  1585     -  
     2     Y  2024  1788  1618     -  
     3     Y     -  1799  1612     -  
     4     Y  1981  1801  1604  1305  
     5     N     -  1828  1658  1350  
     6     N  1984  1837  1638  1218  
     7     N  1979  1839  1669     -  
     8     Y  1995  1848  1657     -  
     9     N     -  1858  1658  1500  
     10    N     -  1858  1658     -  
     11    N  1999  1889  1699     -  
     12    N  2230  1898  1770     -  
     13    N  2232  1995  1794  1470  
     14    N     -  1998  1847  1445  
     15    N  2286  2045  1877  1397  
     16    N  2350  2090  1895     -  ,
            지역                 상호                         주소      상표  \
     0   서울특별시              원천주유소      서울 성북구 돌곶이로 142 (장위동)   알뜰주유소   
     1   서울특별시    지에스칼텍스(주) 종암주유소       서울 성북구 종암로 145 (종암동)   GS칼텍스   
     2   서울특별시     (주)삼표에너지 정릉주유소       서울 성북구 보국문로 35 (정릉동)   GS칼텍스   
     3   서울특별시        중앙에너비스 종암지점              서울 성북구 종암로 58   SK에너지   
     4   서울특별시           (주)성북주유소             서울 성북구 보문로 142  현대오일뱅크   
     5   서울특별시   SK에너지(주) 드림랜드주유소       서울 성북구 월계로 128 (장위동)   SK에너지   
     6   서울특별시    현대오일뱅크㈜직영 장삼주유소       서울 성북구 한천로 612 (장위동)  현대오일뱅크   
     7   서울특별시  이케이에너지(주) 강산제2주유소             서울 성북구 보국문로 52  현대오일뱅크   
     8   서울특별시  현대오일뱅크㈜직영 북악셀프주유소       서울 성북구 정릉로 218 (정릉동)  현대오일뱅크   
     9   서울특별시      이케이에너지㈜ 강산주유소      서울 성북구 보문로 27 (보문동7가)   GS칼텍스   
     10  서울특별시  현대오일뱅크㈜직영 광덕셀프주유소      서울 성북구 보문로 89 (보문동5가)  현대오일뱅크   
     11  서울특별시       재정제2주유소 길음지점        서울 성북구 삼양로 78 (길음동)  현대오일뱅크   
     12  서울특별시              장위주유소      서울 성북구 화랑로 110 (하월곡동)   S-OIL   
     13  서울특별시  현대오일뱅크㈜직영 고대셀프주유소        서울 성북구 종암로 12 (종암동)  현대오일뱅크   
     14  서울특별시             신동방주유소        서울 성북구 월계로 84 (장위동)   S-OIL   
     15  서울특별시              우리주유소             서울 성북구 화랑로 292   SK에너지   
     16  서울특별시    (주)신용 구도일주유소화랑로             서울 성북구 화랑로 174   S-OIL   
     17  서울특별시   현대오일뱅크㈜직영 아리랑주유소       서울 성북구 아리랑로 96 (정릉동)  현대오일뱅크   
     18  서울특별시      지에스칼텍스㈜ 화랑주유소             서울 성북구 화랑로 185   GS칼텍스   
     19  서울특별시              삼선주유소            서울 성북구 창경궁로 324   S-OIL   
     20  서울특별시       ㈜명연에너지 효성주유소              서울 성북구 화랑로 27   GS칼텍스   
     21  서울특별시              신방주유소     서울 성북구 안암로 111 (안암동5가)   S-OIL   
     22  서울특별시              동일주유소  서울특별시 성북구  보문로 85 (보문동5가)   GS칼텍스   
     23  서울특별시      지에스칼텍스㈜ 세창주유소            서울 성북구 동소문로 323   GS칼텍스   
     
                  전화번호 셀프여부 고급휘발유   휘발유    경유  실내등유  
     0   070-4063-1057    N     -  1739  1564     -  
     1     02-921-7785    Y  1951  1752  1595     -  
     2     02-914-6556    Y  1939  1755  1575  1200  
     3   070-8707-4565    Y     -  1755  1585     -  
     4     02-928-4900    Y     -  1755  1585     -  
     5     02-916-9906    N  1933  1759  1579  1200  
     6     02-909-0314    Y  1998  1765  1595  1289  
     7     02-942-1448    Y  1939  1765  1585     -  
     8     02-911-5189    Y  2115  1765  1585     -  
     9     02-953-1448    Y     -  1765  1585  1200  
     10    02-923-5545    Y  1993  1767  1597     -  
     11    02-980-1311    N     -  1769  1599  1200  
     12   02-6498-5189    Y     -  1775  1605     -  
     13    02-912-5151    Y  1995  1775  1595     -  
     14    02-918-5151    Y  2007  1775  1605     -  
     15    02-969-5185    Y     -  1777  1617     -  
     16    02-963-0051    Y     -  1783  1613     -  
     17    02-941-5189    N  1999  1793  1628  1293  
     18    02-942-5152    N     -  1819  1645  1290  
     19    02-766-5105    Y  2105  1827  1627     -  
     20    02-942-5150    N  2119  1829  1697  1249  
     21    02-922-5151    N     -  1829  1649     -  
     22    02-923-8484    N     -  1859  1677  1549  
     23    02-988-2491    Y  2047  1872  1713  1249  ,
            지역                  상호                        주소      상표          전화번호  \
     0   서울특별시              아시아주유소      서울 송파구 도곡로 438 (잠실동)   GS칼텍스   02-416-1911   
     1   서울특별시   현대오일뱅크㈜직영 잠실셀프주유소     서울 송파구 송파대로 397 (석촌동)  현대오일뱅크   02-417-7111   
     2   서울특별시               삼화주유소          서울 송파구 백제고분로 125   GS칼텍스  02-2203-2280   
     3   서울특별시            백제고분로주유소      서울 송파구 오금로 143 (방이동)   SK에너지  02-2202-4050   
     4   서울특별시              남성대주유소      서울 송파구 송파대로 52 (장지동)   SK에너지   02-409-2211   
     5   서울특별시            (주)잠실에너지     서울 송파구 송파대로 442 (송파동)   S-OIL   02-414-5010   
     6   서울특별시             위례드림주유소         서울시 송파구  위례중앙로 10   S-OIL   02-404-5189   
     7   서울특별시   지에스이앤알 직영 송파제일주유소      서울 송파구 삼학사로 50 (석촌동)  현대오일뱅크   02-424-2900   
     8   서울특별시       (주)신화에너지 서울지점       서울 송파구 가락로 47 (석촌동)   SK에너지  02-2202-8484   
     9   서울특별시             삼전셀프주유소          서울 송파구 백제고분로 199   SK에너지   02-420-5101   
     10  서울특별시   지에스칼텍스(주)스마트위례주유소     서울 송파구 위례중앙로 43 (장지동)   GS칼텍스   02-409-5185   
     11  서울특별시   지에스칼텍스(주)가든파이브주유소           서울 송파구 탄천동로 740   GS칼텍스   02-409-5145   
     12  서울특별시             위례제일주유소           서울 송파구 위례서로 260   S-OIL   02-408-9951   
     13  서울특별시               방이주유소  서울 송파구 위례성대로12길 38 (방이동)   SK에너지   02-424-3051   
     14  서울특별시               상아주유소             서울 송파구 거마로 82   S-OIL   02-409-8251   
     15  서울특별시     (주)삼표에너지 훼미리주유소       서울 송파구 중대로 58 (문정동)   GS칼텍스   02-448-9252   
     16  서울특별시  현대오일뱅크㈜직영 올림픽셀프주유소    서울 송파구 위례성대로 188 (오금동)  현대오일뱅크   02-448-9804   
     17  서울특별시           제트라인DM주유소      서울 송파구 중대로 183 (가락동)  현대오일뱅크   02-430-5151   
     18  서울특별시      (주)삼표에너지 우리주유소            서울 송파구 동남로 153   GS칼텍스  02-3401-1588   
     19  서울특별시               완불주유소       서울 송파구 송파대로 3 (장지동)   SK에너지  02-3402-2900   
     20  서울특별시               대성주유소      서울 송파구 마천로 230 (마천동)   SK에너지   02-431-1991   
     21  서울특별시            (주)유진주유소      서울 송파구 동남로 325 (오금동)   SK에너지   02-406-3956   
     22  서울특별시       (주)남경석유 세영주유소            서울 송파구 동남로 298   GS칼텍스   02-406-7778   
     23  서울특별시           (주)정직한주유소      서울 송파구 오금로 455 (거여동)  현대오일뱅크   02-406-4634   
     24  서울특별시     현대오일뱅크㈜직영 서원주유소      서울 송파구 중대로 154 (가락동)  현대오일뱅크   02-402-5929   
     25  서울특별시               송파주유소       서울 송파구 송이로 28 (송파동)   GS칼텍스  02-2203-3737   
     26  서울특별시   현대오일뱅크㈜직영 거여셀프주유소        서울 송파구 거마로 5 (거여동)  현대오일뱅크   02-409-9836   
     27  서울특별시       (주)퍼스트오일서울주유소            서울 송파구 문정로 153   S-OIL   02-407-0708   
     28  서울특별시        대성석유(주)석촌주유소          서울 송파구 백제고분로 289   GS칼텍스   02-421-0051   
     29  서울특별시      한강에너지(주)퍼스트주유소      서울 송파구 삼학사로 22 (석촌동)   SK에너지   02-422-2834   
     30  서울특별시      (주)뉴명성산업 남성주유소    서울 송파구 백제고분로 474 (방이동)  현대오일뱅크   02-423-5128   
     31  서울특별시        대신석유(주)진양주유소     서울 송파구 올림픽로 499 (풍납동)   SK에너지   02-477-1906   
     
        셀프여부 고급휘발유   휘발유    경유  실내등유  
     0     Y  1885  1755  1575     -  
     1     Y  1905  1760  1585  1240  
     2     Y  1885  1763  1583     -  
     3     Y  1872  1763  1583     -  
     4     Y     -  1763  1574     -  
     5     Y  1872  1763  1589     -  
     6     Y  1874  1773  1584     -  
     7     Y     -  1775  1615     -  
     8     Y     -  1775  1635  1350  
     9     Y  1910  1783  1597     -  
     10    Y  1894  1783  1599     -  
     11    Y  1894  1783  1599     -  
     12    Y     -  1783  1594     -  
     13    N     -  1783  1597     -  
     14    Y     -  1783  1594  1250  
     15    N  1968  1788  1608  1380  
     16    Y  1931  1793  1614     -  
     17    N     -  1793  1614     -  
     18    N  1965  1795  1615  1350  
     19    Y  1945  1796  1595     -  
     20    N     -  1798  1598  1298  
     21    N     -  1799  1599     -  
     22    N     -  1799  1599     -  
     23    Y     -  1808  1648     -  
     24    N  1989  1814  1682  1325  
     25    Y     -  1817  1657  1300  
     26    Y  1951  1818  1658     -  
     27    N     -  1818  1658  1300  
     28    N  2017  1827  1697  1450  
     29    Y  2005  1835  1685     -  
     30    N     -  1879  1699     -  
     31    N  2098  1998  1838     -  ,
            지역                     상호                      주소      상표  \
     0   서울특별시         (주)타이거오일 신정주유소    서울 양천구 중앙로 226 (신정동)   SK에너지   
     1   서울특별시                  현대주유소  서울 양천구 남부순환로 372 (신월동)   S-OIL   
     2   서울특별시                가로공원주유소  서울 양천구 가로공원로 165 (신월동)   SK에너지   
     3   서울특별시                 양천구주유소    서울 양천구 국회대로 275 (목동)   알뜰주유소   
     4   서울특별시          지에스칼텍스㈜ 건지주유소   서울 양천구 안양천로 1171 (목동)   GS칼텍스   
     5   서울특별시  현대오일뱅크(주)직영 양천현대셀프주유소   서울 양천구 안양천로 1179 (목동)  현대오일뱅크   
     6   서울특별시             개나리Self주유소  서울 양천구 남부순환로 442 (신월동)   SK에너지   
     7   서울특별시            형산석유(주)원주유소        서울 양천구 남부순환로 408  현대오일뱅크   
     8   서울특별시         (주)삼표에너지 목동주유소    서울 양천구 목동서로 129 (목동)   GS칼텍스   
     9   서울특별시    현대오일뱅크(주)직영 양천셀프주유소           서울 양천구 목동로 17  현대오일뱅크   
     10  서울특별시       삼미상사(주)신월IC셀프주유소    서울 양천구 중앙로 331 (신월동)   SK에너지   
     11  서울특별시        지에스이앤알 직영 서울주유소    서울 양천구 신정로 236 (신정동)   GS칼텍스   
     12  서울특별시          지에스칼텍스㈜ 서호주유소        서울 양천구 남부순환로 317   GS칼텍스   
     13  서울특별시  현대오일뱅크(주)직영 남부순환셀프주유소  서울 양천구 남부순환로 553 (신월동)  현대오일뱅크   
     14  서울특별시                  목동주유소   서울 양천구 목동중앙로 125 (목동)   SK에너지   
     15  서울특별시      현대오일뱅크㈜직영 목동셀프주유소    서울 양천구 공항대로 648 (목동)  현대오일뱅크   
     16  서울특별시                 신정동주유소   서울 양천구 안양천로 663 (신정동)  현대오일뱅크   
     17  서울특별시         SK에너지(주) 경인주유소   서울 양천구 국회대로 170 (신정동)   SK에너지   
     18  서울특별시                  신월주유소    서울 양천구 신월로 193 (신월동)   GS칼텍스   
     19  서울특별시   현대오일뱅크(주)직영 신목동셀프주유소       서울 양천구 목동동로10길 13  현대오일뱅크   
     20  서울특별시                  양정주유소   서울 양천구 국회대로 158 (신정동)  현대오일뱅크   
     21  서울특별시             (주)서부트럭터미날    서울 양천구 신정로 167 (신정동)  현대오일뱅크   
     22  서울특별시            SK에너지(주) 신평    서울 양천구 목동남로 62 (신정동)   SK에너지   
     23  서울특별시                  신양주유소           서울 양천구 지양로 67   SK에너지   
     24  서울특별시                  평화주유소   서울 양천구 안양천로 657 (신정동)   SK에너지   
     
                 전화번호 셀프여부 고급휘발유   휘발유    경유  실내등유  
     0   02-2646-6212    Y     -  1714  1569     -  
     1   02-2608-9231    Y     -  1714  1568     -  
     2   02-2695-3423    N     -  1718  1568     -  
     3   02-2644-5105    Y     -  1725  1575     -  
     4   02-2644-5108    Y  1934  1726  1584  1150  
     5   02-2653-5189    Y  1934  1726  1584     -  
     6   02-2606-5189    Y     -  1729  1579     -  
     7   02-2690-5837    N     -  1729  1579  1290  
     8   02-2654-5153    Y  1940  1739  1589     -  
     9   02-2644-5185    Y  1984  1744  1582     -  
     10  02-2694-4966    Y     -  1749  1595     -  
     11  02-2607-9478    N     -  1755  1595     -  
     12  02-2602-5172    Y  1969  1755  1608  1310  
     13  02-2690-5001    Y  2030  1769  1638     -  
     14  02-2645-5104    Y     -  1778  1618     -  
     15  02-2648-4204    Y     -  1779  1619     -  
     16  02-2651-5189    Y     -  1787  1617     -  
     17  02-2693-4994    Y     -  1789  1629  1298  
     18  02-2603-5182    Y     -  1798  1618  1300  
     19  02-2642-5188    Y  2020  1798  1647     -  
     20  02-2691-5185    N     -  1798  1658     -  
     21  02-2614-0047    N     -  1799  1649  1250  
     22  02-2654-5145    N  1939  1819  1679  1150  
     23  02-2608-3312    N     -  1844  1664  1399  
     24  02-2647-2122    N  2187  1987  1797     -  ,
            지역                 상호                             주소      상표  \
     0   서울특별시              성락주유소         서울 영등포구 가마산로 414 (신길동)   S-OIL   
     1   서울특별시      지에스칼텍스㈜ 신길주유소           서울 영등포구 신길로 74 (신길동)   GS칼텍스   
     2   서울특별시              도림주유소          서울 영등포구 도림로 343 (도림동)   알뜰주유소   
     3   서울특별시         영등포제일셀프주유소               서울 영등포구 가마산로 379  현대오일뱅크   
     4   서울특별시           (주)MS에너지                서울 영등포구 대림로 230  현대오일뱅크   
     5   서울특별시           남서울고속주유소         서울 영등포구 가마산로 367 (대림동)   SK에너지   
     6   서울특별시             선유도주유소        서울 영등포구 양평로 141 (양평동5가)   S-OIL   
     7   서울특별시     (주)대청에너지 대청주유소         서울 영등포구 가마산로 328 (대림동)   GS칼텍스   
     8   서울특별시       한경석유(주)경덕주유소       서울 영등포구 여의대방로23길 2 (신길동)   SK에너지   
     9   서울특별시            (주)강서오일                서울 영등포구 도신로 151  현대오일뱅크   
     10  서울특별시       씨앤에스유통 한성주유소              서울 영등포구 여의대방로 227   S-OIL   
     11  서울특별시              매봉주유소          서울 영등포구 도신로 248 (신길동)  현대오일뱅크   
     12  서울특별시     ㈜지에스이앤알 모드니주유소                서울 영등포구 경인로 789   GS칼텍스   
     13  서울특별시    (주)지에스이앤알 보라주유소         서울 영등포구 영등포로 399 (신길동)   GS칼텍스   
     14  서울특별시              행촌주유소          서울 영등포구 도신로 130 (신길동)   SK에너지   
     15  서울특별시         영등포현대셀프주유소         서울 영등포구 경인로 822 (영등포동)  현대오일뱅크   
     16  서울특별시    (주)한미석유 제2한강주유소        서울 영등포구 선유로 260 (양평동4가)   GS칼텍스   
     17  서울특별시  현대오일뱅크㈜직영 대일셀프주유소               서울 영등포구 영등포로 168  현대오일뱅크   
     18  서울특별시     SK에너지(주) 양평주유소        서울 영등포구 선유로 195 (양평동3가)   SK에너지   
     19  서울특별시    SK에너지(주) 신길동주유소         서울 영등포구 영등포로 348 (신길동)   SK에너지   
     20  서울특별시     SK에너지(주) 기린주유소                서울 영등포구 선유로 270   SK에너지   
     21  서울특별시     성원이앤에스(주)영등포지점  서울 영등포구 국회대로52길 9-13 (영등포동7가)   GS칼텍스   
     22  서울특별시              한일주유소        서울 영등포구 도림로 486 (문래동3가)   SK에너지   
     23  서울특별시           버드나룻길주유소        서울 영등포구 버드나루로 111 (당산동)   SK에너지   
     24  서울특별시     SJ오일(주) 여의도주유소                 서울 영등포구 은행로 64   GS칼텍스   
     25  서울특별시  지에스칼텍스(주) 국회대로주유소        서울 영등포구 국회대로 746 (여의도동)   GS칼텍스   
     26  서울특별시           KH여의도주유소        서울 영등포구 국회대로 794 (여의도동)   SK에너지   
     27  서울특별시      지에스칼텍스㈜ 화일주유소                서울 영등포구 도림로 415   GS칼텍스   
     
                  전화번호 셀프여부 고급휘발유   휘발유    경유  실내등유  
     0     02-842-6148    Y     -  1728  1588     -  
     1     02-833-1113    Y  1989  1754  1587  1199  
     2     02-835-8881    Y     -  1757  1587     -  
     3     02-847-5151    Y     -  1758  1588     -  
     4     02-844-5151    N     -  1767  1597     -  
     5     02-843-5151    Y     -  1768  1598     -  
     6    02-2671-5223    Y     -  1775  1635     -  
     7     02-841-8780    Y     -  1778  1608     -  
     8     02-843-3900    Y  1894  1778  1598     -  
     9     02-832-1700    N     -  1778  1608  1246  
     10    02-849-5180    N     -  1783  1613  1200  
     11    02-836-8851    Y     -  1785  1605  1300  
     12   02-2637-7788    N     -  1785  1615     -  
     13    02-842-1155    N  1889  1785  1605     -  
     14  070-7758-5189    N     -  1787  1615     -  
     15   02-2678-0503    Y     -  1788  1588     -  
     16   02-2633-2716    Y     -  1795  1655     -  
     17   02-2068-8700    Y  1945  1799  1638  1259  
     18   02-2633-1013    Y     -  1825  1685     -  
     19    02-843-0481    N  1925  1825  1645  1173  
     20   02-2671-5182    Y  1955  1845  1705     -  
     21   02-2635-7781    N  2170  1965  1795  1300  
     22   02-2679-1794    N     -  1985  1795  1450  
     23   02-2634-5104    N  2190  2090  1870  1440  
     24    02-785-8201    N  2265  2095  1948  1450  
     25    02-761-5122    N  2265  2095  1948     -  
     26    02-761-5101    N  2195  2095  1948     -  
     27   02-2633-5546    Y     -     -     -     -  ,
            지역                   상호                     주소      상표         전화번호  \
     0   서울특별시     씨앤에스에너지㈜ 미아셀프주유소   서울 강북구 도봉로 200 (미아동)   S-OIL  02-945-7999   
     1   서울특별시               덕릉로주유소    서울 강북구 덕릉로 158 (번동)   S-OIL  02-989-9806   
     2   서울특별시  현대오일뱅크(주)직영 번동셀프주유소    서울 강북구 한천로 963 (번동)  현대오일뱅크  02-992-3331   
     3   서울특별시             (주)석산에너지   서울 강북구 삼양로 316 (수유동)  현대오일뱅크  02-980-1448   
     4   서울특별시             북서울고속주유소   서울 강북구 삼양로 410 (수유동)   S-OIL  02-907-5182   
     5   서울특별시       (주)서울에너지 시민주유소  서울 강북구 인수봉로 185 (수유동)  현대오일뱅크  02-907-9496   
     6   서울특별시               수유동주유소   서울 강북구 도봉로 395 (수유동)   GS칼텍스  02-902-9470   
     7   서울특별시        ㈜지에스이앤알 미아주유소   서울 강북구 도봉로 122 (미아동)   GS칼텍스  02-987-5152   
     8   서울특별시    현대오일뱅크㈜직영 새한셀프주유소          서울 강북구 도봉로 75  현대오일뱅크  02-985-4382   
     9   서울특별시                세원주유소    서울 강북구 한천로 918 (번동)   SK에너지  02-907-6890   
     10  서울특별시         대성석유(주)신광주유소         서울 강북구 삼양로 484   GS칼텍스  02-908-3320   
     11  서울특별시       SK에너지(주) 매일주유소   서울 강북구 삼양로 217 (미아동)   SK에너지  02-982-8855   
     12  서울특별시                에덴주유소    서울 강북구 월계로 195 (번동)   SK에너지  02-987-8182   
     
        셀프여부 고급휘발유   휘발유    경유  실내등유  
     0     Y     -  1745  1595     -  
     1     N     -  1758  1583     -  
     2     Y  2005  1759  1584     -  
     3     Y     -  1762  1587  1200  
     4     Y     -  1762  1587     -  
     5     N     -  1762  1587     -  
     6     Y     -  1762  1587     -  
     7     Y  1894  1764  1584     -  
     8     Y  2005  1764  1584     -  
     9     Y     -  1768  1598  1300  
     10    N     -  1775  1595  1350  
     11    Y     -  1789  1609     -  
     12    Y     -  1798  1598     -  ,
            지역                  상호                        주소      상표  \
     0   서울특별시   현대오일뱅크㈜직영 강변현대주유소        서울 용산구 원효로 9 (청암동)  현대오일뱅크   
     1   서울특별시             제3한강주유소      서울 용산구 한남대로 45 (한남동)   GS칼텍스   
     2   서울특별시         (주)영원 풍기주유소    서울 용산구 원효로 178 (원효로2가)   GS칼텍스   
     3   서울특별시    현대오일뱅크㈜직영 한남동주유소     서울 용산구 한남대로 204 (한남동)  현대오일뱅크   
     4   서울특별시              갈월동주유소     서울 용산구 한강대로 322 (갈월동)  현대오일뱅크   
     5   서울특별시           (주)신태성주유소    서울 용산구 원효로 147 (원효로3가)   SK에너지   
     6   서울특별시  현대오일뱅크(주)직영 소월길주유소       서울 용산구 소월로 66 (후암동)  현대오일뱅크   
     7   서울특별시            (주)남경주유소        서울 용산구 녹사평대로11길 24   SK에너지   
     8   서울특별시               한석주유소            서울 용산구 이촌로 164   SK에너지   
     9   서울특별시                에너비스      서울 용산구 한남대로 82 (한남동)   SK에너지   
     10  서울특별시                한남지점    서울 용산구 한남대로21길 4 (한남동)   SK에너지   
     11  서울특별시              동자동주유소   서울 용산구 한강대로104길 6 (동자동)   SK에너지   
     12  서울특별시               서계주유소  서울특별시 용산구  청파로 367 (청파동)   GS칼텍스   
     
                  전화번호 셀프여부  고급휘발유   휘발유    경유  실내등유  
     0     02-712-7124    N   2078  2007  1849     -  
     1     02-749-3180    N   2278  2048  1848     -  
     2     02-719-2202    N   2358  2130  1970  1480  
     3     02-795-0802    N   2398  2136  1979     -  
     4     02-754-5217    N   2438  2137  1977  1280  
     5     02-701-9447    N   2358  2138  1998  1563  
     6     02-318-3314    N   2527  2139  1986     -  
     7     02-793-2954    N   2368  2149  2049  1573  
     8     02-790-1020    N   2474  2205  2123     -  
     9   070-8707-4572    N   2438  2238  2038     -  
     10  070-8707-4586    N   2438  2238  2038     -  
     11    02-754-6667    N   2590  2290  2120  1540  
     12    02-713-3324    N   2912  2630  2519  1866  ,
            지역                 상호                     주소      상표         전화번호 셀프여부  \
     0   서울특별시              불광주유소   서울 은평구 연서로 314 (불광동)  현대오일뱅크  02-382-5149    Y   
     1   서울특별시      성원이앤에스(주)은평지점   서울 은평구 통일로 968 (진관동)   GS칼텍스  02-352-4451    Y   
     2   서울특별시              다회주유소   서울 은평구 증산로 441 (신사동)   S-OIL  02-375-5156    Y   
     3   서울특별시        대성산업㈜ 대성주유소         서울 은평구 통일로 642   GS칼텍스  02-355-3434    Y   
     4   서울특별시           은평뉴타운주유소   서울 은평구 통일로 924 (불광동)   SK에너지  02-355-0349    Y   
     5   서울특별시             타이거주유소   서울 은평구 수색로 188 (증산동)   SK에너지  02-309-9145    Y   
     6   서울특별시            박석고개주유소   서울 은평구 통일로 945 (갈현동)   SK에너지  02-388-0477    Y   
     7   서울특별시  지에스칼텍스(주)수색뉴타운주유소   서울 은평구 수색로 350 (수색동)   GS칼텍스  02-309-5051    Y   
     8   서울특별시           뉴타운셀프주유소        서울 은평구 통일로 1031   S-OIL  02-355-3055    Y   
     9   서울특별시  현대오일뱅크㈜직영 은평드림주유소  서울 은평구 통일로 1151 (진관동)  현대오일뱅크  02-354-5182    N   
     10  서울특별시      지에스칼텍스㈜ 녹번주유소   서울 은평구 통일로 600 (녹번동)   GS칼텍스  02-385-5002    Y   
     11  서울특별시      지에스칼텍스㈜ 서부주유소   서울 은평구 응암로 210 (응암동)   GS칼텍스  02-302-6041    Y   
     12  서울특별시    지에스칼텍스㈜ 신사제일주유소   서울 은평구 증산로 423 (신사동)   GS칼텍스  02-308-4333    Y   
     13  서울특별시  (주)명연에너지 수색훼미리주유소   서울 은평구 수색로 236 (수색동)  현대오일뱅크  02-374-8770    Y   
     14  서울특별시            제이제이에너지         서울 은평구 응암로 163   SK에너지  02-303-1448    Y   
     15  서울특별시             코끼리주유소   서울 은평구 서오릉로 41 (녹번동)    자가상표  02-384-4000    N   
     16  서울특별시              삼융주유소   서울 은평구 수색로 299 (수색동)   SK에너지  02-307-3314    N   
     
        고급휘발유   휘발유    경유  실내등유  
     0   1933  1743  1578     -  
     1   1975  1749  1577     -  
     2      -  1754  1594     -  
     3   1948  1765  1599     -  
     4      -  1768  1587  1280  
     5      -  1769  1609  1300  
     6      -  1778  1597     -  
     7   1964  1784  1627     -  
     8      -  1785  1615     -  
     9   2004  1788  1607  1300  
     10  1965  1788  1623     -  
     11  1965  1788  1623  1250  
     12  1965  1788  1623  1250  
     13     -  1789  1629     -  
     14     -  1797  1657     -  
     15     -  1818  1668     -  
     16     -     -     -     -  ,
           지역               상호                      주소      상표           전화번호 셀프여부  \
     0  서울특별시    ㈜지에스이앤알 평창주유소  서울 종로구 평창문화로 135 (평창동)  현대오일뱅크    02-391-5185    N   
     1  서울특별시            안풍주유소         서울 종로구 자하문로 303   S-OIL    02-396-5151    N   
     2  서울특별시           자하문주유소   서울 종로구 자하문로 248 (부암동)   SK에너지    02-396-5252    Y   
     3  서울특별시         구도일주유소특종   서울 종로구 평창문화로 90 (평창동)   S-OIL    02-379-6524    N   
     4  서울특별시          SK북악주유소        서울 종로구 평창문화로 137   SK에너지    02-395-6500    N   
     5  서울특별시           경복궁주유소      서울 종로구 율곡로 6 (중학동)   GS칼텍스   02-6016-6981    N   
     6  서울특별시   (주)대양씨앤씨 사직주유소     서울 종로구 사직로 65 (사직동)   GS칼텍스    02-735-4858    N   
     7  서울특별시  (주)중앙에너비스 혜화주유소        서울 종로구 창경궁로35길 1   SK에너지  070-8707-4563    N   
     
        고급휘발유   휘발유    경유  실내등유  
     0   1979  1819  1649     -  
     1   1989  1829  1659     -  
     2   1990  1829  1659     -  
     3   2050  1850  1680  1350  
     4   2418  2218  2038     -  
     5   2390  2225  2030     -  
     6   2415  2235  2037  1400  
     7   2438  2238  2038  1400  ,
            지역               상호                      주소      상표          전화번호 셀프여부  \
     0   서울특별시            다산주유소           서울 중구 다산로 233   S-OIL  02-2252-2210    Y   
     1   서울특별시          장충드림주유소           서울 중구 동호로 296   S-OIL  02-2275-5150    Y   
     2   서울특별시            세화주유소          서울 중구 왕십리로 403   알뜰주유소  02-2234-3451    N   
     3   서울특별시     현대오일뱅크 장원주유소     서울 중구 동호로 203 (신당동)  현대오일뱅크  02-2236-2759    N   
     4   서울특별시            장충주유소  서울 중구 장충단로 202 (장충동1가)   SK에너지  02-2279-9965    N   
     5   서울특별시           신당동주유소     서울 중구 다산로 242 (신당동)   SK에너지  02-2252-6688    N   
     6   서울특별시            약수주유소           서울 중구 다산로 173   GS칼텍스  02-2252-3345    N   
     7   서울특별시  SK에너지(주) 퇴계로주유소    서울 중구 퇴계로 228 (필동2가)   SK에너지  02-2273-5189    N   
     8   서울특별시            필동주유소   서울 중구  퇴계로 196 (필동2가)   GS칼텍스  02-2267-8025    N   
     9   서울특별시            서남주유소            서울 중구 통일로 30   SK에너지   02-752-2262    N   
     10  서울특별시  지에스칼텍스(주)직영 역전점            서울 중구 퇴계로 15   GS칼텍스   02-752-6880    N   
     
        고급휘발유   휘발유    경유  실내등유  
     0   1889  1749  1549  1300  
     1      -  1795  1635     -  
     2      -  1898  1698  1400  
     3   2158  1957  1828  1400  
     4   2298  2098  1988     -  
     5   2348  2148  1998  1490  
     6   2498  2231  2083     -  
     7   2468  2394  2292     -  
     8   2729  2429  2319  1759  
     9   2999  2631  2520  2023  
     10     -     -     -     -  ,
            지역                  상호                           주소      상표  \
     0   서울특별시              오천만주유소         서울 중랑구 동일로 547 (면목동)   S-OIL   
     1   서울특별시           구도일주유소 동천         서울 중랑구 동일로 654 (면목동)   S-OIL   
     2   서울특별시               대원주유소               서울 중랑구 동일로 600   GS칼텍스   
     3   서울특별시            (주)기지에너지        서울 중랑구 용마산로 716 (신내동)   S-OIL   
     4   서울특별시           면목SELF주유소         서울 중랑구 동일로 627 (면목동)   SK에너지   
     5   서울특별시      (주)자연에너지 대창주유소         서울 중랑구 동일로 636 (면목동)  현대오일뱅크   
     6   서울특별시               대양주유소        서울 중랑구 봉우재로 105 (상봉동)   GS칼텍스   
     7   서울특별시               우림주유소  서울특별시 중랑구  용마산로 487 (망우제3동)   GS칼텍스   
     8   서울특별시               신내주유소        서울 중랑구 용마산로 705 (신내동)   SK에너지   
     9   서울특별시              용마로주유소        서울 중랑구 용마산로 309 (면목동)   SK에너지   
     10  서울특별시     (주)태영 구도일주유소 한인         서울 중랑구 망우로 170 (상봉동)   S-OIL   
     11  서울특별시             신일셀프주유소          서울 중랑구 상봉로 58 (망우동)   SK에너지   
     12  서울특별시               범아주유소          서울 중랑구 동일로 881 (묵동)   S-OIL   
     13  서울특별시  현대오일뱅크㈜직영 중랑교셀프주유소         서울 중랑구 망우로 229 (중화동)  현대오일뱅크   
     
                  전화번호 셀프여부 고급휘발유   휘발유    경유  실내등유  
     0   070-7797-7474    Y     -  1737  1575     -  
     1     02-495-0081    Y     -  1737  1565     -  
     2     02-438-6111    Y  1895  1737  1575  1300  
     3    02-2207-9419    N     -  1745  1575  1280  
     4     02-437-4072    Y     -  1757  1585     -  
     5     02-434-1448    N     -  1757  1585  1220  
     6     02-437-5457    Y  1950  1765  1595  1250  
     7     02-433-9990    Y     -  1765  1595     -  
     8    02-2207-0523    Y     -  1769  1598  1300  
     9     02-439-3037    Y     -  1788  1628  1300  
     10    02-438-5151    Y  1925  1795  1615  1200  
     11    02-436-3651    Y     -  1798  1599  1300  
     12    02-974-8356    N     -  1799  1619  1300  
     13    02-493-0115    Y  2050  1818  1639     -  ,
            지역                   상호                       주소      상표  \
     0   서울특별시               뉴신정주유소    서울 강서구 곰달래로 207 (화곡동)   알뜰주유소   
     1   서울특별시               화곡역주유소     서울 강서구 강서로 154 (화곡동)   알뜰주유소   
     2   서울특별시      지에스칼텍스㈜ 경인고속주유소    서울 강서구 국회대로 225 (화곡동)   GS칼텍스   
     3   서울특별시         현대오일뱅크 등촌주유소     서울 강서구 등촌로 189 (등촌동)  현대오일뱅크   
     4   서울특별시                목화주유소    서울 강서구 국회대로 251 (화곡동)   SK에너지   
     5   서울특별시              강서열린주유소     서울 강서구 등촌로 213 (등촌동)   GS칼텍스   
     6   서울특별시                방화주유소   서울 강서구 방화동로 58-2 (방화동)   SK에너지   
     7   서울특별시            강서오곡셀프주유소     서울 강서구 벌말로 254 (오곡동)   SK에너지   
     8   서울특별시                유턴주유소          서울 강서구 남부순환로 57   알뜰주유소   
     9   서울특별시          행촌에너지 공항주유소    서울 강서구 개화동로 420 (개화동)  현대오일뱅크   
     10  서울특별시                개화주유소            서울 강서구 양천로 57   SK에너지   
     11  서울특별시               스카이주유소    서울 강서구 개화동로 457 (방화동)   S-OIL   
     12  서울특별시        (주)한진 김포공항주유소           서울 강서구 하늘길 259   S-OIL   
     13  서울특별시  KH에너지(주)직영 KH외발산주유소           서울 강서구 방화대로 30   SK에너지   
     14  서울특별시  현대오일뱅크㈜직영 강서제일셀프주유소     서울 강서구 화곡로 273 (화곡동)  현대오일뱅크   
     15  서울특별시        현대오일뱅크 양화교주유소          서울 강서구 공항대로 653  현대오일뱅크   
     16  서울특별시      대성석유(주) 마곡대성주유소           서울 강서구 강서로 457   GS칼텍스   
     17  서울특별시               신화곡주유소           서울 강서구 국회대로 71   S-OIL   
     18  서울특별시              하이웨이주유소  서울특별시 강서구 공항대로 432(화곡동)   S-OIL   
     19  서울특별시              세원제1주유소     서울 강서구 양천로 311 (가양동)   SK에너지   
     20  서울특별시              화곡현대주유소     서울 강서구 강서로 151 (화곡동)   SK에너지   
     21  서울특별시        대성석유(주) 관문주유소          서울 강서구 공항대로 314   GS칼텍스   
     22  서울특별시               우장산주유소    서울 강서구 강서로 292 (내발산동)   SK에너지   
     23  서울특별시       대성석유(주)방화대성주유소           서울 강서구 양천로 176   GS칼텍스   
     24  서울특별시                대성주유소           서울 강서구 강서로 472   GS칼텍스   
     25  서울특별시     KH에너지(주)직영 가양주유소     서울 강서구 강서로 498 (가양동)   SK에너지   
     26  서울특별시      현대오일뱅크(주) 가양주유소    서울 강서구  양천로 391 (가양동)  현대오일뱅크   
     27  서울특별시      (주)한진 김포공항제2주유소           서울 강서구 하늘길 112   S-OIL   
     28  서울특별시               박물관주유소   서울 강서구 양천로53길 97 (가양동)   GS칼텍스   
     29  서울특별시          코리나(주)청룡주유소           서울 강서구 양천로 576   SK에너지   
     30  서울특별시                참솔에너지     서울 강서구 벌말로 281 (오곡동)   S-OIL   
     31  서울특별시               염창동주유소     서울 강서구 양천로 720 (염창동)   SK에너지   
     
                  전화번호 셀프여부 고급휘발유   휘발유    경유  실내등유  
     0    02-2601-0077    N     -  1718  1568     -  
     1    02-2691-5151    Y     -  1718  1568     -  
     2    02-2608-5151    Y  1939  1725  1578     -  
     3    02-2647-5700    N     -  1736  1616     -  
     4    02-2654-4564    Y     -  1737  1585     -  
     5    02-2647-9091    N     -  1740  1620  1350  
     6    02-2662-0503    N     -  1743  1573  1300  
     7    032-671-5186    Y     -  1745  1575     -  
     8    02-2665-5047    Y     -  1748  1588  1250  
     9    02-2665-5189    Y     -  1757  1597     -  
     10   02-2661-5555    Y     -  1757  1597     -  
     11   02-2663-5146    Y  1925  1757  1594     -  
     12   02-2662-0422    Y     -  1759  1599  1250  
     13   032-677-9497    Y  1998  1765  1595     -  
     14   02-2695-4544    Y     -  1769  1629     -  
     15   02-3665-2004    Y  1985  1779  1619  1310  
     16   02-3664-7781    Y  2015  1795  1657     -  
     17   02-2611-3161    Y     -  1795  1625     -  
     18   02-2605-4000    Y  1927  1797  1657     -  
     19   02-3663-5151    Y     -  1800  1660     -  
     20   02-2607-1942    Y  2013  1803  1663     -  
     21   02-3665-2051    N  2015  1805  1667  1450  
     22   02-3664-7163    N     -  1805  1667  1450  
     23   02-3663-7781    Y  2015  1805  1667     -  
     24   02-3661-6102    N     -  1815  1677     -  
     25   02-3664-6051    N  2015  1815  1677     -  
     26   02-3661-9470    N  2016  1825  1677     -  
     27   02-2661-8892    Y     -  1831  1665     -  
     28   02-3665-5189    N  1998  1848  1698     -  
     29   02-3661-1575    N     -  1878  1728  1350  
     30  070-8844-8282    Y     -  1953  1753     -  
     31   02-3664-4134    N     -  2067  1806     -  ,
            지역                   상호                          주소      상표  \
     0   서울특별시   (주)엠오티이엔지 직영 삼화주유소              서울 관악구 보라매로 41  현대오일뱅크   
     1   서울특별시  현대오일뱅크(주)직영 관악셀프주유소     서울 관악구 남부순환로 1520 (신림동)  현대오일뱅크   
     2   서울특별시       (주)연우에너지 신관주유소        서울 관악구 신림로 290 (신림동)   알뜰주유소   
     3   서울특별시                유림주유소        서울 관악구 신림로 176 (신림동)   S-OIL   
     4   서울특별시                현대주유소        서울 관악구 난곡로 108 (신림동)  현대오일뱅크   
     5   서울특별시     대양석유(주)직영 보라매주유소       서울 관악구  보라매로 26 (봉천동)   SK에너지   
     6   서울특별시         서일석유(주)락성주유소     서울 관악구 남부순환로 1920 (봉천동)   GS칼텍스   
     7   서울특별시        지에스칼텍스㈜ 난곡주유소              서울 관악구 난곡로 206   GS칼텍스   
     8   서울특별시    SK에너지(주)직영 대공원주유소       서울 관악구 과천대로 921 (남현동)   SK에너지   
     9   서울특별시   현대오일뱅크(주)직영 문성골주유소         서울 관악구 문성로 97 (신림동)  현대오일뱅크   
     10  서울특별시         SK에너지(주) 신봉천     서울 관악구 남부순환로 1880 (봉천동)   SK에너지   
     11  서울특별시              관악시몬주유소  서울특별시 관악구 남부순환로 1753 (봉천동)   S-OIL   
     12  서울특별시      (주)한유에너지행운셀프주유소     서울 관악구 남부순환로 1883 (봉천동)   SK에너지   
     13  서울특별시        CJ대한통운㈜ 신림주유소     서울 관악구 남부순환로 1515 (신림동)   GS칼텍스   
     
                 전화번호 셀프여부 고급휘발유   휘발유    경유  실내등유  
     0    02-889-8929    N     -  1768  1598  1190  
     1    02-867-1877    Y  2069  1769  1599     -  
     2    02-871-1356    Y     -  1788  1618  1300  
     3    02-887-5145    N     -  1798  1648  1198  
     4    02-851-9200    N     -  1799  1639     -  
     5    02-882-5189    Y     -  1799  1619     -  
     6    02-877-0867    Y  2069  1809  1648  1300  
     7    02-858-2003    N     -  1819  1682     -  
     8    02-584-2522    N  1965  1819  1659     -  
     9    02-839-0081    N     -  1839  1679  1290  
     10   02-885-5189    N  1985  1849  1689  1169  
     11   02-874-5185    N     -  1873  1697     -  
     12   02-871-5189    Y  2254  1879  1698     -  
     13  02-2632-8612    N     -  1899  1735     -  ,
            지역                   상호                     주소      상표          전화번호  \
     0   서울특별시              (주)창원CW  서울 광진구 광나루로 460 (화양동)  현대오일뱅크  02-3436-1112   
     1   서울특별시    현대오일뱅크(주)직영 능동주유소   서울 광진구 천호대로 584 (능동)  현대오일뱅크   02-452-7723   
     2   서울특별시                태양주유소   서울 광진구 동일로 345 (중곡동)  현대오일뱅크   02-464-5141   
     3   서울특별시       정해네트웍스(주)일진주유소   서울 광진구 동일로 413 (중곡동)   S-OIL   02-461-5152   
     4   서울특별시                대원주유소  서울 광진구 용마산로 122 (중곡동)   S-OIL   02-444-1666   
     5   서울특별시  현대오일뱅크(주)직영 중곡현대주유소   서울 광진구 동일로 435 (중곡동)  현대오일뱅크   02-497-5151   
     6   서울특별시      현대오일뱅크(주) 중원주유소   서울 광진구 동일로 398 (중곡동)  현대오일뱅크   02-467-2410   
     7   서울특별시             (주)장수주유소   서울 광진구 동일로 266 (군자동)   SK에너지   02-498-1981   
     8   서울특별시                용마주유소   서울 광진구 용마산로 68 (중곡동)   GS칼텍스   02-456-1884   
     9   서울특별시    현대오일뱅크㈜직영 장호셀프주유소     서울 광진구 자양로37 (자양동)  현대오일뱅크   02-447-9796   
     10  서울특별시         대성산업(주)구의주유소  서울 광진구 광나루로 570 (구의동)   GS칼텍스   02-457-0638   
     11  서울특별시               동서울주유소   서울 광진구 강변역로 10 (구의동)   GS칼텍스   02-444-3910   
     12  서울특별시                강평주유소  서울 광진구 아차산로 616 (광장동)   SK에너지  02-2201-0736   
     13  서울특별시                삼호주유소  서울 광진구 천호대로 809 (광장동)   S-OIL   02-455-7200   
     14  서울특별시                자양주유소  서울 광진구 아차산로 298 (자양동)   SK에너지   02-457-7600   
     15  서울특별시              구의스타주유소         서울 광진구 자양로 103   GS칼텍스   02-457-4071   
     
        셀프여부 고급휘발유   휘발유    경유  실내등유  
     0     Y     -  1749  1579     -  
     1     Y  1975  1749  1579  1230  
     2     N     -  1759  1599     -  
     3     Y  1917  1767  1607     -  
     4     N     -  1775  1629     -  
     5     N  1990  1775  1613     -  
     6     N  2010  1775  1613  1230  
     7     N     -  1778  1615     -  
     8     N     -  1785  1639     -  
     9     Y     -  1799  1639     -  
     10    N     -  1799  1619     -  
     11    N     -  1817  1657  1300  
     12    N  2048  1838  1678  1348  
     13    Y  2038  1838  1678     -  
     14    N  2065  1875  1725     -  
     15    N     -     -     -     -  ,
            지역                  상호                       주소      상표          전화번호  \
     0   서울특별시             대원셀프주유소             서울 구로구 개봉로 7  현대오일뱅크  02-2612-3880   
     1   서울특별시             근린공원주유소     서울 구로구 고척로 199 (고척동)   S-OIL  02-2066-3700   
     2   서울특별시               신성주유소  서울 구로구 구로동로 187 (구로제2동)  현대오일뱅크   02-866-5189   
     3   서울특별시               개봉주유소     서울 구로구 고척로 115 (개봉동)  현대오일뱅크  02-2618-5145   
     4   서울특별시       서울석유(주)풀페이주유소      서울 구로구 경인로 41 (온수동)   SK에너지  02-2613-7708   
     5   서울특별시             처음처럼주유소     서울 구로구 오리로 1299 (궁동)   S-OIL  02-2611-5051   
     6   서울특별시   현대오일뱅크㈜직영 구로셀프주유소          서울 구로구 시흥대로 531  현대오일뱅크   02-856-1135   
     7   서울특별시               구인주유소     서울 구로구 경인로 558 (구로동)   SK에너지  02-2677-5010   
     8   서울특별시             SK구로주유소      서울 구로구 구일로 94 (구로동)   SK에너지   02-868-5758   
     9   서울특별시      (주)한미석유구로그린주유소    서울 구로구 구로중앙로 76 (구로동)   GS칼텍스   02-861-5189   
     10  서울특별시    현대오일뱅크㈜직영 신오류주유소     서울 구로구 경인로 161 (오류동)  현대오일뱅크  02-2687-4186   
     11  서울특별시       극동유화(주) 항동주유소    서울 구로구 서해안로 2154 (항동)   S-OIL  02-2611-1113   
     12  서울특별시       대성산업(주)디큐브주유소    서울 구로구 경인로 650 (신도림동)   GS칼텍스  02-2633-7188   
     13  서울특별시              JHC에너지          서울 구로구 시흥대로 539  현대오일뱅크   02-866-9553   
     14  서울특별시            서서울고속주유소     서울 구로구 경인로 150 (오류동)   GS칼텍스  02-2683-1126   
     15  서울특별시   SK에너지(주)직영 개봉동주유소     서울 구로구 경인로 290 (개봉동)   SK에너지  02-2616-5189   
     16  서울특별시  현대오일뱅크(주)직영 신구로주유소    서울 구로구 가마산로 293 (구로동)  현대오일뱅크   02-859-0051   
     17  서울특별시               영진주유소    서울 구로구 구로동로 20 (가리봉동)   S-OIL   02-861-6625   
     18  서울특별시               시몬주유소           서울 구로구 부일로 871   S-OIL  02-2689-5185   
     19  서울특별시               동아주유소      서울 구로구 도림로 91 (구로동)   S-OIL   02-855-1282   
     20  서울특별시               구로주유소    서울 구로구 구로동로 137 (구로동)   GS칼텍스   02-587-1251   
     
        셀프여부 고급휘발유   휘발유    경유  실내등유  
     0     Y     -  1747  1587     -  
     1     N     -  1757  1597  1290  
     2     Y     -  1758  1588     -  
     3     Y     -  1759  1598  1250  
     4     N     -  1759  1579     -  
     5     N     -  1769  1599  1200  
     6     Y  1979  1769  1599     -  
     7     N     -  1777  1617  1300  
     8     N     -  1778  1618  1290  
     9     Y     -  1778  1598     -  
     10    N  1974  1779  1619  1230  
     11    Y     -  1779  1609     -  
     12    N  1978  1788  1588     -  
     13    N     -  1799  1659     -  
     14    N     -  1799  1629     -  
     15    N     -  1809  1629  1200  
     16    N  1964  1814  1663     -  
     17    N     -  1839  1639  1250  
     18    N     -  1857  1657     -  
     19    N     -  1948  1698  1398  
     20    N     -  2278  2098  1546  ,
            지역                     상호                         주소      상표  \
     0   서울특별시                  구광주유소  서울특별시 금천구  서부샛길 674 (가산동)   S-OIL   
     1   서울특별시          (주)화동유업 화동주유소            서울 금천구 시흥대로 484   SK에너지   
     2   서울특별시         (주)진우에너지 백운주유소      서울 금천구 시흥대로 282 (독산동)   알뜰주유소   
     3   서울특별시  현대오일뱅크(주)직영 금천현대셀프주유소       서울 금천구 독산로 147 (시흥동)  현대오일뱅크   
     4   서울특별시         대득에너지(금천셀프주유소)      서울 금천구  시흥대로 81 (시흥동)   GS칼텍스   
     5   서울특별시         지에스칼텍스(주)일신주유소            서울 금천구 시흥대로 118   GS칼텍스   
     6   서울특별시      현대오일뱅크㈜직영 금천제일주유소    서울 금천구 남부순환로 1410 (독산동)  현대오일뱅크   
     7   서울특별시                  백산주유소  서울특별시 금천구  시흥대로 174 (시흥동)   S-OIL   
     8   서울특별시         SK에너지(주) 박미주유소     서울 금천구 시흥대로 39-7 (시흥동)   SK에너지   
     9   서울특별시               남서울경복에너지       서울 금천구 독산로 257 (독산동)  현대오일뱅크   
     10  서울특별시         SK에너지(주) 이가주유소            서울 금천구 시흥대로 441   SK에너지   
     
                전화번호 셀프여부 고급휘발유   휘발유    경유  실내등유  
     0   02-868-6889    N     -  1755  1585  1130  
     1   02-856-0283    Y     -  1764  1594  1250  
     2   02-894-8521    Y     -  1765  1595  1300  
     3   02-891-5189    Y  1961  1765  1595     -  
     4   02-805-7888    Y  1940  1775  1610     -  
     5   02-896-5145    Y  1945  1775  1613  1150  
     6   02-859-5426    N     -  1779  1609     -  
     7   02-807-3161    Y     -  1795  1610     -  
     8   02-802-6749    N     -  1795  1615  1250  
     9   02-855-9880    Y     -  1795  1610  1200  
     10  02-861-2241    N  1946  1796  1624  1250  ,
            지역                 상호                         주소      상표          전화번호  \
     0   서울특별시              한신주유소      서울 노원구 동일로 1089 (공릉동)   SK에너지   02-974-5151   
     1   서울특별시             성북역주유소        서울 노원구 광운로 95 (월계동)   GS칼텍스   02-919-8141   
     2   서울특별시     이엠석유(주)배꽃나라주유소  서울특별시 노원구  화랑로 466 (공릉1동)   GS칼텍스   02-973-5172   
     3   서울특별시              삼육주유소       서울 노원구 화랑로 822 (공릉동)   SK에너지   02-949-3677   
     4   서울특별시            태릉솔밭주유소        서울 노원구 노원로 49 (공릉동)   S-OIL   02-976-5189   
     5   서울특별시    현대오일뱅크㈜직영 하계주유소     서울 노원구 노원로17길 29 (하계동)  현대오일뱅크   02-975-1386   
     6   서울특별시             화랑대주유소             서울 노원구 화랑로 483  현대오일뱅크   02-977-9697   
     7   서울특별시              월계주유소       서울 노원구 월계로 252 (월계동)   GS칼텍스   02-917-7650   
     8   서울특별시   남선석유(주)구도일주유소 불암     서울 노원구 한글비석로 268 (중계동)   S-OIL   02-932-6850   
     9   서울특별시              신성주유소       서울 노원구 월계로 328 (월계동)   S-OIL   02-916-4334   
     10  서울특별시     SK에너지㈜직영 상계주유소       서울 노원구 노해로 527 (상계동)   SK에너지   02-930-5151   
     11  서울특별시              노원주유소      서울 노원구 동일로 1008 (공릉동)   GS칼텍스   02-949-5151   
     12  서울특별시             상계동주유소    서울 노원구 노원로26길 191 (상계동)  현대오일뱅크   02-936-5035   
     13  서울특별시            하계삼호주유소       서울 노원구 공릉로 294 (하계동)   GS칼텍스   02-974-8818   
     14  서울특별시  (주)소모에너지 수락산셀프주유소            서울 노원구 동일로 1772   GS칼텍스  02-3392-5656   
     
        셀프여부 고급휘발유   휘발유    경유  실내등유  
     0     Y  1888  1718  1578     -  
     1     N  1938  1758  1598     -  
     2     Y  1968  1765  1595     -  
     3     Y     -  1775  1595  1250  
     4     Y  1985  1785  1595     -  
     5     N  2005  1785  1615  1289  
     6     Y  1995  1785  1595  1400  
     7     Y     -  1789  1625  1349  
     8     Y     -  1795  1625     -  
     9     Y     -  1798  1598     -  
     10    N     -  1815  1645     -  
     11    N     -  1828  1669  1350  
     12    N     -  1870  1690  1440  
     13    N     -  1880  1695     -  
     14    Y     -  1928  1758  1300  ,
            지역                   상호                    주소      상표          전화번호  \
     0   서울특별시       (주)자연에너지 햇살주유소  서울 도봉구 방학로 142 (방학동)  현대오일뱅크   02-954-4555   
     1   서울특별시  (주)헨지스에너지 구도일주유소 도봉  서울 도봉구 도봉로 706 (방학동)   S-OIL  02-3491-3454   
     2   서울특별시      도봉제일주유소(주)송만에너지  서울 도봉구 도봉로 783 (도봉동)  현대오일뱅크   02-955-5185   
     3   서울특별시  현대오일뱅크㈜직영 도봉현대셀프주유소  서울 도봉구 도봉로 941 (도봉동)  현대오일뱅크  02-3492-7371   
     4   서울특별시             정다운셀프주유소        서울 도봉구 도봉로 635   SK에너지   02-996-5151   
     5   서울특별시       지에스칼텍스㈜ 방학동주유소        서울 도봉구 방학로 186   GS칼텍스  02-3493-5189   
     6   서울특별시        지에스칼텍스㈜ 도봉주유소  서울 도봉구 도봉로 895 (도봉동)   GS칼텍스   02-954-0118   
     7   서울특별시           구도일주유소 파크빌  서울 도봉구 해등로3길 86 (창동)   S-OIL   02-906-5104   
     8   서울특별시        극동유화(주) 대안주유소   서울 도봉구 마들로 574 (창동)   S-OIL   02-996-6640   
     9   서울특별시     한이에너지(주)KLP제1주유소   서울 도봉구 도봉로 596 (창동)  현대오일뱅크   02-902-5189   
     10  서울특별시       한이에너지(주) 쌍문주유소  서울 도봉구 도봉로 547 (쌍문동)   S-OIL   02-992-0220   
     11  서울특별시         대성산업(주)신창주유소   서울 도봉구 덕릉로 267 (창동)   GS칼텍스   02-905-4441   
     12  서울특별시      현대오일뱅크㈜직영 영신주유소        서울 도봉구 방학로 151  현대오일뱅크   02-956-5152   
     13  서울특별시        동일석유(주) 창동주유소  서울 도봉구  도봉로 434 (창동)   SK에너지   02-902-5544   
     14  서울특별시               노원교주유소  서울 도봉구 마들로 776 (도봉동)  현대오일뱅크   02-956-5189   
     15  서울특별시           (주)쌍문셀프주유소  서울 도봉구 노해로 161 (쌍문동)  현대오일뱅크   02-998-9704   
     16  서울특별시            삼미북부셀프주유소  서울 도봉구 도봉로 437 (쌍문동)   SK에너지   02-992-5561   
     17  서울특별시                오복주유소         서울 도봉구 방학로 43   S-OIL  02-3494-1500   
     
        셀프여부 고급휘발유   휘발유    경유  실내등유  
     0     Y  1958  1715  1543     -  
     1     Y     -  1715  1543     -  
     2     N     -  1717  1545  1180  
     3     Y     -  1745  1575     -  
     4     Y     -  1759  1579     -  
     5     Y  1968  1767  1605  1305  
     6     Y  1965  1771  1599  1345  
     7     Y     -  1779  1599  1250  
     8     Y     -  1779  1609     -  
     9     N     -  1779  1599     -  
     10    Y     -  1779  1599     -  
     11    Y     -  1779  1599     -  
     12    N  2004  1789  1619  1289  
     13    Y     -  1789  1599     -  
     14    Y     -  1795  1625     -  
     15    Y     -  1795  1615  1200  
     16    Y     -  1799  1619  1300  
     17    Y  2100  1823  1648  1350  ,
            지역                   상호                         주소      상표  \
     0   서울특별시          (주)보성 세곡주유소      서울 강남구  헌릉로 731 (세곡동)   SK에너지   
     1   서울특별시  현대오일뱅크(주)직영 산성셀프주유소             서울 강남구 헌릉로 730  현대오일뱅크   
     2   서울특별시       현대오일뱅크 도곡셀프주유소  서울 강남구  남부순환로 2718 (도곡2동)  현대오일뱅크   
     3   서울특별시                대교주유소      서울 강남구 강남대로 640 (신사동)   SK에너지   
     4   서울특별시      현대오일뱅크(주) 유진주유소       서울 강남구 논현로 152 (도곡동)  현대오일뱅크   
     5   서울특별시             오일프러스 셀프    서울 강남구 남부순환로 2651 (도곡동)   SK에너지   
     6   서울특별시                방죽주유소      서울 강남구 밤고개로 215 (율현동)   GS칼텍스   
     7   서울특별시              SK서광주유소             서울 강남구 역삼로 142   SK에너지   
     8   서울특별시  지에스칼텍스㈜에너지플러스허브GS타워       서울 강남구 논현로 516 (역삼동)   GS칼텍스   
     9   서울특별시              자곡셀프주유소      서울 강남구 밤고개로 120 (자곡동)   SK에너지   
     10  서울특별시                일원주유소     서울 강남구 양재대로55길 3 (일원동)   S-OIL   
     11  서울특별시       (주)중앙에너비스 수서지점       서울 강남구 광평로 202 (수서동)   SK에너지   
     12  서울특별시        SK에너지㈜ 진달래주유소             서울 강남구 도곡로 208   SK에너지   
     13  서울특별시      에쓰-오일㈜직영 개나리주유소       서울 강남구 언주로 423 (역삼동)   S-OIL   
     14  서울특별시           (주)선진도곡주유소       서울 강남구 도곡로 162 (도곡동)   S-OIL   
     15  서울특별시       SK에너지(주) 매봉주유소             서울 강남구 언주로 307   SK에너지   
     16  서울특별시          대동석유 압구정주유소       서울 강남구 언주로 842 (신사동)   SK에너지   
     17  서울특별시      (유)동하석유 힐탑셀프주유소             서울 강남구 논현로 640   SK에너지   
     18  서울특별시   에스제이에너지산업(주) 개포주유소            서울 강남구 양재대로 339   GS칼텍스   
     19  서울특별시        지에스칼텍스㈜ 은마주유소            서울 강남구 영동대로 235   GS칼텍스   
     20  서울특별시     현대오일뱅크㈜직영 삼성동주유소      서울 강남구 테헤란로 619 (삼성동)  현대오일뱅크   
     21  서울특별시  현대오일뱅크(주)직영 신사현대주유소      서울 강남구 도산대로 163 (신사동)  현대오일뱅크   
     22  서울특별시       지에스칼텍스㈜ 삼성로주유소       서울 강남구 삼성로 563 (삼성동)   GS칼텍스   
     23  서울특별시    현대오일뱅크(주)직영 한양주유소      서울 강남구 압구정로 302 (신사동)  현대오일뱅크   
     24  서울특별시        ㈜새서울석유 새서울주유소            서울 강남구 압구정로 154  현대오일뱅크   
     25  서울특별시         대성석유(주)동호주유소         서울 강남구 봉은사로113길 51   GS칼텍스   
     26  서울특별시                명품주유소       서울 강남구 도곡로 249 (역삼동)   S-OIL   
     27  서울특별시                대청주유소       서울 강남구 개포로 654 (일원동)   SK에너지   
     28  서울특별시      지에스칼텍스(주)학여울주유소   서울 강남구 남부순환로 3170 (일원2동)   GS칼텍스   
     29  서울특별시              갤러리아주유소            서울 강남구 압구정로 426   SK에너지   
     30  서울특별시      (주)소모에너지 쎈트럴주유소             서울 강남구 삼성로 335   GS칼텍스   
     31  서울특별시              SK논현주유소       서울 강남구 논현로 747 (논현동)   SK에너지   
     32  서울특별시             (주)만정에너지      서울 강남구 봉은사로 433 (삼성동)   GS칼텍스   
     33  서울특별시              제이제이주유소             서울 강남구 언주로 716  현대오일뱅크   
     34  서울특별시                동우주유소  서울특별시 강남구  봉은사로 311 (논현동)   SK에너지   
     35  서울특별시                경원주유소      서울 강남구 도산대로 428 (청담동)   S-OIL   
     36  서울특별시                삼성주유소       서울 강남구 삼성로 521 (삼성동)   SK에너지   
     
                  전화번호 셀프여부 고급휘발유   휘발유    경유  실내등유  
     0     02-445-6870    Y     -  1763  1574     -  
     1    02-2226-4963    Y  1990  1779  1584     -  
     2     02-529-5101    Y  1953  1798  1648     -  
     3     02-512-5521    N  1970  1810  1650     -  
     4    02-3462-5215    N  1968  1813  1663  1300  
     5    02-3462-5100    Y  1968  1813  1663     -  
     6     02-459-3434    Y     -  1817  1649     -  
     7     02-562-4855    Y  1975  1825  1675     -  
     8     02-539-5145    N  2002  1842  1683     -  
     9     02-445-5841    Y     -  1857  1675     -  
     10   02-2226-5188    Y     -  1858  1698  1300  
     11  070-8707-4582    Y  1988  1858  1698     -  
     12   02-3462-0018    N  1989  1869  1719     -  
     13    02-564-0187    N  2019  1869  1719     -  
     14   02-2058-3024    N  2019  1869  1719     -  
     15    02-556-5510    Y  2004  1879  1729     -  
     16    02-545-6161    Y  2037  1897  1737     -  
     17    02-544-4075    Y  2037  1897  1737     -  
     18    02-573-9031    N  2235  1928  1808  1550  
     19   02-3452-1882    N  2098  1948  1814     -  
     20    02-508-6572    N  2054  1974  1814     -  
     21    02-546-2182    N  2299  2014  1872     -  
     22    02-538-5138    Y  2168  2018  1875     -  
     23   02-3444-0804    N  2195  2024  1857     -  
     24    02-543-1154    N  2257  2058  1898  1650  
     25    02-545-0720    N  2193  2093  1899     -  
     26    02-501-1256    N  2244  2109  1992     -  
     27    02-445-5500    N  2336  2119  1989     -  
     28    02-459-8829    N  2384  2129  2012     -  
     29    02-540-4965    N  2425  2243  2042  1530  
     30    02-565-0267    N  2433  2284  2042  1300  
     31    02-511-0955    N  2440  2285  2098  1650  
     32    02-518-5141    N  2498  2298  2054  1599  
     33    02-518-5631    N  2565  2375  2235     -  
     34    02-542-6726    N     -     -     -     -  
     35    02-517-1957    N     -     -     -     -  
     36    02-538-0809    N     -     -     -     -  ]



- 형식이 동일하고 연달아 붙이기만 하면 될 떄는 concat


```python
stations_raw = pd.concat(tmp_raw) # 데이터 프레임 형식으로 바꿔서 붙여줌
stations_raw

# rows 는 469개인데 마지막 번호가 36인걸 봐서 무언가 숫자가 반복되면서 문제가 생겼음을 인지해야한다.
# 하지만 어떤 이유에서 이렇게 index가 매겨지는지는 모르겠다. 
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
      <th>지역</th>
      <th>상호</th>
      <th>주소</th>
      <th>상표</th>
      <th>전화번호</th>
      <th>셀프여부</th>
      <th>고급휘발유</th>
      <th>휘발유</th>
      <th>경유</th>
      <th>실내등유</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>서울특별시</td>
      <td>재건에너지 재정제2주유소 고속셀프지점</td>
      <td>서울특별시 강동구  천호대로 1246 (둔촌제2동)</td>
      <td>현대오일뱅크</td>
      <td>02-487-2030</td>
      <td>Y</td>
      <td>-</td>
      <td>1769</td>
      <td>1599</td>
      <td>-</td>
    </tr>
    <tr>
      <th>1</th>
      <td>서울특별시</td>
      <td>구천면주유소</td>
      <td>서울 강동구 구천면로 357 (암사동)</td>
      <td>현대오일뱅크</td>
      <td>02-441-0536</td>
      <td>N</td>
      <td>-</td>
      <td>1793</td>
      <td>1657</td>
      <td>-</td>
    </tr>
    <tr>
      <th>2</th>
      <td>서울특별시</td>
      <td>지에스칼텍스㈜ 신월주유소</td>
      <td>서울 강동구 양재대로 1323 (성내동)</td>
      <td>GS칼텍스</td>
      <td>02-475-2600</td>
      <td>N</td>
      <td>1958</td>
      <td>1808</td>
      <td>1659</td>
      <td>1345</td>
    </tr>
    <tr>
      <th>3</th>
      <td>서울특별시</td>
      <td>방아다리주유소</td>
      <td>서울 강동구 동남로 811 (명일동)</td>
      <td>SK에너지</td>
      <td>02-442-5145</td>
      <td>Y</td>
      <td>-</td>
      <td>1810</td>
      <td>1650</td>
      <td>1300</td>
    </tr>
    <tr>
      <th>4</th>
      <td>서울특별시</td>
      <td>지에스칼텍스㈜ 동서울주유소</td>
      <td>서울 강동구 천호대로 1456 (상일동)</td>
      <td>GS칼텍스</td>
      <td>02-426-5372</td>
      <td>Y</td>
      <td>-</td>
      <td>1815</td>
      <td>1660</td>
      <td>-</td>
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
    </tr>
    <tr>
      <th>32</th>
      <td>서울특별시</td>
      <td>(주)만정에너지</td>
      <td>서울 강남구 봉은사로 433 (삼성동)</td>
      <td>GS칼텍스</td>
      <td>02-518-5141</td>
      <td>N</td>
      <td>2498</td>
      <td>2298</td>
      <td>2054</td>
      <td>1599</td>
    </tr>
    <tr>
      <th>33</th>
      <td>서울특별시</td>
      <td>제이제이주유소</td>
      <td>서울 강남구 언주로 716</td>
      <td>현대오일뱅크</td>
      <td>02-518-5631</td>
      <td>N</td>
      <td>2565</td>
      <td>2375</td>
      <td>2235</td>
      <td>-</td>
    </tr>
    <tr>
      <th>34</th>
      <td>서울특별시</td>
      <td>동우주유소</td>
      <td>서울특별시 강남구  봉은사로 311 (논현동)</td>
      <td>SK에너지</td>
      <td>02-542-6726</td>
      <td>N</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <th>35</th>
      <td>서울특별시</td>
      <td>경원주유소</td>
      <td>서울 강남구 도산대로 428 (청담동)</td>
      <td>S-OIL</td>
      <td>02-517-1957</td>
      <td>N</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <th>36</th>
      <td>서울특별시</td>
      <td>삼성주유소</td>
      <td>서울 강남구 삼성로 521 (삼성동)</td>
      <td>SK에너지</td>
      <td>02-538-0809</td>
      <td>N</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
    </tr>
  </tbody>
</table>
<p>469 rows × 10 columns</p>
</div>




```python
stations_raw.info()
```

    <class 'pandas.core.frame.DataFrame'>
    Int64Index: 469 entries, 0 to 36
    Data columns (total 10 columns):
     #   Column  Non-Null Count  Dtype 
    ---  ------  --------------  ----- 
     0   지역      469 non-null    object
     1   상호      469 non-null    object
     2   주소      469 non-null    object
     3   상표      469 non-null    object
     4   전화번호    469 non-null    object
     5   셀프여부    469 non-null    object
     6   고급휘발유   469 non-null    object
     7   휘발유     469 non-null    object
     8   경유      469 non-null    object
     9   실내등유    469 non-null    object
    dtypes: object(10)
    memory usage: 40.3+ KB
    


```python
stations_raw.columns
```




    Index(['지역', '상호', '주소', '상표', '전화번호', '셀프여부', '고급휘발유', '휘발유', '경유', '실내등유'], dtype='object')




```python
# 필요한 index 만 뽑아서 새롭게 데이터 프레임 구성
stations = pd.DataFrame({
    '상호' : stations_raw['상호'],
    '주소' : stations_raw['주소'],
    '가격' : stations_raw['휘발유'],
    '셀프' : stations_raw['셀프여부'],
    '상표' : stations_raw['상표'],
    
})
stations.tail()
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
      <th>상호</th>
      <th>주소</th>
      <th>가격</th>
      <th>셀프</th>
      <th>상표</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>32</th>
      <td>(주)만정에너지</td>
      <td>서울 강남구 봉은사로 433 (삼성동)</td>
      <td>2298</td>
      <td>N</td>
      <td>GS칼텍스</td>
    </tr>
    <tr>
      <th>33</th>
      <td>제이제이주유소</td>
      <td>서울 강남구 언주로 716</td>
      <td>2375</td>
      <td>N</td>
      <td>현대오일뱅크</td>
    </tr>
    <tr>
      <th>34</th>
      <td>동우주유소</td>
      <td>서울특별시 강남구  봉은사로 311 (논현동)</td>
      <td>-</td>
      <td>N</td>
      <td>SK에너지</td>
    </tr>
    <tr>
      <th>35</th>
      <td>경원주유소</td>
      <td>서울 강남구 도산대로 428 (청담동)</td>
      <td>-</td>
      <td>N</td>
      <td>S-OIL</td>
    </tr>
    <tr>
      <th>36</th>
      <td>삼성주유소</td>
      <td>서울 강남구 삼성로 521 (삼성동)</td>
      <td>-</td>
      <td>N</td>
      <td>SK에너지</td>
    </tr>
  </tbody>
</table>
</div>




```python
stations['주소']
```




    0     서울특별시 강동구  천호대로 1246 (둔촌제2동)
    1            서울 강동구 구천면로 357 (암사동)
    2           서울 강동구 양재대로 1323 (성내동)
    3             서울 강동구 동남로 811 (명일동)
    4           서울 강동구 천호대로 1456 (상일동)
                      ...             
    32           서울 강남구 봉은사로 433 (삼성동)
    33                  서울 강남구 언주로 716
    34       서울특별시 강남구  봉은사로 311 (논현동)
    35           서울 강남구 도산대로 428 (청담동)
    36            서울 강남구 삼성로 521 (삼성동)
    Name: 주소, Length: 469, dtype: object




```python
for eachAddress in stations['주소']:
    print(eachAddress.split()[1])  # index = 1 에 담긴 구 데이터만 추출한다.
```

    강동구
    강동구
    강동구
    강동구
    강동구
    강동구
    강동구
    강동구
    강동구
    강동구
    강동구
    강동구
    강동구
    강동구
    동대문구
    동대문구
    동대문구
    동대문구
    동대문구
    동대문구
    동대문구
    동대문구
    동대문구
    동대문구
    동대문구
    동대문구
    동대문구
    동대문구
    동대문구
    동대문구
    동대문구
    동대문구
    동대문구
    동작구
    동작구
    동작구
    동작구
    동작구
    동작구
    동작구
    동작구
    동작구
    동작구
    마포구
    마포구
    마포구
    마포구
    마포구
    마포구
    마포구
    마포구
    마포구
    마포구
    마포구
    마포구
    서대문구
    서대문구
    서대문구
    서대문구
    서대문구
    서대문구
    서대문구
    서대문구
    서대문구
    서대문구
    서대문구
    서대문구
    서대문구
    서대문구
    서대문구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    서초구
    성동구
    성동구
    성동구
    성동구
    성동구
    성동구
    성동구
    성동구
    성동구
    성동구
    성동구
    성동구
    성동구
    성동구
    성동구
    성동구
    성동구
    성북구
    성북구
    성북구
    성북구
    성북구
    성북구
    성북구
    성북구
    성북구
    성북구
    성북구
    성북구
    성북구
    성북구
    성북구
    성북구
    성북구
    성북구
    성북구
    성북구
    성북구
    성북구
    성북구
    성북구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    송파구
    양천구
    양천구
    양천구
    양천구
    양천구
    양천구
    양천구
    양천구
    양천구
    양천구
    양천구
    양천구
    양천구
    양천구
    양천구
    양천구
    양천구
    양천구
    양천구
    양천구
    양천구
    양천구
    양천구
    양천구
    양천구
    영등포구
    영등포구
    영등포구
    영등포구
    영등포구
    영등포구
    영등포구
    영등포구
    영등포구
    영등포구
    영등포구
    영등포구
    영등포구
    영등포구
    영등포구
    영등포구
    영등포구
    영등포구
    영등포구
    영등포구
    영등포구
    영등포구
    영등포구
    영등포구
    영등포구
    영등포구
    영등포구
    영등포구
    강북구
    강북구
    강북구
    강북구
    강북구
    강북구
    강북구
    강북구
    강북구
    강북구
    강북구
    강북구
    강북구
    용산구
    용산구
    용산구
    용산구
    용산구
    용산구
    용산구
    용산구
    용산구
    용산구
    용산구
    용산구
    용산구
    은평구
    은평구
    은평구
    은평구
    은평구
    은평구
    은평구
    은평구
    은평구
    은평구
    은평구
    은평구
    은평구
    은평구
    은평구
    은평구
    은평구
    종로구
    종로구
    종로구
    종로구
    종로구
    종로구
    종로구
    종로구
    중구
    중구
    중구
    중구
    중구
    중구
    중구
    중구
    중구
    중구
    중구
    중랑구
    중랑구
    중랑구
    중랑구
    중랑구
    중랑구
    중랑구
    중랑구
    중랑구
    중랑구
    중랑구
    중랑구
    중랑구
    중랑구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    강서구
    관악구
    관악구
    관악구
    관악구
    관악구
    관악구
    관악구
    관악구
    관악구
    관악구
    관악구
    관악구
    관악구
    관악구
    광진구
    광진구
    광진구
    광진구
    광진구
    광진구
    광진구
    광진구
    광진구
    광진구
    광진구
    광진구
    광진구
    광진구
    광진구
    광진구
    구로구
    구로구
    구로구
    구로구
    구로구
    구로구
    구로구
    구로구
    구로구
    구로구
    구로구
    구로구
    구로구
    구로구
    구로구
    구로구
    구로구
    구로구
    구로구
    구로구
    구로구
    금천구
    금천구
    금천구
    금천구
    금천구
    금천구
    금천구
    금천구
    금천구
    금천구
    금천구
    노원구
    노원구
    노원구
    노원구
    노원구
    노원구
    노원구
    노원구
    노원구
    노원구
    노원구
    노원구
    노원구
    노원구
    노원구
    도봉구
    도봉구
    도봉구
    도봉구
    도봉구
    도봉구
    도봉구
    도봉구
    도봉구
    도봉구
    도봉구
    도봉구
    도봉구
    도봉구
    도봉구
    도봉구
    도봉구
    도봉구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    강남구
    


```python
stations['주소']
```




    0     서울특별시 강동구  천호대로 1246 (둔촌제2동)
    1            서울 강동구 구천면로 357 (암사동)
    2           서울 강동구 양재대로 1323 (성내동)
    3             서울 강동구 동남로 811 (명일동)
    4           서울 강동구 천호대로 1456 (상일동)
                      ...             
    32           서울 강남구 봉은사로 433 (삼성동)
    33                  서울 강남구 언주로 716
    34       서울특별시 강남구  봉은사로 311 (논현동)
    35           서울 강남구 도산대로 428 (청담동)
    36            서울 강남구 삼성로 521 (삼성동)
    Name: 주소, Length: 469, dtype: object




```python
stations['구'] = [eachAddress.split()[1] for eachAddress in stations['주소']] # 주소에서 각 구만 뽑아서 구 컬럼을 만들고 추가시켜준다.
stations 
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
      <th>상호</th>
      <th>주소</th>
      <th>가격</th>
      <th>셀프</th>
      <th>상표</th>
      <th>구</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>재건에너지 재정제2주유소 고속셀프지점</td>
      <td>서울특별시 강동구  천호대로 1246 (둔촌제2동)</td>
      <td>1769</td>
      <td>Y</td>
      <td>현대오일뱅크</td>
      <td>강동구</td>
    </tr>
    <tr>
      <th>1</th>
      <td>구천면주유소</td>
      <td>서울 강동구 구천면로 357 (암사동)</td>
      <td>1793</td>
      <td>N</td>
      <td>현대오일뱅크</td>
      <td>강동구</td>
    </tr>
    <tr>
      <th>2</th>
      <td>지에스칼텍스㈜ 신월주유소</td>
      <td>서울 강동구 양재대로 1323 (성내동)</td>
      <td>1808</td>
      <td>N</td>
      <td>GS칼텍스</td>
      <td>강동구</td>
    </tr>
    <tr>
      <th>3</th>
      <td>방아다리주유소</td>
      <td>서울 강동구 동남로 811 (명일동)</td>
      <td>1810</td>
      <td>Y</td>
      <td>SK에너지</td>
      <td>강동구</td>
    </tr>
    <tr>
      <th>4</th>
      <td>지에스칼텍스㈜ 동서울주유소</td>
      <td>서울 강동구 천호대로 1456 (상일동)</td>
      <td>1815</td>
      <td>Y</td>
      <td>GS칼텍스</td>
      <td>강동구</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>32</th>
      <td>(주)만정에너지</td>
      <td>서울 강남구 봉은사로 433 (삼성동)</td>
      <td>2298</td>
      <td>N</td>
      <td>GS칼텍스</td>
      <td>강남구</td>
    </tr>
    <tr>
      <th>33</th>
      <td>제이제이주유소</td>
      <td>서울 강남구 언주로 716</td>
      <td>2375</td>
      <td>N</td>
      <td>현대오일뱅크</td>
      <td>강남구</td>
    </tr>
    <tr>
      <th>34</th>
      <td>동우주유소</td>
      <td>서울특별시 강남구  봉은사로 311 (논현동)</td>
      <td>-</td>
      <td>N</td>
      <td>SK에너지</td>
      <td>강남구</td>
    </tr>
    <tr>
      <th>35</th>
      <td>경원주유소</td>
      <td>서울 강남구 도산대로 428 (청담동)</td>
      <td>-</td>
      <td>N</td>
      <td>S-OIL</td>
      <td>강남구</td>
    </tr>
    <tr>
      <th>36</th>
      <td>삼성주유소</td>
      <td>서울 강남구 삼성로 521 (삼성동)</td>
      <td>-</td>
      <td>N</td>
      <td>SK에너지</td>
      <td>강남구</td>
    </tr>
  </tbody>
</table>
<p>469 rows × 6 columns</p>
</div>




```python
stations['구'].unique(), len(stations['구'].unique())
```




    (array(['강동구', '동대문구', '동작구', '마포구', '서대문구', '서초구', '성동구', '성북구', '송파구',
            '양천구', '영등포구', '강북구', '용산구', '은평구', '종로구', '중구', '중랑구', '강서구',
            '관악구', '광진구', '구로구', '금천구', '노원구', '도봉구', '강남구'], dtype=object),
     25)




```python
# stations[stations['구'] == '서울특별시']
# stations.loc[stations['구'] == '서울특별시', '구'] = '성동구'
# stations[stations['구'] == '특별시']
# stations.loc[stations['구'] == '특별시', '구'] = '도봉구'

# 여기가 잘 이해가 안가긴 함
```


```python
# 가격 데이터형 변환 object => float

stations['가격'] = stations['가격'].astype('float')  # astype 을 이용해 기존 object(문자열) 을 float으로 바꿔줌
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    ~\AppData\Local\Temp/ipykernel_65764/703157356.py in <module>
          1 # 가격 데이터형 변환 object => float
          2 
    ----> 3 stations['가격'] = stations['가격'].astype('float')  # astype 을 이용해 기존 object(문자열) 을 float으로 바꿔줌
    

    ~\anaconda3\envs\ds_study\lib\site-packages\pandas\core\generic.py in astype(self, dtype, copy, errors)
       5918         else:
       5919             # else, only a single dtype is given
    -> 5920             new_data = self._mgr.astype(dtype=dtype, copy=copy, errors=errors)
       5921             return self._constructor(new_data).__finalize__(self, method="astype")
       5922 
    

    ~\anaconda3\envs\ds_study\lib\site-packages\pandas\core\internals\managers.py in astype(self, dtype, copy, errors)
        417 
        418     def astype(self: T, dtype, copy: bool = False, errors: str = "raise") -> T:
    --> 419         return self.apply("astype", dtype=dtype, copy=copy, errors=errors)
        420 
        421     def convert(
    

    ~\anaconda3\envs\ds_study\lib\site-packages\pandas\core\internals\managers.py in apply(self, f, align_keys, ignore_failures, **kwargs)
        302                     applied = b.apply(f, **kwargs)
        303                 else:
    --> 304                     applied = getattr(b, f)(**kwargs)
        305             except (TypeError, NotImplementedError):
        306                 if not ignore_failures:
    

    ~\anaconda3\envs\ds_study\lib\site-packages\pandas\core\internals\blocks.py in astype(self, dtype, copy, errors)
        578         values = self.values
        579 
    --> 580         new_values = astype_array_safe(values, dtype, copy=copy, errors=errors)
        581 
        582         new_values = maybe_coerce_values(new_values)
    

    ~\anaconda3\envs\ds_study\lib\site-packages\pandas\core\dtypes\cast.py in astype_array_safe(values, dtype, copy, errors)
       1290 
       1291     try:
    -> 1292         new_values = astype_array(values, dtype, copy=copy)
       1293     except (ValueError, TypeError):
       1294         # e.g. astype_nansafe can fail on object-dtype of strings
    

    ~\anaconda3\envs\ds_study\lib\site-packages\pandas\core\dtypes\cast.py in astype_array(values, dtype, copy)
       1235 
       1236     else:
    -> 1237         values = astype_nansafe(values, dtype, copy=copy)
       1238 
       1239     # in pandas we don't store numpy str dtypes, so convert to object
    

    ~\anaconda3\envs\ds_study\lib\site-packages\pandas\core\dtypes\cast.py in astype_nansafe(arr, dtype, copy, skipna)
       1179     if copy or is_object_dtype(arr.dtype) or is_object_dtype(dtype):
       1180         # Explicit copy, or required since NumPy can't view from / to object.
    -> 1181         return arr.astype(dtype, copy=True)
       1182 
       1183     return arr.astype(dtype, copy=copy)
    

    ValueError: could not convert string to float: '-'



```python
# 가격 정보가 빈 곳이 있었고 그곳에 가격대신 '-' 가 채워져 있었다.

stations[stations['가격'] == '-']
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
      <th>상호</th>
      <th>주소</th>
      <th>가격</th>
      <th>셀프</th>
      <th>상표</th>
      <th>구</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>27</th>
      <td>지에스칼텍스㈜ 화일주유소</td>
      <td>서울 영등포구 도림로 415</td>
      <td>-</td>
      <td>Y</td>
      <td>GS칼텍스</td>
      <td>영등포구</td>
    </tr>
    <tr>
      <th>16</th>
      <td>삼융주유소</td>
      <td>서울 은평구 수색로 299 (수색동)</td>
      <td>-</td>
      <td>N</td>
      <td>SK에너지</td>
      <td>은평구</td>
    </tr>
    <tr>
      <th>10</th>
      <td>지에스칼텍스(주)직영 역전점</td>
      <td>서울 중구 퇴계로 15</td>
      <td>-</td>
      <td>N</td>
      <td>GS칼텍스</td>
      <td>중구</td>
    </tr>
    <tr>
      <th>15</th>
      <td>구의스타주유소</td>
      <td>서울 광진구 자양로 103</td>
      <td>-</td>
      <td>N</td>
      <td>GS칼텍스</td>
      <td>광진구</td>
    </tr>
    <tr>
      <th>34</th>
      <td>동우주유소</td>
      <td>서울특별시 강남구  봉은사로 311 (논현동)</td>
      <td>-</td>
      <td>N</td>
      <td>SK에너지</td>
      <td>강남구</td>
    </tr>
    <tr>
      <th>35</th>
      <td>경원주유소</td>
      <td>서울 강남구 도산대로 428 (청담동)</td>
      <td>-</td>
      <td>N</td>
      <td>S-OIL</td>
      <td>강남구</td>
    </tr>
    <tr>
      <th>36</th>
      <td>삼성주유소</td>
      <td>서울 강남구 삼성로 521 (삼성동)</td>
      <td>-</td>
      <td>N</td>
      <td>SK에너지</td>
      <td>강남구</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 가격 정보가 있는 주유소만 사용

stations = stations[stations['가격'] != '-']
stations.tail()
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
      <th>상호</th>
      <th>주소</th>
      <th>가격</th>
      <th>셀프</th>
      <th>상표</th>
      <th>구</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>29</th>
      <td>갤러리아주유소</td>
      <td>서울 강남구 압구정로 426</td>
      <td>2243</td>
      <td>N</td>
      <td>SK에너지</td>
      <td>강남구</td>
    </tr>
    <tr>
      <th>30</th>
      <td>(주)소모에너지 쎈트럴주유소</td>
      <td>서울 강남구 삼성로 335</td>
      <td>2284</td>
      <td>N</td>
      <td>GS칼텍스</td>
      <td>강남구</td>
    </tr>
    <tr>
      <th>31</th>
      <td>SK논현주유소</td>
      <td>서울 강남구 논현로 747 (논현동)</td>
      <td>2285</td>
      <td>N</td>
      <td>SK에너지</td>
      <td>강남구</td>
    </tr>
    <tr>
      <th>32</th>
      <td>(주)만정에너지</td>
      <td>서울 강남구 봉은사로 433 (삼성동)</td>
      <td>2298</td>
      <td>N</td>
      <td>GS칼텍스</td>
      <td>강남구</td>
    </tr>
    <tr>
      <th>33</th>
      <td>제이제이주유소</td>
      <td>서울 강남구 언주로 716</td>
      <td>2375</td>
      <td>N</td>
      <td>현대오일뱅크</td>
      <td>강남구</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 다시 float으로 변환 진행
stations['가격'] = stations['가격'].astype('float')
```

    C:\Users\jcc96\AppData\Local\Temp/ipykernel_65764/786094376.py:1: SettingWithCopyWarning: 
    A value is trying to be set on a copy of a slice from a DataFrame.
    Try using .loc[row_indexer,col_indexer] = value instead
    
    See the caveats in the documentation: https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy
      stations['가격'] = stations['가격'].astype('float')
    


```python
stations.info()
```

    <class 'pandas.core.frame.DataFrame'>
    Int64Index: 462 entries, 0 to 33
    Data columns (total 6 columns):
     #   Column  Non-Null Count  Dtype  
    ---  ------  --------------  -----  
     0   상호      462 non-null    object 
     1   주소      462 non-null    object 
     2   가격      462 non-null    float64
     3   셀프      462 non-null    object 
     4   상표      462 non-null    object 
     5   구       462 non-null    object 
    dtypes: float64(1), object(5)
    memory usage: 25.3+ KB
    


```python
stations
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
      <th>상호</th>
      <th>주소</th>
      <th>가격</th>
      <th>셀프</th>
      <th>상표</th>
      <th>구</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>재건에너지 재정제2주유소 고속셀프지점</td>
      <td>서울특별시 강동구  천호대로 1246 (둔촌제2동)</td>
      <td>1769.0</td>
      <td>Y</td>
      <td>현대오일뱅크</td>
      <td>강동구</td>
    </tr>
    <tr>
      <th>1</th>
      <td>구천면주유소</td>
      <td>서울 강동구 구천면로 357 (암사동)</td>
      <td>1793.0</td>
      <td>N</td>
      <td>현대오일뱅크</td>
      <td>강동구</td>
    </tr>
    <tr>
      <th>2</th>
      <td>지에스칼텍스㈜ 신월주유소</td>
      <td>서울 강동구 양재대로 1323 (성내동)</td>
      <td>1808.0</td>
      <td>N</td>
      <td>GS칼텍스</td>
      <td>강동구</td>
    </tr>
    <tr>
      <th>3</th>
      <td>방아다리주유소</td>
      <td>서울 강동구 동남로 811 (명일동)</td>
      <td>1810.0</td>
      <td>Y</td>
      <td>SK에너지</td>
      <td>강동구</td>
    </tr>
    <tr>
      <th>4</th>
      <td>지에스칼텍스㈜ 동서울주유소</td>
      <td>서울 강동구 천호대로 1456 (상일동)</td>
      <td>1815.0</td>
      <td>Y</td>
      <td>GS칼텍스</td>
      <td>강동구</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>29</th>
      <td>갤러리아주유소</td>
      <td>서울 강남구 압구정로 426</td>
      <td>2243.0</td>
      <td>N</td>
      <td>SK에너지</td>
      <td>강남구</td>
    </tr>
    <tr>
      <th>30</th>
      <td>(주)소모에너지 쎈트럴주유소</td>
      <td>서울 강남구 삼성로 335</td>
      <td>2284.0</td>
      <td>N</td>
      <td>GS칼텍스</td>
      <td>강남구</td>
    </tr>
    <tr>
      <th>31</th>
      <td>SK논현주유소</td>
      <td>서울 강남구 논현로 747 (논현동)</td>
      <td>2285.0</td>
      <td>N</td>
      <td>SK에너지</td>
      <td>강남구</td>
    </tr>
    <tr>
      <th>32</th>
      <td>(주)만정에너지</td>
      <td>서울 강남구 봉은사로 433 (삼성동)</td>
      <td>2298.0</td>
      <td>N</td>
      <td>GS칼텍스</td>
      <td>강남구</td>
    </tr>
    <tr>
      <th>33</th>
      <td>제이제이주유소</td>
      <td>서울 강남구 언주로 716</td>
      <td>2375.0</td>
      <td>N</td>
      <td>현대오일뱅크</td>
      <td>강남구</td>
    </tr>
  </tbody>
</table>
<p>462 rows × 6 columns</p>
</div>




```python
# 인덱스 재정렬

stations.reset_index(inplace=True)
stations.tail()

# 이번에는 index 값이 461까지 총 462개 잘 찍혀있음을 확인 가능하다.
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
      <th>index</th>
      <th>상호</th>
      <th>주소</th>
      <th>가격</th>
      <th>셀프</th>
      <th>상표</th>
      <th>구</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>457</th>
      <td>29</td>
      <td>갤러리아주유소</td>
      <td>서울 강남구 압구정로 426</td>
      <td>2243.0</td>
      <td>N</td>
      <td>SK에너지</td>
      <td>강남구</td>
    </tr>
    <tr>
      <th>458</th>
      <td>30</td>
      <td>(주)소모에너지 쎈트럴주유소</td>
      <td>서울 강남구 삼성로 335</td>
      <td>2284.0</td>
      <td>N</td>
      <td>GS칼텍스</td>
      <td>강남구</td>
    </tr>
    <tr>
      <th>459</th>
      <td>31</td>
      <td>SK논현주유소</td>
      <td>서울 강남구 논현로 747 (논현동)</td>
      <td>2285.0</td>
      <td>N</td>
      <td>SK에너지</td>
      <td>강남구</td>
    </tr>
    <tr>
      <th>460</th>
      <td>32</td>
      <td>(주)만정에너지</td>
      <td>서울 강남구 봉은사로 433 (삼성동)</td>
      <td>2298.0</td>
      <td>N</td>
      <td>GS칼텍스</td>
      <td>강남구</td>
    </tr>
    <tr>
      <th>461</th>
      <td>33</td>
      <td>제이제이주유소</td>
      <td>서울 강남구 언주로 716</td>
      <td>2375.0</td>
      <td>N</td>
      <td>현대오일뱅크</td>
      <td>강남구</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 이제 원래 있던 33번이 마지막으로 되어있는 잘못된 index 를 지워준다.
del stations['index']
stations.head()
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
      <th>상호</th>
      <th>주소</th>
      <th>가격</th>
      <th>셀프</th>
      <th>상표</th>
      <th>구</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>재건에너지 재정제2주유소 고속셀프지점</td>
      <td>서울특별시 강동구  천호대로 1246 (둔촌제2동)</td>
      <td>1769.0</td>
      <td>Y</td>
      <td>현대오일뱅크</td>
      <td>강동구</td>
    </tr>
    <tr>
      <th>1</th>
      <td>구천면주유소</td>
      <td>서울 강동구 구천면로 357 (암사동)</td>
      <td>1793.0</td>
      <td>N</td>
      <td>현대오일뱅크</td>
      <td>강동구</td>
    </tr>
    <tr>
      <th>2</th>
      <td>지에스칼텍스㈜ 신월주유소</td>
      <td>서울 강동구 양재대로 1323 (성내동)</td>
      <td>1808.0</td>
      <td>N</td>
      <td>GS칼텍스</td>
      <td>강동구</td>
    </tr>
    <tr>
      <th>3</th>
      <td>방아다리주유소</td>
      <td>서울 강동구 동남로 811 (명일동)</td>
      <td>1810.0</td>
      <td>Y</td>
      <td>SK에너지</td>
      <td>강동구</td>
    </tr>
    <tr>
      <th>4</th>
      <td>지에스칼텍스㈜ 동서울주유소</td>
      <td>서울 강동구 천호대로 1456 (상일동)</td>
      <td>1815.0</td>
      <td>Y</td>
      <td>GS칼텍스</td>
      <td>강동구</td>
    </tr>
  </tbody>
</table>
</div>




```python
stations.tail()
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
      <th>상호</th>
      <th>주소</th>
      <th>가격</th>
      <th>셀프</th>
      <th>상표</th>
      <th>구</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>457</th>
      <td>갤러리아주유소</td>
      <td>서울 강남구 압구정로 426</td>
      <td>2243.0</td>
      <td>N</td>
      <td>SK에너지</td>
      <td>강남구</td>
    </tr>
    <tr>
      <th>458</th>
      <td>(주)소모에너지 쎈트럴주유소</td>
      <td>서울 강남구 삼성로 335</td>
      <td>2284.0</td>
      <td>N</td>
      <td>GS칼텍스</td>
      <td>강남구</td>
    </tr>
    <tr>
      <th>459</th>
      <td>SK논현주유소</td>
      <td>서울 강남구 논현로 747 (논현동)</td>
      <td>2285.0</td>
      <td>N</td>
      <td>SK에너지</td>
      <td>강남구</td>
    </tr>
    <tr>
      <th>460</th>
      <td>(주)만정에너지</td>
      <td>서울 강남구 봉은사로 433 (삼성동)</td>
      <td>2298.0</td>
      <td>N</td>
      <td>GS칼텍스</td>
      <td>강남구</td>
    </tr>
    <tr>
      <th>461</th>
      <td>제이제이주유소</td>
      <td>서울 강남구 언주로 716</td>
      <td>2375.0</td>
      <td>N</td>
      <td>현대오일뱅크</td>
      <td>강남구</td>
    </tr>
  </tbody>
</table>
</div>



### 5. 주유 가격 정보 시각화


```python
import matplotlib.pyplot as plt
import seaborn as sns
import platform
from matplotlib import font_manager, rc

get_ipython().run_line_magic('matplotlib', 'inline')

path = 'C:/Windows/Fonts/malgun.ttf'

if platform.system() == 'Darwin':
    rc('font', family = 'Arial Unicode MS')
elif platform.system() == 'Windows':
    font_name = font_manager.FontProperties(fname=path).get_name()
    rc('font', family=font_name)
else:
    print('Unkown system')
    

       
```


```python
# boxplot(feat. pandas)

stations.boxplot(column='가격', by='셀프', figsize=(12,8)) # 박스 플롯 가져온다

# 해석 중요
```




    <AxesSubplot:title={'center':'가격'}, xlabel='셀프'>




    
![png](output_63_1.png)
    



```python
# boxplot(feat. seaborn)

plt.figure(figsize=(12,8))
sns.boxplot(x='셀프', y='가격', data = stations, palette='Set1')
plt.grid(True)
plt.show()
```


    
![png](output_64_0.png)
    



```python
# boxplot(feat. seaborn)

plt.figure(figsize=(12,8))
sns.boxplot(x='상표', y='가격', hue='셀프', data=stations, palette='Set1' , )
plt.grid(True)
plt.show()
```


    
![png](output_65_0.png)
    



```python
# 지도 시각화
```


```python
import json
import folium
import warnings # 경고문구가 나타나지 않음 / 어떤 경고 말하는거지?
warnings.simplefilter(action='ignore', category=FutureWarning)
```


```python
# 가장 비싼 주유소 5개
stations.sort_values(by='가격', ascending=False).head()
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
      <th>상호</th>
      <th>주소</th>
      <th>가격</th>
      <th>셀프</th>
      <th>상표</th>
      <th>구</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>287</th>
      <td>서남주유소</td>
      <td>서울 중구 통일로 30</td>
      <td>2631.0</td>
      <td>N</td>
      <td>SK에너지</td>
      <td>중구</td>
    </tr>
    <tr>
      <th>253</th>
      <td>서계주유소</td>
      <td>서울특별시 용산구  청파로 367 (청파동)</td>
      <td>2630.0</td>
      <td>N</td>
      <td>GS칼텍스</td>
      <td>용산구</td>
    </tr>
    <tr>
      <th>286</th>
      <td>필동주유소</td>
      <td>서울 중구  퇴계로 196 (필동2가)</td>
      <td>2429.0</td>
      <td>N</td>
      <td>GS칼텍스</td>
      <td>중구</td>
    </tr>
    <tr>
      <th>285</th>
      <td>SK에너지(주) 퇴계로주유소</td>
      <td>서울 중구 퇴계로 228 (필동2가)</td>
      <td>2394.0</td>
      <td>N</td>
      <td>SK에너지</td>
      <td>중구</td>
    </tr>
    <tr>
      <th>461</th>
      <td>제이제이주유소</td>
      <td>서울 강남구 언주로 716</td>
      <td>2375.0</td>
      <td>N</td>
      <td>현대오일뱅크</td>
      <td>강남구</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 가장 싼 주유소
stations.sort_values(by='가격').head()
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
      <th>상호</th>
      <th>주소</th>
      <th>가격</th>
      <th>셀프</th>
      <th>상표</th>
      <th>구</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>70</th>
      <td>만남의광장주유소</td>
      <td>서울 서초구 양재대로12길 73-71</td>
      <td>1714.0</td>
      <td>Y</td>
      <td>알뜰(ex)</td>
      <td>서초구</td>
    </tr>
    <tr>
      <th>176</th>
      <td>(주)타이거오일 신정주유소</td>
      <td>서울 양천구 중앙로 226 (신정동)</td>
      <td>1714.0</td>
      <td>Y</td>
      <td>SK에너지</td>
      <td>양천구</td>
    </tr>
    <tr>
      <th>177</th>
      <td>현대주유소</td>
      <td>서울 양천구 남부순환로 372 (신월동)</td>
      <td>1714.0</td>
      <td>Y</td>
      <td>S-OIL</td>
      <td>양천구</td>
    </tr>
    <tr>
      <th>411</th>
      <td>(주)헨지스에너지 구도일주유소 도봉</td>
      <td>서울 도봉구 도봉로 706 (방학동)</td>
      <td>1715.0</td>
      <td>Y</td>
      <td>S-OIL</td>
      <td>도봉구</td>
    </tr>
    <tr>
      <th>410</th>
      <td>(주)자연에너지 햇살주유소</td>
      <td>서울 도봉구 방학로 142 (방학동)</td>
      <td>1715.0</td>
      <td>Y</td>
      <td>현대오일뱅크</td>
      <td>도봉구</td>
    </tr>
  </tbody>
</table>
</div>




```python
import numpy as np

gu_data = pd.pivot_table(data=stations, index='구', values='가격', aggfunc=np.mean)
gu_data.head()
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
      <th>가격</th>
    </tr>
    <tr>
      <th>구</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>강남구</th>
      <td>1970.941176</td>
    </tr>
    <tr>
      <th>강동구</th>
      <td>1840.214286</td>
    </tr>
    <tr>
      <th>강북구</th>
      <td>1766.769231</td>
    </tr>
    <tr>
      <th>강서구</th>
      <td>1793.437500</td>
    </tr>
    <tr>
      <th>관악구</th>
      <td>1821.928571</td>
    </tr>
  </tbody>
</table>
</div>




```python
geo_path = '../data/02. skorea_municipalities_geo_simple.json'
geo_str = json.load(open(geo_path, encoding='utf-8'))

my_map = folium.Map(location=[37.5502, 126.982], zoom_start=10.5, tiles='Stamen Toner')
my_map.choropleth(
    geo_data = geo_str,
    data=gu_data,
    columns = [gu_data.index, '가격'],
    key_on = 'feature.id',
    fill_color = 'PuRd'
)
my_map
```




<div style="width:100%;">
  <div style="position:relative;width:100%;height:0;padding-bottom:60%;">
    <span style="color:#565656">Make this Notebook Trusted to load map: File -> Trust Notebook</span>
    <iframe src="about:blank" style="position:absolute;width:100%;height:100%;left:0;top:0;border:none !important;" data-html=%3C%21DOCTYPE%20html%3E%0A%3Chead%3E%20%20%20%20%0A%20%20%20%20%3Cmeta%20http-equiv%3D%22content-type%22%20content%3D%22text/html%3B%20charset%3DUTF-8%22%20/%3E%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%3Cscript%3E%0A%20%20%20%20%20%20%20%20%20%20%20%20L_NO_TOUCH%20%3D%20false%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20L_DISABLE_3D%20%3D%20false%3B%0A%20%20%20%20%20%20%20%20%3C/script%3E%0A%20%20%20%20%0A%20%20%20%20%3Cstyle%3Ehtml%2C%20body%20%7Bwidth%3A%20100%25%3Bheight%3A%20100%25%3Bmargin%3A%200%3Bpadding%3A%200%3B%7D%3C/style%3E%0A%20%20%20%20%3Cstyle%3E%23map%20%7Bposition%3Aabsolute%3Btop%3A0%3Bbottom%3A0%3Bright%3A0%3Bleft%3A0%3B%7D%3C/style%3E%0A%20%20%20%20%3Cscript%20src%3D%22https%3A//cdn.jsdelivr.net/npm/leaflet%401.6.0/dist/leaflet.js%22%3E%3C/script%3E%0A%20%20%20%20%3Cscript%20src%3D%22https%3A//code.jquery.com/jquery-1.12.4.min.js%22%3E%3C/script%3E%0A%20%20%20%20%3Cscript%20src%3D%22https%3A//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/js/bootstrap.min.js%22%3E%3C/script%3E%0A%20%20%20%20%3Cscript%20src%3D%22https%3A//cdnjs.cloudflare.com/ajax/libs/Leaflet.awesome-markers/2.0.2/leaflet.awesome-markers.js%22%3E%3C/script%3E%0A%20%20%20%20%3Clink%20rel%3D%22stylesheet%22%20href%3D%22https%3A//cdn.jsdelivr.net/npm/leaflet%401.6.0/dist/leaflet.css%22/%3E%0A%20%20%20%20%3Clink%20rel%3D%22stylesheet%22%20href%3D%22https%3A//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css%22/%3E%0A%20%20%20%20%3Clink%20rel%3D%22stylesheet%22%20href%3D%22https%3A//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap-theme.min.css%22/%3E%0A%20%20%20%20%3Clink%20rel%3D%22stylesheet%22%20href%3D%22https%3A//maxcdn.bootstrapcdn.com/font-awesome/4.6.3/css/font-awesome.min.css%22/%3E%0A%20%20%20%20%3Clink%20rel%3D%22stylesheet%22%20href%3D%22https%3A//cdnjs.cloudflare.com/ajax/libs/Leaflet.awesome-markers/2.0.2/leaflet.awesome-markers.css%22/%3E%0A%20%20%20%20%3Clink%20rel%3D%22stylesheet%22%20href%3D%22https%3A//cdn.jsdelivr.net/gh/python-visualization/folium/folium/templates/leaflet.awesome.rotate.min.css%22/%3E%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20%3Cmeta%20name%3D%22viewport%22%20content%3D%22width%3Ddevice-width%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20initial-scale%3D1.0%2C%20maximum-scale%3D1.0%2C%20user-scalable%3Dno%22%20/%3E%0A%20%20%20%20%20%20%20%20%20%20%20%20%3Cstyle%3E%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%23map_de70fb954f834b8ca105f09bf9b18e69%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20position%3A%20relative%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20width%3A%20100.0%25%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20height%3A%20100.0%25%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20left%3A%200.0%25%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20top%3A%200.0%25%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%3C/style%3E%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%3Cscript%20src%3D%22https%3A//cdnjs.cloudflare.com/ajax/libs/d3/3.5.5/d3.min.js%22%3E%3C/script%3E%0A%3C/head%3E%0A%3Cbody%3E%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20%3Cdiv%20class%3D%22folium-map%22%20id%3D%22map_de70fb954f834b8ca105f09bf9b18e69%22%20%3E%3C/div%3E%0A%20%20%20%20%20%20%20%20%0A%3C/body%3E%0A%3Cscript%3E%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20map_de70fb954f834b8ca105f09bf9b18e69%20%3D%20L.map%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%22map_de70fb954f834b8ca105f09bf9b18e69%22%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20center%3A%20%5B37.5502%2C%20126.982%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20crs%3A%20L.CRS.EPSG3857%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20zoom%3A%2010.5%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20zoomControl%3A%20true%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20preferCanvas%3A%20false%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29%3B%0A%0A%20%20%20%20%20%20%20%20%20%20%20%20%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20tile_layer_0663ee7bbe364b78a4d096934d3d1d48%20%3D%20L.tileLayer%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%22https%3A//stamen-tiles-%7Bs%7D.a.ssl.fastly.net/toner/%7Bz%7D/%7Bx%7D/%7By%7D.png%22%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%22attribution%22%3A%20%22Map%20tiles%20by%20%5Cu003ca%20href%3D%5C%22http%3A//stamen.com%5C%22%5Cu003eStamen%20Design%5Cu003c/a%5Cu003e%2C%20under%20%5Cu003ca%20href%3D%5C%22http%3A//creativecommons.org/licenses/by/3.0%5C%22%5Cu003eCC%20BY%203.0%5Cu003c/a%5Cu003e.%20Data%20by%20%5Cu0026copy%3B%20%5Cu003ca%20href%3D%5C%22http%3A//openstreetmap.org%5C%22%5Cu003eOpenStreetMap%5Cu003c/a%5Cu003e%2C%20under%20%5Cu003ca%20href%3D%5C%22http%3A//www.openstreetmap.org/copyright%5C%22%5Cu003eODbL%5Cu003c/a%5Cu003e.%22%2C%20%22detectRetina%22%3A%20false%2C%20%22maxNativeZoom%22%3A%2018%2C%20%22maxZoom%22%3A%2018%2C%20%22minZoom%22%3A%200%2C%20%22noWrap%22%3A%20false%2C%20%22opacity%22%3A%201%2C%20%22subdomains%22%3A%20%22abc%22%2C%20%22tms%22%3A%20false%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_de70fb954f834b8ca105f09bf9b18e69%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20var%20choropleth_26451781925f421dbdb5ca42cbb0f119%20%3D%20L.featureGroup%28%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7B%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20%29.addTo%28map_de70fb954f834b8ca105f09bf9b18e69%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%20%20function%20geo_json_6ce8523f02c149d9a1449280d0c9496b_styler%28feature%29%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20switch%28feature.id%29%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20case%20%22%5Cuac15%5Cub3d9%5Cuad6c%22%3A%20case%20%22%5Cuc11c%5Cucd08%5Cuad6c%22%3A%20case%20%22%5Cuc601%5Cub4f1%5Cud3ec%5Cuad6c%22%3A%20case%20%22%5Cub9c8%5Cud3ec%5Cuad6c%22%3A%20case%20%22%5Cuc131%5Cub3d9%5Cuad6c%22%3A%20%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20return%20%7B%22color%22%3A%20%22black%22%2C%20%22fillColor%22%3A%20%22%23d4b9da%22%2C%20%22fillOpacity%22%3A%200.6%2C%20%22opacity%22%3A%201%2C%20%22weight%22%3A%201%7D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20case%20%22%5Cuac15%5Cub0a8%5Cuad6c%22%3A%20%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20return%20%7B%22color%22%3A%20%22black%22%2C%20%22fillColor%22%3A%20%22%23c994c7%22%2C%20%22fillOpacity%22%3A%200.6%2C%20%22opacity%22%3A%201%2C%20%22weight%22%3A%201%7D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20case%20%22%5Cuc6a9%5Cuc0b0%5Cuad6c%22%3A%20case%20%22%5Cuc911%5Cuad6c%22%3A%20%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20return%20%7B%22color%22%3A%20%22black%22%2C%20%22fillColor%22%3A%20%22%23980043%22%2C%20%22fillOpacity%22%3A%200.6%2C%20%22opacity%22%3A%201%2C%20%22weight%22%3A%201%7D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20case%20%22%5Cuc885%5Cub85c%5Cuad6c%22%3A%20%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20return%20%7B%22color%22%3A%20%22black%22%2C%20%22fillColor%22%3A%20%22%23df65b0%22%2C%20%22fillOpacity%22%3A%200.6%2C%20%22opacity%22%3A%201%2C%20%22weight%22%3A%201%7D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20default%3A%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20return%20%7B%22color%22%3A%20%22black%22%2C%20%22fillColor%22%3A%20%22%23f1eef6%22%2C%20%22fillOpacity%22%3A%200.6%2C%20%22opacity%22%3A%201%2C%20%22weight%22%3A%201%7D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%7D%0A%0A%20%20%20%20%20%20%20%20function%20geo_json_6ce8523f02c149d9a1449280d0c9496b_onEachFeature%28feature%2C%20layer%29%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20layer.on%28%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%7D%29%3B%0A%20%20%20%20%20%20%20%20%7D%3B%0A%20%20%20%20%20%20%20%20var%20geo_json_6ce8523f02c149d9a1449280d0c9496b%20%3D%20L.geoJson%28null%2C%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20onEachFeature%3A%20geo_json_6ce8523f02c149d9a1449280d0c9496b_onEachFeature%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20style%3A%20geo_json_6ce8523f02c149d9a1449280d0c9496b_styler%2C%0A%20%20%20%20%20%20%20%20%7D%29%3B%0A%0A%20%20%20%20%20%20%20%20function%20geo_json_6ce8523f02c149d9a1449280d0c9496b_add%20%28data%29%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20geo_json_6ce8523f02c149d9a1449280d0c9496b%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20.addData%28data%29%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20.addTo%28choropleth_26451781925f421dbdb5ca42cbb0f119%29%3B%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20geo_json_6ce8523f02c149d9a1449280d0c9496b_add%28%7B%22features%22%3A%20%5B%7B%22geometry%22%3A%20%7B%22coordinates%22%3A%20%5B%5B%5B127.11519584981606%2C%2037.557533180704915%5D%2C%20%5B127.16683184366129%2C%2037.57672487388627%5D%2C%20%5B127.18408792330152%2C%2037.55814280369575%5D%2C%20%5B127.16530984307447%2C%2037.54221851258693%5D%2C%20%5B127.14672806823502%2C%2037.51415680680291%5D%2C%20%5B127.12123165719615%2C%2037.52528270089%5D%2C%20%5B127.1116764203608%2C%2037.540669955324965%5D%2C%20%5B127.11519584981606%2C%2037.557533180704915%5D%5D%5D%2C%20%22type%22%3A%20%22Polygon%22%7D%2C%20%22id%22%3A%20%22%5Cuac15%5Cub3d9%5Cuad6c%22%2C%20%22properties%22%3A%20%7B%22base_year%22%3A%20%222013%22%2C%20%22code%22%3A%20%2211250%22%2C%20%22name%22%3A%20%22%5Cuac15%5Cub3d9%5Cuad6c%22%2C%20%22name_eng%22%3A%20%22Gangdong-gu%22%7D%2C%20%22type%22%3A%20%22Feature%22%7D%2C%20%7B%22geometry%22%3A%20%7B%22coordinates%22%3A%20%5B%5B%5B127.0690698130372%2C%2037.522279423505026%5D%2C%20%5B127.10087519791962%2C%2037.524841220167055%5D%2C%20%5B127.1116764203608%2C%2037.540669955324965%5D%2C%20%5B127.12123165719615%2C%2037.52528270089%5D%2C%20%5B127.14672806823502%2C%2037.51415680680291%5D%2C%20%5B127.1634944215765%2C%2037.497445406097484%5D%2C%20%5B127.14206058413274%2C%2037.47089819098501%5D%2C%20%5B127.12440571080893%2C%2037.46240445587048%5D%2C%20%5B127.11117085201238%2C%2037.485708381512445%5D%2C%20%5B127.0719146000724%2C%2037.50224013587669%5D%2C%20%5B127.0690698130372%2C%2037.522279423505026%5D%5D%5D%2C%20%22type%22%3A%20%22Polygon%22%7D%2C%20%22id%22%3A%20%22%5Cuc1a1%5Cud30c%5Cuad6c%22%2C%20%22properties%22%3A%20%7B%22base_year%22%3A%20%222013%22%2C%20%22code%22%3A%20%2211240%22%2C%20%22name%22%3A%20%22%5Cuc1a1%5Cud30c%5Cuad6c%22%2C%20%22name_eng%22%3A%20%22Songpa-gu%22%7D%2C%20%22type%22%3A%20%22Feature%22%7D%2C%20%7B%22geometry%22%3A%20%7B%22coordinates%22%3A%20%5B%5B%5B127.05867359288398%2C%2037.52629974922568%5D%2C%20%5B127.0690698130372%2C%2037.522279423505026%5D%2C%20%5B127.0719146000724%2C%2037.50224013587669%5D%2C%20%5B127.11117085201238%2C%2037.485708381512445%5D%2C%20%5B127.12440571080893%2C%2037.46240445587048%5D%2C%20%5B127.09842759318751%2C%2037.45862253857461%5D%2C%20%5B127.08640440578156%2C%2037.472697935184655%5D%2C%20%5B127.0559170481904%2C%2037.4659228914077%5D%2C%20%5B127.03621915098798%2C%2037.48175802427603%5D%2C%20%5B127.01397119667513%2C%2037.52503988289669%5D%2C%20%5B127.02302831890559%2C%2037.53231899582663%5D%2C%20%5B127.05867359288398%2C%2037.52629974922568%5D%5D%5D%2C%20%22type%22%3A%20%22Polygon%22%7D%2C%20%22id%22%3A%20%22%5Cuac15%5Cub0a8%5Cuad6c%22%2C%20%22properties%22%3A%20%7B%22base_year%22%3A%20%222013%22%2C%20%22code%22%3A%20%2211230%22%2C%20%22name%22%3A%20%22%5Cuac15%5Cub0a8%5Cuad6c%22%2C%20%22name_eng%22%3A%20%22Gangnam-gu%22%7D%2C%20%22type%22%3A%20%22Feature%22%7D%2C%20%7B%22geometry%22%3A%20%7B%22coordinates%22%3A%20%5B%5B%5B127.01397119667513%2C%2037.52503988289669%5D%2C%20%5B127.03621915098798%2C%2037.48175802427603%5D%2C%20%5B127.0559170481904%2C%2037.4659228914077%5D%2C%20%5B127.08640440578156%2C%2037.472697935184655%5D%2C%20%5B127.09842759318751%2C%2037.45862253857461%5D%2C%20%5B127.09046928565951%2C%2037.44296826114185%5D%2C%20%5B127.06778107605433%2C%2037.426197424057314%5D%2C%20%5B127.04957232987142%2C%2037.42805836845694%5D%2C%20%5B127.03881782597922%2C%2037.45382039851715%5D%2C%20%5B126.99072073195462%2C%2037.455326143310025%5D%2C%20%5B126.98367668291802%2C%2037.473856492692086%5D%2C%20%5B126.98223807916081%2C%2037.509314966770326%5D%2C%20%5B127.01397119667513%2C%2037.52503988289669%5D%5D%5D%2C%20%22type%22%3A%20%22Polygon%22%7D%2C%20%22id%22%3A%20%22%5Cuc11c%5Cucd08%5Cuad6c%22%2C%20%22properties%22%3A%20%7B%22base_year%22%3A%20%222013%22%2C%20%22code%22%3A%20%2211220%22%2C%20%22name%22%3A%20%22%5Cuc11c%5Cucd08%5Cuad6c%22%2C%20%22name_eng%22%3A%20%22Seocho-gu%22%7D%2C%20%22type%22%3A%20%22Feature%22%7D%2C%20%7B%22geometry%22%3A%20%7B%22coordinates%22%3A%20%5B%5B%5B126.98367668291802%2C%2037.473856492692086%5D%2C%20%5B126.99072073195462%2C%2037.455326143310025%5D%2C%20%5B126.96520439085143%2C%2037.438249784006246%5D%2C%20%5B126.95000001010182%2C%2037.43613451165719%5D%2C%20%5B126.93084408056525%2C%2037.447382928333994%5D%2C%20%5B126.9167728146601%2C%2037.45490566423789%5D%2C%20%5B126.90156094129895%2C%2037.47753842789901%5D%2C%20%5B126.90531975801812%2C%2037.48218087575429%5D%2C%20%5B126.94922661389508%2C%2037.49125437495649%5D%2C%20%5B126.9725891850662%2C%2037.472561363278125%5D%2C%20%5B126.98367668291802%2C%2037.473856492692086%5D%5D%5D%2C%20%22type%22%3A%20%22Polygon%22%7D%2C%20%22id%22%3A%20%22%5Cuad00%5Cuc545%5Cuad6c%22%2C%20%22properties%22%3A%20%7B%22base_year%22%3A%20%222013%22%2C%20%22code%22%3A%20%2211210%22%2C%20%22name%22%3A%20%22%5Cuad00%5Cuc545%5Cuad6c%22%2C%20%22name_eng%22%3A%20%22Gwanak-gu%22%7D%2C%20%22type%22%3A%20%22Feature%22%7D%2C%20%7B%22geometry%22%3A%20%7B%22coordinates%22%3A%20%5B%5B%5B126.98223807916081%2C%2037.509314966770326%5D%2C%20%5B126.98367668291802%2C%2037.473856492692086%5D%2C%20%5B126.9725891850662%2C%2037.472561363278125%5D%2C%20%5B126.94922661389508%2C%2037.49125437495649%5D%2C%20%5B126.90531975801812%2C%2037.48218087575429%5D%2C%20%5B126.92177893174825%2C%2037.494889877415176%5D%2C%20%5B126.92810628828279%2C%2037.51329595732015%5D%2C%20%5B126.95249990298159%2C%2037.51722500741813%5D%2C%20%5B126.98223807916081%2C%2037.509314966770326%5D%5D%5D%2C%20%22type%22%3A%20%22Polygon%22%7D%2C%20%22id%22%3A%20%22%5Cub3d9%5Cuc791%5Cuad6c%22%2C%20%22properties%22%3A%20%7B%22base_year%22%3A%20%222013%22%2C%20%22code%22%3A%20%2211200%22%2C%20%22name%22%3A%20%22%5Cub3d9%5Cuc791%5Cuad6c%22%2C%20%22name_eng%22%3A%20%22Dongjak-gu%22%7D%2C%20%22type%22%3A%20%22Feature%22%7D%2C%20%7B%22geometry%22%3A%20%7B%22coordinates%22%3A%20%5B%5B%5B126.89184663862764%2C%2037.547373974997114%5D%2C%20%5B126.94566733083212%2C%2037.526617542453366%5D%2C%20%5B126.95249990298159%2C%2037.51722500741813%5D%2C%20%5B126.92810628828279%2C%2037.51329595732015%5D%2C%20%5B126.92177893174825%2C%2037.494889877415176%5D%2C%20%5B126.90531975801812%2C%2037.48218087575429%5D%2C%20%5B126.89594776782485%2C%2037.504675281309176%5D%2C%20%5B126.88156402353862%2C%2037.513970034765684%5D%2C%20%5B126.88825757860099%2C%2037.54079733630232%5D%2C%20%5B126.89184663862764%2C%2037.547373974997114%5D%5D%5D%2C%20%22type%22%3A%20%22Polygon%22%7D%2C%20%22id%22%3A%20%22%5Cuc601%5Cub4f1%5Cud3ec%5Cuad6c%22%2C%20%22properties%22%3A%20%7B%22base_year%22%3A%20%222013%22%2C%20%22code%22%3A%20%2211190%22%2C%20%22name%22%3A%20%22%5Cuc601%5Cub4f1%5Cud3ec%5Cuad6c%22%2C%20%22name_eng%22%3A%20%22Yeongdeungpo-gu%22%7D%2C%20%22type%22%3A%20%22Feature%22%7D%2C%20%7B%22geometry%22%3A%20%7B%22coordinates%22%3A%20%5B%5B%5B126.90156094129895%2C%2037.47753842789901%5D%2C%20%5B126.9167728146601%2C%2037.45490566423789%5D%2C%20%5B126.93084408056525%2C%2037.447382928333994%5D%2C%20%5B126.9025831711697%2C%2037.434549366349124%5D%2C%20%5B126.87683271502428%2C%2037.482576591607305%5D%2C%20%5B126.90156094129895%2C%2037.47753842789901%5D%5D%5D%2C%20%22type%22%3A%20%22Polygon%22%7D%2C%20%22id%22%3A%20%22%5Cuae08%5Cucc9c%5Cuad6c%22%2C%20%22properties%22%3A%20%7B%22base_year%22%3A%20%222013%22%2C%20%22code%22%3A%20%2211180%22%2C%20%22name%22%3A%20%22%5Cuae08%5Cucc9c%5Cuad6c%22%2C%20%22name_eng%22%3A%20%22Geumcheon-gu%22%7D%2C%20%22type%22%3A%20%22Feature%22%7D%2C%20%7B%22geometry%22%3A%20%7B%22coordinates%22%3A%20%5B%5B%5B126.82688081517314%2C%2037.50548972232896%5D%2C%20%5B126.88156402353862%2C%2037.513970034765684%5D%2C%20%5B126.89594776782485%2C%2037.504675281309176%5D%2C%20%5B126.90531975801812%2C%2037.48218087575429%5D%2C%20%5B126.90156094129895%2C%2037.47753842789901%5D%2C%20%5B126.87683271502428%2C%2037.482576591607305%5D%2C%20%5B126.84762676054953%2C%2037.47146723936323%5D%2C%20%5B126.83549485076196%2C%2037.474098236975095%5D%2C%20%5B126.82264796791348%2C%2037.4878476492147%5D%2C%20%5B126.82504736331406%2C%2037.50302612640443%5D%2C%20%5B126.82688081517314%2C%2037.50548972232896%5D%5D%5D%2C%20%22type%22%3A%20%22Polygon%22%7D%2C%20%22id%22%3A%20%22%5Cuad6c%5Cub85c%5Cuad6c%22%2C%20%22properties%22%3A%20%7B%22base_year%22%3A%20%222013%22%2C%20%22code%22%3A%20%2211170%22%2C%20%22name%22%3A%20%22%5Cuad6c%5Cub85c%5Cuad6c%22%2C%20%22name_eng%22%3A%20%22Guro-gu%22%7D%2C%20%22type%22%3A%20%22Feature%22%7D%2C%20%7B%22geometry%22%3A%20%7B%22coordinates%22%3A%20%5B%5B%5B126.79575768552907%2C%2037.57881087633202%5D%2C%20%5B126.80702115023597%2C%2037.60123001013228%5D%2C%20%5B126.82251438477105%2C%2037.5880430810082%5D%2C%20%5B126.85984199399667%2C%2037.571847855292745%5D%2C%20%5B126.89184663862764%2C%2037.547373974997114%5D%2C%20%5B126.88825757860099%2C%2037.54079733630232%5D%2C%20%5B126.86637464321238%2C%2037.54859191094823%5D%2C%20%5B126.86610073476395%2C%2037.52699964144669%5D%2C%20%5B126.84257291943153%2C%2037.52373707805596%5D%2C%20%5B126.8242331426722%2C%2037.53788078753248%5D%2C%20%5B126.77324417717703%2C%2037.5459123450554%5D%2C%20%5B126.76979180579352%2C%2037.55139183008809%5D%2C%20%5B126.79575768552907%2C%2037.57881087633202%5D%5D%5D%2C%20%22type%22%3A%20%22Polygon%22%7D%2C%20%22id%22%3A%20%22%5Cuac15%5Cuc11c%5Cuad6c%22%2C%20%22properties%22%3A%20%7B%22base_year%22%3A%20%222013%22%2C%20%22code%22%3A%20%2211160%22%2C%20%22name%22%3A%20%22%5Cuac15%5Cuc11c%5Cuad6c%22%2C%20%22name_eng%22%3A%20%22Gangseo-gu%22%7D%2C%20%22type%22%3A%20%22Feature%22%7D%2C%20%7B%22geometry%22%3A%20%7B%22coordinates%22%3A%20%5B%5B%5B126.8242331426722%2C%2037.53788078753248%5D%2C%20%5B126.84257291943153%2C%2037.52373707805596%5D%2C%20%5B126.86610073476395%2C%2037.52699964144669%5D%2C%20%5B126.86637464321238%2C%2037.54859191094823%5D%2C%20%5B126.88825757860099%2C%2037.54079733630232%5D%2C%20%5B126.88156402353862%2C%2037.513970034765684%5D%2C%20%5B126.82688081517314%2C%2037.50548972232896%5D%2C%20%5B126.8242331426722%2C%2037.53788078753248%5D%5D%5D%2C%20%22type%22%3A%20%22Polygon%22%7D%2C%20%22id%22%3A%20%22%5Cuc591%5Cucc9c%5Cuad6c%22%2C%20%22properties%22%3A%20%7B%22base_year%22%3A%20%222013%22%2C%20%22code%22%3A%20%2211150%22%2C%20%22name%22%3A%20%22%5Cuc591%5Cucc9c%5Cuad6c%22%2C%20%22name_eng%22%3A%20%22Yangcheon-gu%22%7D%2C%20%22type%22%3A%20%22Feature%22%7D%2C%20%7B%22geometry%22%3A%20%7B%22coordinates%22%3A%20%5B%5B%5B126.90522065831053%2C%2037.57409700522574%5D%2C%20%5B126.93898161798973%2C%2037.552310003728124%5D%2C%20%5B126.96358226710812%2C%2037.55605635475154%5D%2C%20%5B126.96448570553055%2C%2037.548705692021635%5D%2C%20%5B126.94566733083212%2C%2037.526617542453366%5D%2C%20%5B126.89184663862764%2C%2037.547373974997114%5D%2C%20%5B126.85984199399667%2C%2037.571847855292745%5D%2C%20%5B126.88433284773288%2C%2037.588143322880526%5D%2C%20%5B126.90522065831053%2C%2037.57409700522574%5D%5D%5D%2C%20%22type%22%3A%20%22Polygon%22%7D%2C%20%22id%22%3A%20%22%5Cub9c8%5Cud3ec%5Cuad6c%22%2C%20%22properties%22%3A%20%7B%22base_year%22%3A%20%222013%22%2C%20%22code%22%3A%20%2211140%22%2C%20%22name%22%3A%20%22%5Cub9c8%5Cud3ec%5Cuad6c%22%2C%20%22name_eng%22%3A%20%22Mapo-gu%22%7D%2C%20%22type%22%3A%20%22Feature%22%7D%2C%20%7B%22geometry%22%3A%20%7B%22coordinates%22%3A%20%5B%5B%5B126.9524752030572%2C%2037.60508692737045%5D%2C%20%5B126.95565425846463%2C%2037.576080790881456%5D%2C%20%5B126.96873633279075%2C%2037.56313604690827%5D%2C%20%5B126.96358226710812%2C%2037.55605635475154%5D%2C%20%5B126.93898161798973%2C%2037.552310003728124%5D%2C%20%5B126.90522065831053%2C%2037.57409700522574%5D%2C%20%5B126.9524752030572%2C%2037.60508692737045%5D%5D%5D%2C%20%22type%22%3A%20%22Polygon%22%7D%2C%20%22id%22%3A%20%22%5Cuc11c%5Cub300%5Cubb38%5Cuad6c%22%2C%20%22properties%22%3A%20%7B%22base_year%22%3A%20%222013%22%2C%20%22code%22%3A%20%2211130%22%2C%20%22name%22%3A%20%22%5Cuc11c%5Cub300%5Cubb38%5Cuad6c%22%2C%20%22name_eng%22%3A%20%22Seodaemun-gu%22%7D%2C%20%22type%22%3A%20%22Feature%22%7D%2C%20%7B%22geometry%22%3A%20%7B%22coordinates%22%3A%20%5B%5B%5B126.9738864128702%2C%2037.62949634786888%5D%2C%20%5B126.95427017006129%2C%2037.622033431339425%5D%2C%20%5B126.9524752030572%2C%2037.60508692737045%5D%2C%20%5B126.90522065831053%2C%2037.57409700522574%5D%2C%20%5B126.88433284773288%2C%2037.588143322880526%5D%2C%20%5B126.90396681003595%2C%2037.59227403419942%5D%2C%20%5B126.90303066177668%2C%2037.609977911401344%5D%2C%20%5B126.91455481429648%2C%2037.64150050996935%5D%2C%20%5B126.956473797387%2C%2037.652480737339445%5D%2C%20%5B126.9738864128702%2C%2037.62949634786888%5D%5D%5D%2C%20%22type%22%3A%20%22Polygon%22%7D%2C%20%22id%22%3A%20%22%5Cuc740%5Cud3c9%5Cuad6c%22%2C%20%22properties%22%3A%20%7B%22base_year%22%3A%20%222013%22%2C%20%22code%22%3A%20%2211120%22%2C%20%22name%22%3A%20%22%5Cuc740%5Cud3c9%5Cuad6c%22%2C%20%22name_eng%22%3A%20%22Eunpyeong-gu%22%7D%2C%20%22type%22%3A%20%22Feature%22%7D%2C%20%7B%22geometry%22%3A%20%7B%22coordinates%22%3A%20%5B%5B%5B127.0838752703195%2C%2037.69359534202034%5D%2C%20%5B127.09706391309695%2C%2037.686383719372294%5D%2C%20%5B127.09440766298717%2C%2037.64713490473045%5D%2C%20%5B127.11326795855199%2C%2037.639622905315925%5D%2C%20%5B127.10782277688129%2C%2037.61804244241069%5D%2C%20%5B127.07351243825278%2C%2037.61283660342313%5D%2C%20%5B127.05209373568619%2C%2037.62164065487782%5D%2C%20%5B127.04358800895609%2C%2037.62848931298715%5D%2C%20%5B127.05800075220091%2C%2037.64318263878276%5D%2C%20%5B127.05288479710485%2C%2037.68423857084347%5D%2C%20%5B127.0838752703195%2C%2037.69359534202034%5D%5D%5D%2C%20%22type%22%3A%20%22Polygon%22%7D%2C%20%22id%22%3A%20%22%5Cub178%5Cuc6d0%5Cuad6c%22%2C%20%22properties%22%3A%20%7B%22base_year%22%3A%20%222013%22%2C%20%22code%22%3A%20%2211110%22%2C%20%22name%22%3A%20%22%5Cub178%5Cuc6d0%5Cuad6c%22%2C%20%22name_eng%22%3A%20%22Nowon-gu%22%7D%2C%20%22type%22%3A%20%22Feature%22%7D%2C%20%7B%22geometry%22%3A%20%7B%22coordinates%22%3A%20%5B%5B%5B127.05288479710485%2C%2037.68423857084347%5D%2C%20%5B127.05800075220091%2C%2037.64318263878276%5D%2C%20%5B127.04358800895609%2C%2037.62848931298715%5D%2C%20%5B127.01465935892466%2C%2037.64943687496812%5D%2C%20%5B127.02062116141389%2C%2037.667173575971205%5D%2C%20%5B127.01039666042071%2C%2037.681894589603594%5D%2C%20%5B127.01795099203432%2C%2037.69824412775662%5D%2C%20%5B127.05288479710485%2C%2037.68423857084347%5D%5D%5D%2C%20%22type%22%3A%20%22Polygon%22%7D%2C%20%22id%22%3A%20%22%5Cub3c4%5Cubd09%5Cuad6c%22%2C%20%22properties%22%3A%20%7B%22base_year%22%3A%20%222013%22%2C%20%22code%22%3A%20%2211100%22%2C%20%22name%22%3A%20%22%5Cub3c4%5Cubd09%5Cuad6c%22%2C%20%22name_eng%22%3A%20%22Dobong-gu%22%7D%2C%20%22type%22%3A%20%22Feature%22%7D%2C%20%7B%22geometry%22%3A%20%7B%22coordinates%22%3A%20%5B%5B%5B126.99383903424%2C%2037.676681761199085%5D%2C%20%5B127.01039666042071%2C%2037.681894589603594%5D%2C%20%5B127.02062116141389%2C%2037.667173575971205%5D%2C%20%5B127.01465935892466%2C%2037.64943687496812%5D%2C%20%5B127.04358800895609%2C%2037.62848931298715%5D%2C%20%5B127.05209373568619%2C%2037.62164065487782%5D%2C%20%5B127.03892400992301%2C%2037.609715611023816%5D%2C%20%5B127.0128154749523%2C%2037.613652243470256%5D%2C%20%5B126.98672705513869%2C%2037.63377641288196%5D%2C%20%5B126.9817452676551%2C%2037.65209769387776%5D%2C%20%5B126.99383903424%2C%2037.676681761199085%5D%5D%5D%2C%20%22type%22%3A%20%22Polygon%22%7D%2C%20%22id%22%3A%20%22%5Cuac15%5Cubd81%5Cuad6c%22%2C%20%22properties%22%3A%20%7B%22base_year%22%3A%20%222013%22%2C%20%22code%22%3A%20%2211090%22%2C%20%22name%22%3A%20%22%5Cuac15%5Cubd81%5Cuad6c%22%2C%20%22name_eng%22%3A%20%22Gangbuk-gu%22%7D%2C%20%22type%22%3A%20%22Feature%22%7D%2C%20%7B%22geometry%22%3A%20%7B%22coordinates%22%3A%20%5B%5B%5B126.977175406416%2C%2037.62859715400388%5D%2C%20%5B126.98672705513869%2C%2037.63377641288196%5D%2C%20%5B127.0128154749523%2C%2037.613652243470256%5D%2C%20%5B127.03892400992301%2C%2037.609715611023816%5D%2C%20%5B127.05209373568619%2C%2037.62164065487782%5D%2C%20%5B127.07351243825278%2C%2037.61283660342313%5D%2C%20%5B127.07382707099227%2C%2037.60401928986419%5D%2C%20%5B127.042705222094%2C%2037.59239437593391%5D%2C%20%5B127.02527254528003%2C%2037.57524616245249%5D%2C%20%5B126.99348293358314%2C%2037.588565457216156%5D%2C%20%5B126.98879865992384%2C%2037.6118927319756%5D%2C%20%5B126.977175406416%2C%2037.62859715400388%5D%5D%5D%2C%20%22type%22%3A%20%22Polygon%22%7D%2C%20%22id%22%3A%20%22%5Cuc131%5Cubd81%5Cuad6c%22%2C%20%22properties%22%3A%20%7B%22base_year%22%3A%20%222013%22%2C%20%22code%22%3A%20%2211080%22%2C%20%22name%22%3A%20%22%5Cuc131%5Cubd81%5Cuad6c%22%2C%20%22name_eng%22%3A%20%22Seongbuk-gu%22%7D%2C%20%22type%22%3A%20%22Feature%22%7D%2C%20%7B%22geometry%22%3A%20%7B%22coordinates%22%3A%20%5B%5B%5B127.07351243825278%2C%2037.61283660342313%5D%2C%20%5B127.10782277688129%2C%2037.61804244241069%5D%2C%20%5B127.1201246020114%2C%2037.60178457598188%5D%2C%20%5B127.10304174249214%2C%2037.57076342290955%5D%2C%20%5B127.08068541280403%2C%2037.56906425519017%5D%2C%20%5B127.07382707099227%2C%2037.60401928986419%5D%2C%20%5B127.07351243825278%2C%2037.61283660342313%5D%5D%5D%2C%20%22type%22%3A%20%22Polygon%22%7D%2C%20%22id%22%3A%20%22%5Cuc911%5Cub791%5Cuad6c%22%2C%20%22properties%22%3A%20%7B%22base_year%22%3A%20%222013%22%2C%20%22code%22%3A%20%2211070%22%2C%20%22name%22%3A%20%22%5Cuc911%5Cub791%5Cuad6c%22%2C%20%22name_eng%22%3A%20%22Jungnang-gu%22%7D%2C%20%22type%22%3A%20%22Feature%22%7D%2C%20%7B%22geometry%22%3A%20%7B%22coordinates%22%3A%20%5B%5B%5B127.02527254528003%2C%2037.57524616245249%5D%2C%20%5B127.042705222094%2C%2037.59239437593391%5D%2C%20%5B127.07382707099227%2C%2037.60401928986419%5D%2C%20%5B127.08068541280403%2C%2037.56906425519017%5D%2C%20%5B127.07421053024362%2C%2037.55724769712085%5D%2C%20%5B127.05005601081567%2C%2037.567577612590846%5D%2C%20%5B127.02547266349976%2C%2037.568943552237734%5D%2C%20%5B127.02527254528003%2C%2037.57524616245249%5D%5D%5D%2C%20%22type%22%3A%20%22Polygon%22%7D%2C%20%22id%22%3A%20%22%5Cub3d9%5Cub300%5Cubb38%5Cuad6c%22%2C%20%22properties%22%3A%20%7B%22base_year%22%3A%20%222013%22%2C%20%22code%22%3A%20%2211060%22%2C%20%22name%22%3A%20%22%5Cub3d9%5Cub300%5Cubb38%5Cuad6c%22%2C%20%22name_eng%22%3A%20%22Dongdaemun-gu%22%7D%2C%20%22type%22%3A%20%22Feature%22%7D%2C%20%7B%22geometry%22%3A%20%7B%22coordinates%22%3A%20%5B%5B%5B127.08068541280403%2C%2037.56906425519017%5D%2C%20%5B127.10304174249214%2C%2037.57076342290955%5D%2C%20%5B127.11519584981606%2C%2037.557533180704915%5D%2C%20%5B127.1116764203608%2C%2037.540669955324965%5D%2C%20%5B127.10087519791962%2C%2037.524841220167055%5D%2C%20%5B127.0690698130372%2C%2037.522279423505026%5D%2C%20%5B127.05867359288398%2C%2037.52629974922568%5D%2C%20%5B127.07421053024362%2C%2037.55724769712085%5D%2C%20%5B127.08068541280403%2C%2037.56906425519017%5D%5D%5D%2C%20%22type%22%3A%20%22Polygon%22%7D%2C%20%22id%22%3A%20%22%5Cuad11%5Cuc9c4%5Cuad6c%22%2C%20%22properties%22%3A%20%7B%22base_year%22%3A%20%222013%22%2C%20%22code%22%3A%20%2211050%22%2C%20%22name%22%3A%20%22%5Cuad11%5Cuc9c4%5Cuad6c%22%2C%20%22name_eng%22%3A%20%22Gwangjin-gu%22%7D%2C%20%22type%22%3A%20%22Feature%22%7D%2C%20%7B%22geometry%22%3A%20%7B%22coordinates%22%3A%20%5B%5B%5B127.02547266349976%2C%2037.568943552237734%5D%2C%20%5B127.05005601081567%2C%2037.567577612590846%5D%2C%20%5B127.07421053024362%2C%2037.55724769712085%5D%2C%20%5B127.05867359288398%2C%2037.52629974922568%5D%2C%20%5B127.02302831890559%2C%2037.53231899582663%5D%2C%20%5B127.01070894177482%2C%2037.54118048964762%5D%2C%20%5B127.02547266349976%2C%2037.568943552237734%5D%5D%5D%2C%20%22type%22%3A%20%22Polygon%22%7D%2C%20%22id%22%3A%20%22%5Cuc131%5Cub3d9%5Cuad6c%22%2C%20%22properties%22%3A%20%7B%22base_year%22%3A%20%222013%22%2C%20%22code%22%3A%20%2211040%22%2C%20%22name%22%3A%20%22%5Cuc131%5Cub3d9%5Cuad6c%22%2C%20%22name_eng%22%3A%20%22Seongdong-gu%22%7D%2C%20%22type%22%3A%20%22Feature%22%7D%2C%20%7B%22geometry%22%3A%20%7B%22coordinates%22%3A%20%5B%5B%5B127.01070894177482%2C%2037.54118048964762%5D%2C%20%5B127.02302831890559%2C%2037.53231899582663%5D%2C%20%5B127.01397119667513%2C%2037.52503988289669%5D%2C%20%5B126.98223807916081%2C%2037.509314966770326%5D%2C%20%5B126.95249990298159%2C%2037.51722500741813%5D%2C%20%5B126.94566733083212%2C%2037.526617542453366%5D%2C%20%5B126.96448570553055%2C%2037.548705692021635%5D%2C%20%5B126.98752996903328%2C%2037.55094818807139%5D%2C%20%5B127.01070894177482%2C%2037.54118048964762%5D%5D%5D%2C%20%22type%22%3A%20%22Polygon%22%7D%2C%20%22id%22%3A%20%22%5Cuc6a9%5Cuc0b0%5Cuad6c%22%2C%20%22properties%22%3A%20%7B%22base_year%22%3A%20%222013%22%2C%20%22code%22%3A%20%2211030%22%2C%20%22name%22%3A%20%22%5Cuc6a9%5Cuc0b0%5Cuad6c%22%2C%20%22name_eng%22%3A%20%22Yongsan-gu%22%7D%2C%20%22type%22%3A%20%22Feature%22%7D%2C%20%7B%22geometry%22%3A%20%7B%22coordinates%22%3A%20%5B%5B%5B127.02547266349976%2C%2037.568943552237734%5D%2C%20%5B127.01070894177482%2C%2037.54118048964762%5D%2C%20%5B126.98752996903328%2C%2037.55094818807139%5D%2C%20%5B126.96448570553055%2C%2037.548705692021635%5D%2C%20%5B126.96358226710812%2C%2037.55605635475154%5D%2C%20%5B126.96873633279075%2C%2037.56313604690827%5D%2C%20%5B127.02547266349976%2C%2037.568943552237734%5D%5D%5D%2C%20%22type%22%3A%20%22Polygon%22%7D%2C%20%22id%22%3A%20%22%5Cuc911%5Cuad6c%22%2C%20%22properties%22%3A%20%7B%22base_year%22%3A%20%222013%22%2C%20%22code%22%3A%20%2211020%22%2C%20%22name%22%3A%20%22%5Cuc911%5Cuad6c%22%2C%20%22name_eng%22%3A%20%22Jung-gu%22%7D%2C%20%22type%22%3A%20%22Feature%22%7D%2C%20%7B%22geometry%22%3A%20%7B%22coordinates%22%3A%20%5B%5B%5B126.9738864128702%2C%2037.62949634786888%5D%2C%20%5B126.977175406416%2C%2037.62859715400388%5D%2C%20%5B126.98879865992384%2C%2037.6118927319756%5D%2C%20%5B126.99348293358314%2C%2037.588565457216156%5D%2C%20%5B127.02527254528003%2C%2037.57524616245249%5D%2C%20%5B127.02547266349976%2C%2037.568943552237734%5D%2C%20%5B126.96873633279075%2C%2037.56313604690827%5D%2C%20%5B126.95565425846463%2C%2037.576080790881456%5D%2C%20%5B126.9524752030572%2C%2037.60508692737045%5D%2C%20%5B126.95427017006129%2C%2037.622033431339425%5D%2C%20%5B126.9738864128702%2C%2037.62949634786888%5D%5D%5D%2C%20%22type%22%3A%20%22Polygon%22%7D%2C%20%22id%22%3A%20%22%5Cuc885%5Cub85c%5Cuad6c%22%2C%20%22properties%22%3A%20%7B%22base_year%22%3A%20%222013%22%2C%20%22code%22%3A%20%2211010%22%2C%20%22name%22%3A%20%22%5Cuc885%5Cub85c%5Cuad6c%22%2C%20%22name_eng%22%3A%20%22Jongno-gu%22%7D%2C%20%22type%22%3A%20%22Feature%22%7D%5D%2C%20%22type%22%3A%20%22FeatureCollection%22%7D%29%3B%0A%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20var%20color_map_fc8230284ed5484cb9a56902dd656d6c%20%3D%20%7B%7D%3B%0A%0A%20%20%20%20%0A%20%20%20%20color_map_fc8230284ed5484cb9a56902dd656d6c.color%20%3D%20d3.scale.threshold%28%29%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20.domain%28%5B1766.7692307692307%2C%201767.6197009403422%2C%201768.4701711114537%2C%201769.320641282565%2C%201770.1711114536765%2C%201771.021581624788%2C%201771.8720517958996%2C%201772.7225219670108%2C%201773.5729921381223%2C%201774.4234623092339%2C%201775.2739324803454%2C%201776.1244026514566%2C%201776.9748728225682%2C%201777.8253429936797%2C%201778.6758131647912%2C%201779.5262833359025%2C%201780.376753507014%2C%201781.2272236781255%2C%201782.077693849237%2C%201782.9281640203483%2C%201783.7786341914598%2C%201784.6291043625713%2C%201785.4795745336828%2C%201786.330044704794%2C%201787.1805148759056%2C%201788.030985047017%2C%201788.8814552181286%2C%201789.73192538924%2C%201790.5823955603514%2C%201791.432865731463%2C%201792.2833359025744%2C%201793.1338060736857%2C%201793.9842762447972%2C%201794.8347464159087%2C%201795.6852165870202%2C%201796.5356867581315%2C%201797.386156929243%2C%201798.2366271003546%2C%201799.087097271466%2C%201799.9375674425773%2C%201800.7880376136889%2C%201801.6385077848004%2C%201802.4889779559119%2C%201803.3394481270232%2C%201804.1899182981347%2C%201805.0403884692462%2C%201805.8908586403577%2C%201806.741328811469%2C%201807.5917989825805%2C%201808.442269153692%2C%201809.2927393248035%2C%201810.1432094959148%2C%201810.9936796670263%2C%201811.8441498381378%2C%201812.6946200092493%2C%201813.5450901803606%2C%201814.395560351472%2C%201815.2460305225836%2C%201816.0965006936951%2C%201816.9469708648064%2C%201817.797441035918%2C%201818.6479112070294%2C%201819.498381378141%2C%201820.3488515492522%2C%201821.1993217203637%2C%201822.0497918914753%2C%201822.9002620625868%2C%201823.750732233698%2C%201824.6012024048096%2C%201825.451672575921%2C%201826.3021427470326%2C%201827.1526129181439%2C%201828.0030830892554%2C%201828.8535532603669%2C%201829.7040234314784%2C%201830.5544936025897%2C%201831.4049637737012%2C%201832.2554339448127%2C%201833.1059041159242%2C%201833.9563742870355%2C%201834.806844458147%2C%201835.6573146292585%2C%201836.50778480037%2C%201837.3582549714813%2C%201838.2087251425928%2C%201839.0591953137043%2C%201839.9096654848158%2C%201840.7601356559271%2C%201841.6106058270386%2C%201842.4610759981501%2C%201843.3115461692616%2C%201844.162016340373%2C%201845.0124865114844%2C%201845.862956682596%2C%201846.7134268537075%2C%201847.5638970248187%2C%201848.4143671959303%2C%201849.2648373670418%2C%201850.1153075381533%2C%201850.9657777092646%2C%201851.816247880376%2C%201852.6667180514876%2C%201853.517188222599%2C%201854.3676583937104%2C%201855.2181285648219%2C%201856.0685987359334%2C%201856.919068907045%2C%201857.7695390781562%2C%201858.6200092492677%2C%201859.4704794203792%2C%201860.3209495914907%2C%201861.171419762602%2C%201862.0218899337135%2C%201862.872360104825%2C%201863.7228302759365%2C%201864.5733004470478%2C%201865.4237706181593%2C%201866.2742407892708%2C%201867.1247109603823%2C%201867.9751811314936%2C%201868.8256513026051%2C%201869.6761214737166%2C%201870.5265916448282%2C%201871.3770618159394%2C%201872.227531987051%2C%201873.0780021581625%2C%201873.928472329274%2C%201874.7789425003853%2C%201875.6294126714968%2C%201876.4798828426083%2C%201877.3303530137198%2C%201878.180823184831%2C%201879.0312933559426%2C%201879.881763527054%2C%201880.7322336981656%2C%201881.5827038692769%2C%201882.4331740403884%2C%201883.2836442115%2C%201884.1341143826114%2C%201884.984584553723%2C%201885.8350547248342%2C%201886.6855248959457%2C%201887.5359950670572%2C%201888.3864652381685%2C%201889.23693540928%2C%201890.0874055803915%2C%201890.937875751503%2C%201891.7883459226146%2C%201892.6388160937258%2C%201893.4892862648373%2C%201894.3397564359489%2C%201895.1902266070601%2C%201896.0406967781717%2C%201896.8911669492832%2C%201897.7416371203947%2C%201898.5921072915062%2C%201899.4425774626175%2C%201900.293047633729%2C%201901.1435178048405%2C%201901.9939879759518%2C%201902.8444581470633%2C%201903.6949283181748%2C%201904.5453984892863%2C%201905.3958686603978%2C%201906.246338831509%2C%201907.0968090026206%2C%201907.947279173732%2C%201908.7977493448434%2C%201909.648219515955%2C%201910.4986896870664%2C%201911.349159858178%2C%201912.1996300292894%2C%201913.0501002004007%2C%201913.9005703715122%2C%201914.7510405426237%2C%201915.601510713735%2C%201916.4519808848465%2C%201917.302451055958%2C%201918.1529212270696%2C%201919.003391398181%2C%201919.8538615692923%2C%201920.7043317404039%2C%201921.5548019115154%2C%201922.4052720826267%2C%201923.2557422537382%2C%201924.1062124248497%2C%201924.9566825959612%2C%201925.8071527670727%2C%201926.657622938184%2C%201927.5080931092955%2C%201928.358563280407%2C%201929.2090334515185%2C%201930.0595036226298%2C%201930.9099737937413%2C%201931.7604439648528%2C%201932.6109141359643%2C%201933.4613843070756%2C%201934.3118544781871%2C%201935.1623246492986%2C%201936.0127948204101%2C%201936.8632649915214%2C%201937.713735162633%2C%201938.5642053337444%2C%201939.414675504856%2C%201940.2651456759672%2C%201941.1156158470787%2C%201941.9660860181903%2C%201942.8165561893018%2C%201943.667026360413%2C%201944.5174965315246%2C%201945.367966702636%2C%201946.2184368737476%2C%201947.0689070448589%2C%201947.9193772159704%2C%201948.7698473870819%2C%201949.6203175581934%2C%201950.4707877293047%2C%201951.3212579004162%2C%201952.1717280715277%2C%201953.0221982426392%2C%201953.8726684137505%2C%201954.723138584862%2C%201955.5736087559735%2C%201956.424078927085%2C%201957.2745490981963%2C%201958.1250192693078%2C%201958.9754894404193%2C%201959.8259596115308%2C%201960.6764297826421%2C%201961.5268999537536%2C%201962.3773701248651%2C%201963.2278402959766%2C%201964.078310467088%2C%201964.9287806381994%2C%201965.779250809311%2C%201966.6297209804225%2C%201967.4801911515337%2C%201968.3306613226453%2C%201969.1811314937568%2C%201970.0316016648683%2C%201970.8820718359796%2C%201971.732542007091%2C%201972.5830121782026%2C%201973.433482349314%2C%201974.2839525204254%2C%201975.1344226915369%2C%201975.9848928626484%2C%201976.8353630337597%2C%201977.6858332048712%2C%201978.5363033759827%2C%201979.3867735470942%2C%201980.2372437182057%2C%201981.087713889317%2C%201981.9381840604285%2C%201982.78865423154%2C%201983.6391244026515%2C%201984.4895945737628%2C%201985.3400647448743%2C%201986.1905349159858%2C%201987.0410050870973%2C%201987.8914752582086%2C%201988.7419454293201%2C%201989.5924156004317%2C%201990.4428857715432%2C%201991.2933559426544%2C%201992.143826113766%2C%201992.9942962848775%2C%201993.844766455989%2C%201994.6952366271003%2C%201995.5457067982118%2C%201996.3961769693233%2C%201997.2466471404348%2C%201998.097117311546%2C%201998.9475874826576%2C%201999.798057653769%2C%202000.6485278248806%2C%202001.4989979959919%2C%202002.3494681671034%2C%202003.199938338215%2C%202004.0504085093264%2C%202004.9008786804377%2C%202005.7513488515492%2C%202006.6018190226607%2C%202007.4522891937722%2C%202008.3027593648835%2C%202009.153229535995%2C%202010.0036997071065%2C%202010.854169878218%2C%202011.7046400493293%2C%202012.5551102204408%2C%202013.4055803915523%2C%202014.2560505626639%2C%202015.1065207337751%2C%202015.9569909048867%2C%202016.8074610759982%2C%202017.6579312471097%2C%202018.5084014182212%2C%202019.3588715893325%2C%202020.209341760444%2C%202021.0598119315555%2C%202021.9102821026668%2C%202022.7607522737783%2C%202023.6112224448898%2C%202024.4616926160013%2C%202025.3121627871128%2C%202026.162632958224%2C%202027.0131031293356%2C%202027.8635733004471%2C%202028.7140434715584%2C%202029.56451364267%2C%202030.4149838137814%2C%202031.265453984893%2C%202032.1159241560044%2C%202032.9663943271157%2C%202033.8168644982272%2C%202034.6673346693387%2C%202035.51780484045%2C%202036.3682750115615%2C%202037.218745182673%2C%202038.0692153537846%2C%202038.9196855248958%2C%202039.7701556960074%2C%202040.6206258671189%2C%202041.4710960382304%2C%202042.3215662093417%2C%202043.1720363804532%2C%202044.0225065515647%2C%202044.8729767226762%2C%202045.7234468937877%2C%202046.573917064899%2C%202047.4243872360105%2C%202048.274857407122%2C%202049.1253275782333%2C%202049.975797749345%2C%202050.8262679204563%2C%202051.6767380915676%2C%202052.5272082626793%2C%202053.3776784337906%2C%202054.2281486049023%2C%202055.0786187760136%2C%202055.929088947125%2C%202056.7795591182366%2C%202057.630029289348%2C%202058.480499460459%2C%202059.330969631571%2C%202060.1814398026822%2C%202061.031909973794%2C%202061.8823801449053%2C%202062.7328503160165%2C%202063.5833204871283%2C%202064.4337906582396%2C%202065.284260829351%2C%202066.1347310004626%2C%202066.985201171574%2C%202067.8356713426856%2C%202068.686141513797%2C%202069.536611684908%2C%202070.38708185602%2C%202071.237552027131%2C%202072.0880221982425%2C%202072.938492369354%2C%202073.7889625404655%2C%202074.639432711577%2C%202075.4899028826885%2C%202076.3403730538%2C%202077.1908432249115%2C%202078.041313396023%2C%202078.891783567134%2C%202079.742253738246%2C%202080.592723909357%2C%202081.443194080469%2C%202082.29366425158%2C%202083.1441344226914%2C%202083.994604593803%2C%202084.8450747649144%2C%202085.6955449360257%2C%202086.5460151071375%2C%202087.3964852782487%2C%202088.24695544936%2C%202089.0974256204718%2C%202089.947895791583%2C%202090.798365962695%2C%202091.648836133806%2C%202092.4993063049174%2C%202093.349776476029%2C%202094.2002466471404%2C%202095.050716818252%2C%202095.9011869893634%2C%202096.7516571604747%2C%202097.6021273315864%2C%202098.4525975026977%2C%202099.303067673809%2C%202100.1535378449207%2C%202101.004008016032%2C%202101.8544781871433%2C%202102.704948358255%2C%202103.5554185293663%2C%202104.405888700478%2C%202105.2563588715893%2C%202106.1068290427006%2C%202106.9572992138123%2C%202107.8077693849236%2C%202108.6582395560354%2C%202109.5087097271467%2C%202110.359179898258%2C%202111.2096500693697%2C%202112.060120240481%2C%202112.9105904115922%2C%202113.761060582704%2C%202114.6115307538153%2C%202115.4620009249265%2C%202116.3124710960383%2C%202117.1629412671496%2C%202118.0134114382613%2C%202118.8638816093726%2C%202119.7143517804843%2C%202120.5648219515956%2C%202121.415292122707%2C%202122.2657622938186%2C%202123.11623246493%2C%202123.966702636041%2C%202124.817172807153%2C%202125.667642978264%2C%202126.5181131493755%2C%202127.3685833204872%2C%202128.2190534915985%2C%202129.06952366271%2C%202129.9199938338215%2C%202130.770464004933%2C%202131.6209341760446%2C%202132.471404347156%2C%202133.3218745182676%2C%202134.172344689379%2C%202135.02281486049%2C%202135.873285031602%2C%202136.723755202713%2C%202137.5742253738244%2C%202138.424695544936%2C%202139.2751657160475%2C%202140.1256358871588%2C%202140.9761060582705%2C%202141.8265762293818%2C%202142.677046400493%2C%202143.527516571605%2C%202144.377986742716%2C%202145.228456913828%2C%202146.078927084939%2C%202146.929397256051%2C%202147.779867427162%2C%202148.6303375982734%2C%202149.480807769385%2C%202150.3312779404964%2C%202151.1817481116077%2C%202152.0322182827194%2C%202152.8826884538307%2C%202153.733158624942%2C%202154.5836287960537%2C%202155.434098967165%2C%202156.2845691382763%2C%202157.135039309388%2C%202157.9855094804993%2C%202158.835979651611%2C%202159.6864498227224%2C%202160.536919993834%2C%202161.3873901649454%2C%202162.2378603360567%2C%202163.0883305071684%2C%202163.9388006782797%2C%202164.789270849391%2C%202165.6397410205027%2C%202166.490211191614%2C%202167.3406813627253%2C%202168.191151533837%2C%202169.0416217049483%2C%202169.89209187606%2C%202170.7425620471713%2C%202171.5930322182826%2C%202172.4435023893943%2C%202173.2939725605056%2C%202174.1444427316173%2C%202174.9949129027286%2C%202175.84538307384%2C%202176.6958532449516%2C%202177.546323416063%2C%202178.396793587174%2C%202179.247263758286%2C%202180.0977339293972%2C%202180.9482041005085%2C%202181.7986742716203%2C%202182.6491444427315%2C%202183.4996146138433%2C%202184.3500847849546%2C%202185.200554956066%2C%202186.0510251271776%2C%202186.901495298289%2C%202187.7519654694006%2C%202188.602435640512%2C%202189.452905811623%2C%202190.303375982735%2C%202191.153846153846%5D%29%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20.range%28%5B%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23f1eef6ff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23d4b9daff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23c994c7ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23df65b0ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23dd1c77ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%2C%20%27%23980043ff%27%5D%29%3B%0A%20%20%20%20%0A%0A%20%20%20%20color_map_fc8230284ed5484cb9a56902dd656d6c.x%20%3D%20d3.scale.linear%28%29%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20.domain%28%5B1766.7692307692307%2C%202191.153846153846%5D%29%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20.range%28%5B0%2C%20400%5D%29%3B%0A%0A%20%20%20%20color_map_fc8230284ed5484cb9a56902dd656d6c.legend%20%3D%20L.control%28%7Bposition%3A%20%27topright%27%7D%29%3B%0A%20%20%20%20color_map_fc8230284ed5484cb9a56902dd656d6c.legend.onAdd%20%3D%20function%20%28map%29%20%7Bvar%20div%20%3D%20L.DomUtil.create%28%27div%27%2C%20%27legend%27%29%3B%20return%20div%7D%3B%0A%20%20%20%20color_map_fc8230284ed5484cb9a56902dd656d6c.legend.addTo%28map_de70fb954f834b8ca105f09bf9b18e69%29%3B%0A%0A%20%20%20%20color_map_fc8230284ed5484cb9a56902dd656d6c.xAxis%20%3D%20d3.svg.axis%28%29%0A%20%20%20%20%20%20%20%20.scale%28color_map_fc8230284ed5484cb9a56902dd656d6c.x%29%0A%20%20%20%20%20%20%20%20.orient%28%22top%22%29%0A%20%20%20%20%20%20%20%20.tickSize%281%29%0A%20%20%20%20%20%20%20%20.tickValues%28%5B1766.7692307692307%2C%201837.5%2C%201908.2307692307693%2C%201978.9615384615386%2C%202049.6923076923076%2C%202120.423076923077%2C%202191.153846153846%5D%29%3B%0A%0A%20%20%20%20color_map_fc8230284ed5484cb9a56902dd656d6c.svg%20%3D%20d3.select%28%22.legend.leaflet-control%22%29.append%28%22svg%22%29%0A%20%20%20%20%20%20%20%20.attr%28%22id%22%2C%20%27legend%27%29%0A%20%20%20%20%20%20%20%20.attr%28%22width%22%2C%20450%29%0A%20%20%20%20%20%20%20%20.attr%28%22height%22%2C%2040%29%3B%0A%0A%20%20%20%20color_map_fc8230284ed5484cb9a56902dd656d6c.g%20%3D%20color_map_fc8230284ed5484cb9a56902dd656d6c.svg.append%28%22g%22%29%0A%20%20%20%20%20%20%20%20.attr%28%22class%22%2C%20%22key%22%29%0A%20%20%20%20%20%20%20%20.attr%28%22transform%22%2C%20%22translate%2825%2C16%29%22%29%3B%0A%0A%20%20%20%20color_map_fc8230284ed5484cb9a56902dd656d6c.g.selectAll%28%22rect%22%29%0A%20%20%20%20%20%20%20%20.data%28color_map_fc8230284ed5484cb9a56902dd656d6c.color.range%28%29.map%28function%28d%2C%20i%29%20%7B%0A%20%20%20%20%20%20%20%20%20%20return%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20x0%3A%20i%20%3F%20color_map_fc8230284ed5484cb9a56902dd656d6c.x%28color_map_fc8230284ed5484cb9a56902dd656d6c.color.domain%28%29%5Bi%20-%201%5D%29%20%3A%20color_map_fc8230284ed5484cb9a56902dd656d6c.x.range%28%29%5B0%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20x1%3A%20i%20%3C%20color_map_fc8230284ed5484cb9a56902dd656d6c.color.domain%28%29.length%20%3F%20color_map_fc8230284ed5484cb9a56902dd656d6c.x%28color_map_fc8230284ed5484cb9a56902dd656d6c.color.domain%28%29%5Bi%5D%29%20%3A%20color_map_fc8230284ed5484cb9a56902dd656d6c.x.range%28%29%5B1%5D%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20z%3A%20d%0A%20%20%20%20%20%20%20%20%20%20%7D%3B%0A%20%20%20%20%20%20%20%20%7D%29%29%0A%20%20%20%20%20%20.enter%28%29.append%28%22rect%22%29%0A%20%20%20%20%20%20%20%20.attr%28%22height%22%2C%2010%29%0A%20%20%20%20%20%20%20%20.attr%28%22x%22%2C%20function%28d%29%20%7B%20return%20d.x0%3B%20%7D%29%0A%20%20%20%20%20%20%20%20.attr%28%22width%22%2C%20function%28d%29%20%7B%20return%20d.x1%20-%20d.x0%3B%20%7D%29%0A%20%20%20%20%20%20%20%20.style%28%22fill%22%2C%20function%28d%29%20%7B%20return%20d.z%3B%20%7D%29%3B%0A%0A%20%20%20%20color_map_fc8230284ed5484cb9a56902dd656d6c.g.call%28color_map_fc8230284ed5484cb9a56902dd656d6c.xAxis%29.append%28%22text%22%29%0A%20%20%20%20%20%20%20%20.attr%28%22class%22%2C%20%22caption%22%29%0A%20%20%20%20%20%20%20%20.attr%28%22y%22%2C%2021%29%0A%20%20%20%20%20%20%20%20.text%28%27%27%29%3B%0A%3C/script%3E onload="this.contentDocument.open();this.contentDocument.write(    decodeURIComponent(this.getAttribute('data-html')));this.contentDocument.close();" allowfullscreen webkitallowfullscreen mozallowfullscreen>
    </iframe>
  </div>
</div>




```python

```
