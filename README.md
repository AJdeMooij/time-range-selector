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
    <script src="timerange-selector-ui-/jquery.ui.timerangeselector.js"></script>
  </head>
    
  <body>
    <div id="time-selector"></div>
    
    <script>
      $("time-selector").selectorTable();
    </script>
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
      <td><a href="#api-resolution">Resolution</a></td>
      <td><a href="#api-destroy">destroy()</a></td>
    </tr>
    <tr>
      <td><a href="#api-tableClass">tableClass</a></td>
      <td><a href="#api-getTimes">getTimes()</a></td>
    </tr>
    <tr>
      <td><a href="#api-hourStart">hourStart</a></td>
      <td><a href="#api-reset">reset()</a></td>
    </tr>
    <tr>
      <td><a href="#api-hourEnd">hourEnd</a></td>
      <td></td>
    </tr>
    <tr>
      <td><a href="#api-hourText">hourText</a></td>
      <td></td>
    </tr>
    <tr>
      <td><a href="#api-selected">selected</a></td>
      <td></td>
    </tr>
    <tr>
      <td><a href="#api-hourFormat24">hourFormat24</a></td>
      <td></td>
    </tr>
  </tbody>
</table>

<h3 name="api-resolution">Resolution</h3>
integer
```javascript
$("time-selector").selectorTable({
  options: {
    resolution: 12 // Default
  } 
});
```
Sets the number of cells for each row. 
A resolution of 6 means that each cell equals 10 minutes. 
For best performances, use a number that 60 is divisible by.

<h3 name="api-tableClass">tableClass</h3>
String
```javascript
$("time-selector").selectorTable({
  options: {
    tableClass: '' // Default
  }
});
```
A string with all the classnames you want to add to your table, seperated by spaces.

<h3 name="api-hourStart">hourStart</h3>
int (in range 0, 24)
```javascript
$("time-selector").selectorTable({
  options: {
    hourStart: 1 // Default
  }
});
```
The first hour that shows in the table. By default, the table starts at 1 am.

<h3 name="api-hourEnd">hourEnd</h3>
int (in range 0, 24)
```javascript
$("time-selector").selectorTable({
  options: {
    hourEnd: 24 // Default
  }
});
```
The last hour that shows in the table. By default, the table ends at 12 pm.

<h3 name="api-hourText">hourText</h3>
String
```javascript
$("time-selector").selectorTable({
  options: {
    hourText: '' // Default
  }
});
```
The table that is generated, will contain a number referring to the hour as the first cell of each row. 
To append a text behind this number, use the hourText option. The string provided in this option will be appended to the first cell of each row.

<h3 name="api-selected">selected</h3>
json array
```javascript
$("time-selector").selectorTable({
  options: {
    selected: [ // Default is NULL
      ["08:30", "18:00"],
      ["20:00", "21:00"]
    ]
  }
});
```
If you want to initialize the time selector table with times already pre-selected, use the 'selected' option.
As an argument, give a json string of jsonstrings, the deepest json string of which always contains two elements: the begin-time of the selected time-range and the end-time as a string. 
The times should be given in the HH:ii format (as you can see in the example code).

<h3 name="api-hourFormat24">hourFormat24</h3>
boolean
```javascript
$("time-selector").selectorTable({
  options: {
    hourFormat24: true // Default
  }
});
```
Set this option to false if you want to use the 12-hour clock. This changes the formatting of the first cell of each row to show the time as a number from 0 to 12 with 'am' or 'pm' added.


<h3 name="destroy">destroy()</h3>
```javascript
$( 'time-selector' ).selectorTable( 'destroy' );
```
Removes the time-selector table from the div-element it had been attached to and returns the div to it's old state.
<h3 name="api-getTimes">getTimes()s</h3>
```javascript
var times = $( 'time-selector' ).selectorTable( 'getTimes' );
```
Returns a json array of arrays containing time-range begin and end pairs. All the times are returned as moment objects. 
The typical format of this json would be:
  [ [moment(starttime1), moment(endtime1)], [moment(starttime2), moment(endtime2)] ]
  
<h3 name="reset">reset()</h3>
```javascript
$( 'time-selector' ).selectorTable( 'reset' );
```
Resets the time-selector table to its original state. This method may be invoked by a user clicking a button, to undo all the times they selected and/or re-selecting the timeranges set in the selected-option.
