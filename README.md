# Selenium
General information about Selenium
https://selenium-python.readthedocs.io/

https://www.techbeamers.com/locate-elements-selenium-python/



#### HTML

Los campos a consultar con get.attribute()

https://www.w3schools.com/tags/ref_attributes.asp



#### Frame

https://stackoverflow.com/questions/47770144/how-can-i-select-a-html-element-no-matter-what-frame-it-is-in-in-selenium/47771879#47771879


##### Reason :

When a page is loaded, Selenium's focus by default remains on the Top Window. The Top Window contains the other iframes and the framesets. So when we need to interact with a WebElement which is within an iframe we have to switch to the respective iframe through one of the below-mentioned methods :

##### Frame Switching Methods :

We can switch over to frames by 3 ways.

##### By Frame Name :

Name attribute of iframe through which we can switch to it.
```
driver.switch_to.frame("iframe_id")
```

##### By Frame Index :

Suppose if there are 10 frames in the page, we can switch to the iframe by using the index.
```
driver.switch_to.frame(0)
driver.switch_to.frame(1)
```

##### Switching back to the Main Frame :

We can switch back to the main frame by using default_content() or parent_frame()

Example:

```
driver.switch_to.default_content()
driver.switch_to.parent_frame()

```
#### Se recomienda buscar frame, esperando la aparicion de este elemento.

As per the best practices while switching to an iframe you need to induce WebDriverWait as follows:

```
WebDriverWait(driver, 10).until(EC.frame_to_be_available_and_switch_to_it(By.ID,"id_of_iframe"))
WebDriverWait(driver, 10).until(EC.frame_to_be_available_and_switch_to_it(By.NAME,"name_of_iframe"))
WebDriverWait(driver, 10).until(EC.frame_to_be_available_and_switch_to_it(By.XPATH,"xpath_of_iframe"))
WebDriverWait(driver, 10).until(EC.frame_to_be_available_and_switch_to_it(By.CSS_SELECTOR,"css_of_iframe"))
```

### Instalacion de Geckodriver

http://www.automationtestinghub.com/selenium-3-0-launch-firefox-with-geckodriver/

What is Gecko and GeckoDriver? Gecko is a web browser engine used in many applications developed by Mozilla Foundation and the Mozilla Corporation.Geckodriver is a proxy for using W3C WebDriver-compatible clients to interact with Gecko-based browsers i.e. Mozilla Firefox in this case.


1. Open Firefox on your machine. Click on Hamburger icon from the right corner to open the menu as shown below
2. From this menu, click on Help icon (Help icon is marked in red box in the above image)
3. Once you click on Help icon, the Help Menu would be displayed
4. Click on About Firefox from the Help menu. About Mozilla Firefox popup would be displayed
5. Note down whether Firefox is 32 or 64 bit. For us, Firefox is 64-bit as shown in the above image. Now close this popup and close Firefox as well.


#### Download the latest version of Selenium Geckodriver

1. Open this Github page – https://github.com/mozilla/geckodriver/releases
2. Download the latest release (windows version) based on whether your Firefox is 32-bit or 64-bit. We are downloading geckodriver-v0.20.1-win64.zip, as we have 64-bit Firefox
3. Once the zip file is downloaded, unzip it to retrieve the driver – geckodriver.exe

#### Launch Firefox Method 2 : Set property in Environment Variables
1. Copy the entire folder location where geckodriver.exe is saved. If the entire path is D:\Firefox\geckodriver.exe, then the folder location would be D:\Firefox\
2. Open Advanced tab in System Properties window as shown in below image.
3. Open Environment Variables window. 
4. In System variables section, select the Path variable (highlighted in the above image) and click on Edit button. Then add the location of Geckodriver that we copied in step 1 (D:\Firefox\), to path variable (below image shows UI for Windows 10)
5. If you are using Windows 7, then move to the end of the Variable value field, then add a semi-colon (;) and then add the folder location as shown below (Semicolon acts as a separator between multiple values in the field)
6. Click on Ok button to close the windows. Once the path is set, you would not need to set the System property every time in the test script. Your test script would simply look like this – 
7. Run the code to check that it works fine.


