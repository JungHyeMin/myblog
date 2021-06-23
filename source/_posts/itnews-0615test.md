---
title: Web Scraping with Python
---
## Source Code


``` bash
import requests
from bs4 import BeautifulSoup

print("[IT 관련 뉴스]")   
url = "https://news.naver.com"
headers = {"User-Agent":"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/90.0.4430.212 Safari/537.36"} 
res = requests.get(url, headers=headers)
res.raise_for_status()
soup = BeautifulSoup(res.text, "lxml")
news_list = soup.find("ul", attrs={"class":"mlist2 no_bg"}).find_all("li", limit=3)


for index, news in enumerate(news_list):
       
    a_idx = 0
    img = news.find("img")
    if img:
        a_idx = 1
       
    title = news.find_all("a")[a_idx].get_text().strip()
    link =  news.find_all("a")[a_idx]["href"]
    print("{0}." "{1}".format(index+1, title))
    print("링크 : {0}".format(link))
```

