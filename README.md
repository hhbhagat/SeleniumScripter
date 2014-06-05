SeleniumScripter
================

Java Swing application to serve as a scripting interpreter for Selenium in order to quickly formulate browser tests <br />
WebElement Find operators:<br />
css<br />xpath<br />id<br />class<br />name<br />text<br />partialtext<br />
<br />WebElement Action operators<br />
click<br />type<br />cc (clear the previously found webelement)<br />

Quick tutorial:<br />
First line has to be firefox, chrome, internetexplorer, or phantomjsdriver<br />
Second line has to be the starting URL<br />
Third line onwards is the actual script.<br />

firefox //browser<br />
http://www.google.com/webhp?complete=0&hl=en //url<br />
id:lst-ib //element selectors in the format of id/class/name/text/partialtext/css/xpath<br />
type:hello //the type/click/cc commands operate on the previously-selected element.<br />
name:btnK //another selector<br />
click: //example of clicking<br />
<br />
You can also iterate over elements (prefix each element selector with "all").<br />
If you want to perform actions on all those elements, one does so like this:<br />
allid:inputID&click/type&optionalTextToType<br />
<br />
That command command is the same as (in java):<br /><br />
for(WebElement el:driver.findElements(By.id("inputID"))){<br />
el.click();<br />
OR<br />
el.sendKeys("optionalTextToType"); <br />
}<br />
<br />
You can also find elements by matching a string in the results of a query that returns multiple elements, <br />
prefixing each line with "for"<br />
forid:idName&query<br />

this is similar to in java code:<br /><br />

for(WebElement el:driver.findElements(By.id("idName"))){<br />
if(el.getAttribute("innerHTML").contains("query")){<br />
//the resulting element is then available to the next command that you input.<br />
}

<br />
You can also type things in each one. for example:<br />
forid:idName&type&WordToType<br />
