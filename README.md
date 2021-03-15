import requests
import re
r = requests.get("http://out-of-eurasia.jp/")
r.text
r.encoding = r.apparent_encoding

demo = r.text
from bs4 import BeautifulSoup
soup = BeautifulSoup(demo,"html.parser")
a = soup.find_all(string=re.compile("〒"))    
# 查找string 中包含“〒”的 tag, find 只能找到一个地址，如果页面有 2 个地址要用 find_all
print (a)
