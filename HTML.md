<h3>HTML</h3>

---

Grammar:  
1. The extension of the html document is html or htm  
2. Labels are divided into:  
   - Containment tags: there are start tags and end tags, such as <html></html>     
   - 自闭和标签: start tag and end tag together, such as <br/>
3. Labels can be nested
4. You can define attributes in the start tag. Properties consist of key-value pairs, and values need to be enclosed in quotation marks (either single or double)
5. html tags are not case sensitive, but lowercase is recommended

<b>tag study</b>：  
1. File label. 
   - html
   - head
   - title
   - body
   - <!DOCTYPE html>. 
2. Text label
  - h1 to h6
  - p
  - br
  - hr
  - b
  - i //italic
  - font

3. Picture label
4. List tag
5. Link tag
```
  <a href="">click</a>
  <a href="mailto:mengjiayu2021@gmail.com">Contact Us</a>
```  
  - target:
    - _self:default value,open in current page
    - _blank:open in blank page
6. Table tag
```
<table>
  <tr>
    <th>Company</th>
    <th>Contact</th>
    <th>Country</th>
  </tr>
  <tr>
    <td>Alfreds Futterkiste</td>
    <td>Maria Anders</td>
    <td>Germany</td>
  </tr>
  <tr>
    <td>Centro comercial Moctezuma</td>
    <td>Francisco Chang</td>
    <td>Mexico</td>
  </tr>
</table>
```
7. div and span  
   - Each div takes up an entire line of block-level labels
   - span： Text information is displayed on a single line, with labels inside the line
8. form
   - Used to collect user input data; used to interact with the server. 
     - action: Specify the URL to submit the data
     - method: get and post
       - get：1. he request parameters are displayed in the address bar and are encapsulated in the request line. 
              2. The request parameter size is limited. 
              3. Not very safe. 
       - post: 1. Request parameters are encapsulated in the request body instead of displayed in the address bar. 
               2. There is no limit to the size of the request parameter. 
               3. Relatively safe. 
     - name：For data in a form entry to be submitted, you must specify the NAME attribute

```
<form action="/action_page.php" method="get">
  <label for="fname">First name:</label>
  <input type="text" id="fname" name="fname"><br><br>
  <label for="lname">Last name:</label>
  <input type="text" id="lname" name="lname"><br><br>
  <input type="submit" value="Submit">
  <input type="submit" formaction="/action_page2.php" value="Submit as Admin">
</form>
```
```
<input type="text">  
<input type="radio">
<input type="password">
<input type="checkbox">
  
```
- text:
  * placeholder: Specify the prompt information of the input box. When the content of the input box changes, the prompt information is automatically cleared  
- radio：
  * For multiple checkboxes to have a radio effect, the NAME property of the multiple checkboxes must have the same value
  * A VALUE attribute is typically given to each checkbox, specifying the value to submit when it is selected
  * CHECKED property, the default value can be specified
> label: The for attribute of the label usually corresponds to the id attribute of the input. If so, clicking on the label field will bring the input field into focus  
- select
- textarea
- file 
- submit
- button
- image： Image submit button, you can specify the image path through the src attribute
