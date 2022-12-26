# Selenium 4 Window/Tab Management

A test automation engineer might need to open a particular link in a new tab or window to perform certain actions. 

For example, a user wants to open new tabs inside their WebDriver. They are using Selenium for scraping website content from the apps with JavaScript elements that load upon some event tigger.
 

In Selenium 3, engineers had to create a new driver object and then perform the _switch_ operation using the _WindowHandle()_ method to perform consequtive steps.

Selenium 4 comes with the _newWindow_ API, which lets testers create and switch to a new window/tab without creating a new WebDriver object.

## Create new window (or) new tab and switch
Create a new blank window (or) tab and focus the new window/tab on the screen. No need to switch to work with the new window/tab. 

     # Open a new tab and switch to it
     driver.switch_to.new_window('tab')

     # Open a new window and switch to it
     driver.switch_to.new_window('window')

I can open www.google.com in the initial tab and www.yahoo.com in the adjacent teb.

    from selenium import webdriver
    from selenium.webdriver.support.ui import WebDriverWait
    from selenium.webdriver.support import expected_conditions as EC
    from webdriver_manager.chrome import ChromeDriverManager

    driver = webdriver.Chrome(service=ChromeService(ChromeDriverManager().install()))
    driver.get("https://www.google.com/")
    print("Original page title is: %s %driver.title)
    original_window = driver.current_window_handle
    print("1st window handle is: %s %original_window)
    driver.switch_to.new_window("https://www.yahoo.com/")
    WebDriverWait(driver, 5).until(EC.number_of_windows_to_be(2))
    new_window = driver.current_window_handle
    print("New page title is: %s %driver.title)
    print("2nd window handle is: %s %original_window)
    driver.quit()

_Console Output_:

    Original page title is: Google
    1st window handle is: CDWindow-B2B3DE3A222B5DA3257840FA784FA780
    New page title is: Yahoo
    2nd window handle is: CDWindow-D7DA6777A0008DE91991C623105B1EC4






----

[Working with windows and tabs](https://www.selenium.dev/documentation/webdriver/interactions/windows/)

[Open web in new tab Selenium + Python](https://stackoverflow.com/questions/28431765/open-web-in-new-tab-selenium-python)

[How to open a new blank Tab or Window - Selenium - 4 new feature](https://youtu.be/7SpCMkUKq-Y)


