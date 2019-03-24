# WebScraper

from urllib.request import urlopen as uReq
 from bs4 import BeautifulSoup as soup
 my_url="https://docs.python.org/3.7/tutorial/index.html"
 uClient=uReq("https://docs.python.org/3.7/tutorial/index.html")
 page_html=uClient.read()
 uClient.close()
 page_soup=soup(page_html,"html.parser")
from urllib.request import urlopen as uReq
from bs4 import BeautifulSoup as soup
import csv
import re

my_url = "https://en.wikipedia.org/wiki/Bayside_(band)"
uClient = uReq("https://en.wikipedia.org/wiki/Bayside_(band)")
page_html = uClient.read()
page_soup = soup(page_html, "html.parser")
def pick(uurl):
    uClient = uReq("https://en.wikipedia.org/wiki/Bayside_(band)")
    page_html = uClient.read()
    uClient.close()
    page_soup = soup(page_html, "html.parser")
    return page_soup;


body = soup.findAll(self='tr').findNext('td')

filename = "data.csv"
title=soup.title.text
f = open(filename, 'w')
f.write(body.text)

print("Success")
for i in body:
        i=i.text
        i=i.re.sub('\[\d+\]','',str(i))
        i = i.re.sub('\[.*?\]', '', str(i))
f.write(str(i)+ '\n\n')
f.close()







if __name__ == '__main__':
        a=pick(my_url)
        print("url :", a)
