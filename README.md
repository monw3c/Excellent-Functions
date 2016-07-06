# Excellent-Functions
一些收集的优秀的函数

```js
window.$ = function(selector, context, undefined) {
	var matches = {
		'#': 'getElementById',
		'.': 'getElementsByClassName',
		'@': 'getElementsByName',
		'=': 'getElementsByTagName',
		'*': 'querySelectorAll'
	}[selector[0]]; 
	var el = (((context === undefined) ? document: context)[matches](selector.slice(1)));//selector.slice(1)去掉例如'.name'&&'#name'的'.#'后的值
	return ((el.length < 2) ? el[0]: el);
};
```
