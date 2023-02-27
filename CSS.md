CSS  Cascading Style Sheets
---
- definition：
Multiple styles can be applied to the same HTML element at the same time  
- benefits：
Separate content presentation and style control, reduce coupling degree, make division of labor and collaboration easier, improve development efficiency  

- css usage: The combination of css and html
1. Inline style: Use the style attribute within the tag to specify the css code 
2. Interior style: Inside the head tag, define the style tag, whose content is the css code
3. External styles:  
   - Define css resource files.  
   - Within the head tag, define the link tag to import the external resource file.  

- css syntax
```
selector{
    Attribute name 1: Attribute value 1;
    Attribute name 2: Attribute value 2;
     }
```
 - Selector: Filters elements with similar characteristics
   - Base selector（https://www.w3schools.com/css/css_selectors.asp）  
     1. id selector: It is recommended to have a unique id value in html #id value{}
     2. Element selector: Select elements with the same label name
        - id Indicates that the selector has a higher priority than the element selector
     3. class selector: Selects elements with the same class attribute value
        - Class selector takes precedence over element selector.        
  
    - Expand the selector https://www.runoob.com/cssref/css-selectors.html
