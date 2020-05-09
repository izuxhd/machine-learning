import bs4

import requests

url=input("ENTER URL")
response=requests.get(url)
print(type(response))
print(response.text)
filename="techsoft.html"
bs=bs4.BeautifulSoup(response.text,"html.parser")
formatted_text=bs.prettify()
print(formatted_text)
with open(filename,"w+") as f:
  f.write(formatted_text)
lis=bs.find_all('img')
print(len(lis))
