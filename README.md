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

```js
window.uuid: function() {
	return "xxx-" + Math.random().toString(36).substring(2, 15) + Math.random().toString(36).substring(2, 15)
}
	
```

```js
function MyArray() {}
MyArray.prototype.length = 0;
(function() {
	var methods = ['push', 'pop', 'shift', 'unshift', 'slice', 'splice', 'join'];
	for (var i = 0; i < methods.length; i++)(function(name) {
		MyArray.prototype[name] = function() {
			return Array.prototype[name].apply(this, arguments);
		}
	})(methods[i]);
})();
var mine = new MyArray();
mine.push(1, 2, 3);
```
