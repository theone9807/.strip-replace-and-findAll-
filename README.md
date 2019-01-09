# .strip-replace-and-findAll-
Today's our topic is .replace(), .strip() and findAll() 

this three are very usefull function for begineers and for web scrapers while they are scraping a webpage.

# .strip()
.strip() is used to remove white space from the start and end of the string.
## .rstrip()  and .lstrip()
.rstrip() is used to remove the white space from thr right of the string
.lstrip() is used to remove white space from thr left of the string

s = "   Hello World!       "
s.strip() gives output as 
"Hello World!"

# .replace() is generally used to remove the new line in the the string, this is  done as follow:

s = "Hello 
     World
     !"
      
      
s.replace("\n", "") will remove all the new line,
if you  do s.replace("\n","-") then all the new line will be replaced with -
the output are as follow
# s.replace("\n", "") gives:
"Hello World!"
# s.replace("\n", "-") gives:
"Hello-World-!"

# findAll() method is brefely explained in the Regrex module, most of the time findAll() is in webscraping, findAll() search for a certain pattern and finds all the pattern of such type and stores it in a list, if you do findAll("p") then it will find all the p tag in a webpage and, it will stores it in a list.

import requests
import re
from bs4 import BeautifulSoup
resp = requests.get(url)
soup = BeautifulSoup(resp.text)
p_tag = soup.findAll("p")
p = [txt.get_text().replace("\n", "").strip() for txt in h1_tag]
print(p)

this code is an python code which is used to find  all the "p" tag  in a website(which you provide by url) and stores it in a p_tag list and after this we have created a variable p which contains all the text part in the p-tags ,removes the new line and white spaces. and finally we pave printed the p.
