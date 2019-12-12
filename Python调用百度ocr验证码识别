# -*- coding:utf-8 -*-
# coding: utf-8
import requests
import json
import sys
import os
import imaplib
from PIL import Image
from io import BytesIO
from requests_toolbelt import MultipartEncoder

from requests.packages.urllib3.exceptions import InsecureRequestWarning
requests.packages.urllib3.disable_warnings(InsecureRequestWarning)

from aip import AipOcr
default_encoding="utf-8"
APP_ID = 'YOUR_APP_ID'
API_KEY = 'YOUR_APP_KEY'
SECRET_KEY = 'YOUR_SECRET_KEY'
client = AipOcr(APP_ID, API_KEY, SECRET_KEY)
LOCATION_IN='temp1.jpg'
location_out="temp2.jpg"
if(default_encoding!=sys.getdefaultencoding()):
    reload(sys)
    sys.setdefaultencoding(default_encoding)

""" 读取图片 """
def get_file_content(filePath):
    with open(filePath, 'rb') as fp:
        return fp.read()

#验证码识别模块
def code_process(im):

    imgry = im.convert('L')  # 转化为灰度图
    #imgry.show()
    imbin=binarizing(imgry,255)
    #imbin.show()
    imout=depoint(imbin)
    #imout.show()
    imout.save(location_out)
    image = get
