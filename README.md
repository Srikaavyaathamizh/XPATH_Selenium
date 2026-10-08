# XPATH_Selenium
## Real-time scenario
Imagine an online student registration form.

The automation must:

Open the registration page.
Enter student name.
Enter password.
Enter additional information.
Select dropdown.
Select checkbox.
Select radio button.
Click Submit.
Verify successful submission.

# Code:
```
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import Select

import time 

#--------------open page-----------------
driver=webdriver.Chrome()
driver.get("https://demoqa.com/automation-practice-form")
driver.maximize_window
time.sleep(2)
#-------------task2-----------------
try:
    fname=driver.find_element(By.XPATH,"//*[@id='firstName']")
    fname.send_keys("Sriiii")
    print("absolute xpath is working")
except Exception as e:
    print("absolute xpath is not working",e)

time.sleep(2)
#-------------- task 3------------------
try:
    lname=driver.find_element(By.XPATH,"//*[@id='lastName']")
    lname.send_keys("kaavyaa")
    print("absolute xpath is working")
except Exception as e:
    print("not working ",e)
time.sleep(2)
#----------------task 4--------------------

submit_button = driver.find_element(
    By.XPATH,
    "//button[text()='Submit']"
)

print("Text XPath:")
print(submit_button.text)
time.sleep(2)
#----------------task 5--------------------

element = driver.find_element(
    By.XPATH,
    "//input[contains(@placeholder,'Mobile')]"
)

element.clear()
element.send_keys("78945612385")

print("contains() executed")
time.sleep(2)
#----------------task 6--------------------
email=driver.find_element(By.XPATH,"//input[@placeholder='name@example.com']")
email.send_keys("srikaavyaa@gmail.com")
time.sleep(2)
#----------------task 7--------------------
sub = driver.find_element(
    By.XPATH,
    "//input[@id='subjectsInput' and @type='text']"
)

sub.send_keys("subjectssss")
time.sleep(2)
#----------------task 8--------------------
current_address = driver.find_element(
    By.XPATH,
    "//textarea[@placeholder='Current Address' or @id='currentAddress']"
)

current_address.send_keys("chennai")
time.sleep(2)
#----------------task 9--------------------
checkbox = driver.find_element(
    By.XPATH,
    "//input[@id='hobbies-checkbox-1']"
)

checkbox.click()

print("Checkbox selected")
time.sleep(2)  
#----------------task 10--------------------
female = driver.find_element(
    By.XPATH,
    "//input[@id='gender-radio-2']"
)

female.click()

print("Female radio button selected")
#----------------task 11--------------------
state = driver.find_element(
    By.XPATH,
    "//input[@id='react-select-3-input']"
)

state.click()
state.send_keys("NCR")

time.sleep(1)

option = driver.find_element(
    By.XPATH,
    "//div[text()='NCR']"
)

option.click()

print("State selected")
time.sleep(2)
#----------------task 12--------------------
inputs = driver.find_elements(
    By.XPATH,
    "//input"
)

print("Total input fields:", len(inputs))
#----------------task 13--------------------
city = driver.find_element(
    By.XPATH,
    "//input[contains(@id,'react-select-4-input')]"
)

city.click()

print("Dynamic element found using contains()")
time.sleep(2)
driver.quit()
```

# Output:
<img width="1765" height="961" alt="Screenshot 2026-10-08 114352" src="https://github.com/user-attachments/assets/587c472a-e8c6-45b5-9a2e-ab1dc60f272a" />
<img width="1811" height="950" alt="Screenshot 2026-10-08 114517" src="https://github.com/user-attachments/assets/a0136834-9eb8-4686-b724-cbf40a6ee0c6" />
<img width="1810" height="946" alt="Screenshot 2026-10-08 114623" src="https://github.com/user-attachments/assets/ec585972-1e88-49fc-a791-68d1c6d890d3" />



