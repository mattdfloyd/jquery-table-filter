##jquery.table_filter.js    

####What's this?
This is a jQuery plugin that uses input from a textbox to filter rows in HTML tables. its fast and 
lightweight (the minified version is just 872 bytes).

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
			'cell_selector': 'td'
		});
	});
```

####Settings:
`table` (CSS DOM selector) - No default
+	Table with the rows you want to filter. This setting has no default value, and is required.

`filter_inverse` (boolean) - default: False
+	`True` - filters out rows that match the filter text
+	`False` - filters out rows that do not match the filter text

`enable_space` (boolean) - default: False
+	`True` - it uses space in filter text as delimiters. e.g. if filter text = "good boy", it will search rows for "good" and "boy" seperately
+	`False` - it will not use space as a delimiter. e.g. "good boy" will be treated as one word.

`cell_selector` (string) - default: 'td'
+	Allows override of the cell selector, so that only certain cells will be filtered. Example setting to only filter on the first column: {'cell_selector':'td:first-child'}

####License
MIT License: http://www.opensource.org/licenses/mit-license.php    
