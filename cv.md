# rsschool-cv/cv
# Akhmad Badalov
## Contact Info:
Contact Adresses
1. Email: akhmadbadalov98@gmail.com
2. Phone number: +998993019713
3. Linkedin: https://www.linkedin.com/in/akhmad-badalov-928966211/
4. Telegram: AkhmaDJ
## Summary
The main _goal_ of mine is to make a good community with my collegues while learning knowledge and share it to the community, including new learners.
## Skills
### Programming Languages
* Python
### Scripting Languages
* JavaScript
* PHP
### Frameworks
* Node.js
* Express.js
* VanillaJs
* CodeIgniter
#### Libraries
* D3.js
* JQuery
* Matplotlib
* Seaborn
* Pandas
## Code Examples
This is one of example codes written by python programming language.
```{python}
def find_closestValue(tree, target):
    return findClosestValueInBstHelper(tree, target, float("inf"))

def findClosestValueinBstHelper(tree, target, closest):
    currentNode = tree      #storing space for tree as another value currentNode
    while currentNode is not None: #it tells to iterate while not at the bottom
    if abs(target - closest) > abs(target - currentNode.value):
        closest = currentNode.value
    if target < currentNode.value:
        currentNode = currentNode.left
    if target > currentNode.value:
        currentNode = currentNode.right
    else:
        break
    return closest

class Node(object):
  
def insert(self, d):
    if self.data == d:
  return False
    elif d < self.data:
  if self.left:
            return self.left.insert(d)
  else:
      self.left = Node(d)
      return True
    else:
  if self.right:
            return self.right.insert(d)
  else:
          self.right = Node(d)
  return True
  
import requests
import csv
import pandas as pd
from bs4 import BeautifulSoup

URL = 'https://kun.uz/news/list?f=latest&next=1620051453'
HEADERS = {'user-agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:85.0) Gecko/20100101 Firefox/85.0', 'accept': '*/*'}


def get_html_page(url, params=None):
    page = requests.get(url, headers=HEADERS, params=params)
    return page
def get_content(html, linkclass, headclass, contentclass):
    soup = BeautifulSoup(html.text, 'html.parser')
    latest_news = soup.find_all('a', class_=linkclass)
    arr = []
    arr_p = []
    arr_heading = []
    for item in latest_news:
        item_url = item.get("href")
        url = 'https://kun.uz'+ item_url
        linked_page = requests.get(url)
        soup_inn = BeautifulSoup(linked_page.text, 'html.parser')
        each_heading = soup_inn.find(class_=headclass)
        each_heading_text = each_heading.text
        all_p = soup_inn.find(class_=contentclass).find_all('p')
        arr.append(url)
        arr_heading.append(each_heading_text)
        content = ''
        for item_p in all_p:
            content += item_p.text
        arr_p.append(content)
    dict = {'Link' : arr, 'Headings' : arr_heading, 'Paragraphs': arr_p}
    df = pd.DataFrame(dict)
    df.to_csv('latest_news.csv')
    # return dict

def parse(linkclass, headclass, contentclass):
    html = get_html_page(URL)
    if html.status_code == 200:
        get_content(html, linkclass, headclass, contentclass)
    else:
        print('Error')


parse('daily-block', 'single-header__title', 'single-content')
```{python}

```{javascript}
const express = require('express')
const path = require('path')
const exphbs = require('express-handlebars')
const logger = require('./middleware/logger')
const products = require('./Members')

const app = express();

//init middleware
// app.use(logger)

//Hnadlebars middlewar
app.engine('handlebars', exphbs({ defaultLayout: 'main' }))
app.set('view engine', 'handlebars')

// Body parser Middleware
app.use(express.json());
app.use(express.urlencoded({ extended: false }))

//HOme page Route
app.get('/', (req, res) => res.render('index', {
    title: 'Member App',
    products
}))

//Set static folder either static or handlebars should be used not both
app.use(express.static(path.join(__dirname, 'public')))

//Products API Routes
app.use('/api/products', require('./routes/api/products'))

const PORT = process.env.PORT || 4000

app.listen(PORT, () => console.log(`Server is running`))
```{javascript}
## Experience
Currently, I am working in the Project of creating robot and teaching it to speak in my native languae (Uzbek). The project is at the middle.
1. NLP in AI and the Realization of Futuristic Robots in Uzbek
2. Contact holder web application on C#
3. Visitor web site on HTML
4. Chatbot on Python
5. A pair of backend part of web application (Vacancy manager on Node.js)
6. Inventory Management System with User Management (RBAC based on CodeIgniter)
7. E-commerce (PHP)
## Education
I am a graduator of Management Development Institute of Singapore in Tashkent. The pioneer student of the faculty I am studying is _Computer Science in Business_. In the period of three-year, we received courses from System Administration Management *(Unix, Ubuntu OS)*, Web development *(HTML, CSS, JS)*, Database *(SQL)*. 
## English
The level of my English is at Pre-Intermediate according to the FY certificate suggested by MDIS in Tashkent in the first-year course.
## Personal Qualities
* High level of communication skills
* Leading workers and people 
* Mindfullness
* High discipline