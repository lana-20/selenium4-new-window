# Selenium 4 Window/Tab Management

A test automation engineer might need to open a particular link in a new tab or window to perform certain actions. 

For example, a user wants to open new tabs inside their WebDriver. They are using Selenium for scraping website content from the apps with JavaScript elements that load upon some event tigger.
 

In Selenium 3, engineers had to create a new driver object and then perform the _switch_ operation using the _WindowHandle()_ method to perform consequtive steps.

Selenium 4 comes with the _newWindow_ API, which lets testers create and switch to a new window/tab without creating a new WebDriver object.


