# Contents
  - [[#Budget Project|Budget Project]]
    - [[#Budget Project#Page Loading|Page Loading]]
    - [[#Budget Project#CapOne360 Scraping|CapOne360 Scraping]]

# Budget Project

## Page Loading

```python
from selenium import webdriver

driver = webdriver.Firefox()
driver.implicitly_wait(10) # seconds
driver.get("http://somedomain/url_that_delays_loading")
myDynamicElement = driver.find_element_by_id("myDynamicElement")
```

Implicit wait only needs to be set once at the start of the script. The driver
should then wait for up to the set number of seconds for the element to become available.

See: [http://selenium-python.readthedocs.io/waits.html Selenium Docs]

## CapOne360 Scraping
This will be way more complicated than suntrust.
