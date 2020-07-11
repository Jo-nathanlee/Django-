## **註冊PythonAnywhere**
1.	首先到  [PythonAnywhere](https://www.pythonanywhere.com/pricing/) 點擊 Create a Beginner account
2.	註冊帳號密碼
## **建置虛擬環境**
1.	點擊紅色方框內的$Bash開啟終端機
![image](https://github.com/Jo-nathanlee/Learning-Django/blob/master/pic/step1.png)
2.	輸入指令
```
mkvirtualenv django2 --python=/usr/bin/python3.6     #django2為環境名稱，可自訂
pip install django 
```
3.	成功完成將會看到畫面如下 
![image](https://github.com/Jo-nathanlee/Learning-Django/blob/master/pic/step2.png)
**之後每次執行djanog專案時，請確保開啟虛擬環境(django2)
**開啟指令為workon django2
## **建立django專案**
1.	輸入指令(mysite為專案名稱，可自訂)
```
django-admin startproject mysite
```
2.	點選右上角Files
![image](https://github.com/Jo-nathanlee/Learning-Django/blob/master/pic/step3.png)
3.	點選Directories下的mysite文件夾即可看到所建專案目錄，右側的Files為該目錄底下的檔案
![image](https://github.com/Jo-nathanlee/Learning-Django/blob/master/pic/step4.png)
## **設定 Allow hosts**
1.  開啟 **settings.py** 找到 **ALLOWED_HOSTS** ，在中括號內加入
```
'*'
```
## **配置Web Server**
1.	點選右上角Web
![image](https://github.com/Jo-nathanlee/Learning-Django/blob/master/pic/step5.png)
2.	點選Add a new web app，選擇Manual configuration
![image](https://github.com/Jo-nathanlee/Learning-Django/blob/master/pic/step6.png)
3.	選擇Python3.6，點選Next
4.	點選Enter path to a virtualenv,if desired
![image](https://github.com/Jo-nathanlee/Learning-Django/blob/master/pic/step7.png)
5.	輸入虛擬環境名稱django2，點選Confirm
6.	點選WSGI configuration file進行編輯
![image](https://github.com/Jo-nathanlee/Learning-Django/blob/master/pic/step8.png) 
7.	將原本的程式碼刪除，輸入以下(第四行mysite可依專案名稱修改)
```
import os
import sys

path = os.path.expanduser('~/mysite')
if path not in sys.path:
    sys.path.insert(0, path)
os.environ['DJANGO_SETTINGS_MODULE'] = 'mysite.settings'
from django.core.wsgi import get_wsgi_application
from django.contrib.staticfiles.handlers import StaticFilesHandler
application = StaticFilesHandler(get_wsgi_application())
```
8.	點選右上角Save按鈕，回到Web頁面
9.	點選Reload
![image](https://github.com/Jo-nathanlee/Learning-Django/blob/master/pic/step10.png) 
**之後每次更新專案程式內容後，需重新點擊Reload以更新上Web Server
10.	點選上方網址連結即可開啟此專案頁面
![image](https://github.com/Jo-nathanlee/Learning-Django/blob/master/pic/step11.png) 

