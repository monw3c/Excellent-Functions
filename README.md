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

```js
addHandler: function( types, handler ) {
            if( !Array.isArray( types ) ) {
                types = [ types ];
            }
            types.forEach( function( type ) {
                handlers[ type ] = handler;
            });
},

removeHandler: function( types ) {
            this.addHandler( types, undefined );
}
```

```js
function isObjectValueEqual(a, b) {
	//判断两个对象是否相等
        var aProps = Object.getOwnPropertyNames(a);
        var bProps = Object.getOwnPropertyNames(b);
	
	if(a===b){
	    return true;
	}

        if (aProps.length != bProps.length) {
            return false;
        }

        for (var i = 0; i < aProps.length; i++) {
            var propName = aProps[i];

            if (a[propName] !== b[propName]) {
                return false;
            }
        }

        return true;
}
```

```js
function validate(mobile) {
    const VALIDATE_REG = /^(0|86|17951)?(13[0-9]|15[012356789]|166|17[0-9]|18[0-9]|14[57]|19[89])[0-9]{8}$/;
    return VALIDATE_REG.test(mobile); 
}
```
