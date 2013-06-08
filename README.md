##jquery.table_filter.js    

####What's this?
This is a jQuery plugin that uses input from a textbox to filter rows in HTML tables.

####Usage:
Include `jquery.table_filter.js` or `jquery.table_filter.min.js` in your HTML file. 
This plugin depends on the jQuery library, so you should have that as well.
```html
	<!-- Jquery library called before "jquery.table_filter.js" -->
	<script type="text/javascript" src="jquery.table_filter.js"></script>
```

You can then call the plugin using the CSS Selector for your Table and Text input. 
```html
	<input type="text" class="f_txt"/>
	<table class="f_tbl">...</table>
```

```javascript
	//basic initialisation
	$(function(){ 
	  	$(".f_txt").table_filter({'table':'.f_tbl'});
	});
```
```javascript
	//full initialisation
	$(function(){ 
	  	$(".f_txt").table_filter({
			'table':'.f_tbl',
			'filter_inverse':false,
			'enable_space':false,
			'cell_selector': 'td',
			'no_result': 'No match found.',
			'no_result_selector': '#no_result'
		});
	});
```

####Settings:
`table` (CSS selector) - ''
+	Table with the rows you want to filter. This setting has no default value, and is required.

`filter_inverse` (boolean) - default: false
+	`True` - filters out rows that match the filter text
+	`False` - filters out rows that do not match the filter text

`enable_space` (boolean) - default: false
+	`True` - it uses space in filter text as delimiters. e.g. if filter text = "good boy", it will search rows for "good" and "boy" seperately
+	`False` - it will not use space as a delimiter. e.g. "good boy" will be treated as one word.

`cell_selector` (CSS selector) - default: 'td'
+	Allows override of the cell selector, so that only certain cells will be filtered. Example setting to only filter on the first column: {'cell_selector':'td:first-child'}

`no_result` (string) - default: ''
+	If you want to display a message when a search doesn't return any matched rows (e.g. "No Match found."), you can set that message here. If this value is left empty, no message will be shown. If a message is set here, the "no_result_selector" should also be set.

`no_result_selector` (CSS selector) - default: ''
+	Element that will display your "no_result" message (usually a div tag).

####License
MIT License: http://www.opensource.org/licenses/mit-license.php    
