# login-using-selenium
this is how to login in a website with selenium
from selenium import webdriver
from selenium.webdriver.chrome.service import Service
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.common.keys import Keys
from webdriver_manager.chrome import ChromeDriverManager
import time

# Use ChromeDriverManager to automatically download the driver
driver_service = Service(ChromeDriverManager().install())  # Automatically handles driver installation and path

# Initialize WebDriver with Service
driver = webdriver.Chrome(service=driver_service)

# Step 1: Open the Website
website_url = ("https://example.com")  # Replace with the target website URL
driver.get(website_url)

# Step 2: Wait for the page to load
time.sleep(2)

# Step 3: Locate the Login Button and Click it (if necessary)
login_button = driver.find_element(By.CSS_SELECTOR, ".top-session-button.button.button__secondary.outline.link")  # Replace with actual button's ID
login_button.click()

# Step 4: Wait for the login form to appear
time.sleep(2)

# Step 5: Enter Username
username_field = driver.find_element(By.CLASS_NAME, "input")
username_field.send_keys("username")
# Replace with actual username input field name
time.sleep(12)
#step 6: enter password
password_field = driver.find_element(By.XPATH, "//input[@type='password' and @class='input']")
password_field.send_keys("password")
time.sleep(12)
#step 7 : clicking the login button after entering the credentials
login_button = driver.find_element(By.XPATH, "//button[contains(@class, 'session__form__button') and contains(span, 'Login')]")
login_button.click()
