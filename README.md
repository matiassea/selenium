# selenium
General information about Selenium
https://selenium-python.readthedocs.io/

https://www.techbeamers.com/locate-elements-selenium-python/



###HTML

Los campos a consultar con get.attribute()

https://www.w3schools.com/tags/ref_attributes.asp



### Frame

https://stackoverflow.com/questions/47770144/how-can-i-select-a-html-element-no-matter-what-frame-it-is-in-in-selenium/47771879#47771879


#### Reason :

When a page is loaded, Selenium's focus by default remains on the Top Window. The Top Window contains the other iframes and the framesets. So when we need to interact with a WebElement which is within an iframe we have to switch to the respective iframe through one of the below-mentioned methods :

#### Frame Switching Methods :

We can switch over to frames by 3 ways.

##### By Frame Name :

Name attribute of iframe through which we can switch to it.
´´´
driver.switch_to.frame("iframe_id")
´´´

##### By Frame Index :

Suppose if there are 10 frames in the page, we can switch to the iframe by using the index.
´´´
driver.switch_to.frame(0)
driver.switch_to.frame(1)
´´´

##### Switching back to the Main Frame :

We can switch back to the main frame by using default_content() or parent_frame()

Example:

´´´
driver.switch_to.default_content()
driver.switch_to.parent_frame()

´´´
#### Se recomienda buscar frame, esperando la aparicion de este elemento.

As per the best practices while switching to an iframe you need to induce WebDriverWait as follows:

´´´
WebDriverWait(driver, 10).until(EC.frame_to_be_available_and_switch_to_it(By.ID,"id_of_iframe"))
WebDriverWait(driver, 10).until(EC.frame_to_be_available_and_switch_to_it(By.NAME,"name_of_iframe"))
WebDriverWait(driver, 10).until(EC.frame_to_be_available_and_switch_to_it(By.XPATH,"xpath_of_iframe"))
WebDriverWait(driver, 10).until(EC.frame_to_be_available_and_switch_to_it(By.CSS_SELECTOR,"css_of_iframe"))
´´´


