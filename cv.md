## Aleksei Kononov
## Contact info:
* **Adress:** Russia, Saint-Petersburg
* **Phone:** +7951665xxxx
* **E-mail:** aleshqeen@gmail.com
* **GitHub:** [conanz0r](https://github.com/conanz0r)
* **Telegram:** [conanz0r](https://t.me/conanz0r)

## About myself:
Я котик и у меня лапки :3

## Skills & tools:
* QA basics (Test design techniques, Test documentation & etc)
* HTML & CSS (basics)
* Linux Bash commands (GitHub link soon)
* Git Bash (GitHub link soon)
* SQL ([SQL-Academy](https://sql-academy.org) & [SQL-EX](https://sql-ex.ru) & HW from Course)
* DevTools
* Postman (GitHub link soon)
* Android Studio 
* Jmeter (GitHub link soon)
* Charles & Fiddler (GitHub link soon)
* Trying to JS :P
* Python (Selenium ONE time for a personal project)
* Editors: VSCode, Pycharm

## Code Example:
```

from selenium import webdriver  
from webdriver_manager.chrome import ChromeDriverManager  
from datetime import datetime  
import time  
from selenium.webdriver.common.action_chains import ActionChains  
from selenium.webdriver.common.by import By  
from collections import *  
import numpy as np  
import pandas as pd  
import random as rd  
  
year = '2021'  
driver = webdriver.Chrome(ChromeDriverManager().install())  
driver.get(f'https://www.flashscore.ru.com/hockey/germany/del/results/')  
  
while True:  
    try:  
        time.sleep(2)  
        driver.execute_script("window.scrollTo(0, document.body.scrollHeight);")  
        time.sleep(2)  
        driver.find_element(By.CSS_SELECTOR, "a.event__more.event__more--static").click()  
    except:  
        break  
  
  
match_id = driver.find_elements(By.CLASS_NAME, "event__match.event__match--static.event__match--twoLine")  
  
matches_id = [el.get_attribute('id') for el in match_id]  
matches_id = list(map(lambda x: x.replace('g_4_', ''), matches_id))  
  
  
# game = matches_id[0]  
# url = 'https://www.flashscore.ru.com/match/' + game + '/#/match-summary/match-summary'  
# driver.get(url)  
#  
# date = driver.find_elements(By.CLASS_NAME, "duelParticipant__startTime")  
# #print(date[0].text)  
# h_team = driver.find_elements(By.CLASS_NAME, "duelParticipant__home")  
# #print(h_team[0].text)  
# a_team = driver.find_elements(By.CLASS_NAME, "duelParticipant__away")  
# #print(a_team[0].text)  
# result = driver.find_elements(By.CLASS_NAME, "detailScore__wrapper")  
# #print(result[0].text)  
# clean_res = result[0].text.replace('\n', '')  
# #print(clean_res)  
# [int (i) for i in clean_res.split('-')]  
#  
# stat_url = 'https://www.flashscore.ru.com/match/' + game + '#/match-summary/match-statistics/0'  
# driver.get(stat_url)  
  
season_data = []  
for game in matches_id[0:378]:  
    url = 'https://www.flashscore.ru.com/match/' + game + '/#/match-summary/match-summary'  
  driver.get(url)  
    date = driver.find_elements(By.CLASS_NAME, "duelParticipant__startTime")[0].text  
    h_team = driver.find_elements(By.CLASS_NAME, "duelParticipant__home")[0].text  
    a_team = driver.find_elements(By.CLASS_NAME, "duelParticipant__away")[0].text  
    result = driver.find_elements(By.CLASS_NAME, "detailScore__wrapper")  
    clean_res = result[0].text.replace('\n', '')  
    goals = [int (i) for i in clean_res.split('-')]  
    print(date, h_team, a_team, goals[0], goals[1])  
    season_data.append((date, h_team, a_team, goals[0], goals[1]))  
  
result_df = pd.DataFrame(season_data, columns = ['Дата', 'Хозяева', 'Гости', 'Забили хозяева', 'Забили гости'])  
result_df.to_excel('testpls1.xlsx')

```

## Education:
* V. K.  Course (link cert)
* Stepik?? (link cert)
* Offline course at 2019 (have certificate), but it too old
* CS50 xz

## EXP:
At my last job, I was testing my products - manually checking data from Excel spreadsheets.

## Language:
* Russian (Native)
* Engilsh (B1)
* Albanian [(kek)](http://lurklurk.com/Ниасилил)
