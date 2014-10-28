Timerange Selector (JQuery UI Widget)
===================

jQuery UI widget for dragging over a table to select (multiple) timeranges. The widget is tied to an html div. 
Once the widget is initialized, it generates a table with a row for each hour and a cell for each minute interval within that hour. 
The user can select multiple timeranges in the table, usually for one single day. 

HTML:
```html
<html>
  <head>
    <!-- Load JQuery -->
    <!-- Load moments.js -->
    <link type="text/css" rel="stylesheet" href="timerange-selector-ui/timerangeselector.css"/>
    
  <body>
    <div id="time-selector"></div>
  </body>
</html>
```


<h2>API</h2>
<table>
<thead>
<th>Options</th>
<th>Methods</th>
</thead>
<tbody>
<tr>
<td>Resolution</td>
<td>_create</td>
</tr>

<tr><td>tableClass</td><td>destroy</td></tr>

<tr><td>hourStart</td><td>getTimes</td></tr>

<tr><td>hourEnd</td><td>reset</td></tr>

<tr><td>hourText</td><td></td></tr>

<tr><td>selected</td><td></td></tr>

<tr><td>hourFormat24</td><td></td></tr>

</tbody>
</table>


