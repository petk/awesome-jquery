# A guide for making awesome jQuery plugin

**Best practices for modern jQuery plugin development**

Currently there isn't any cannonical way to develop a jQuery plugin so when developing a jQuery plugin, some **best practices** should be followed besides the [official documentation](http://learn.jquery.com/plugins/).

* [1. Protect the $ alias and add scope](#tip-1)
* [2. Use package manager(s)](#tip-2)
* [3. Plugin should be actively maintained](#tip-3)
* [4. Provide default settings](#tip-4)
* [5. Documentation](#tip-5)
* [6. Testing](#tip-6)
* [7. Enable chaining](#tip-7)
* [8. Easy Usage](#tip-8)


## 1. Protect the `$` alias and add scope<a name="tip-1"></a>

Use a closure and never create plugin dependant on `$` that is referencing jQuery. Application might depend on some other libraries or frameworks also and it may have grabbed `$` before jQuery was loaded.

```javascript
(function($) {
    // code here can use $ to reference jQuery
})(jQuery);
```

## 2. Use package manager(s)<a name="tip-2"></a>

JavaScript has a **lot** of package managers (npm, Bower, component, spm, jam, jspm, Ender, volo, Duo). Since all of them are actually used by users you should support some packagers as well. Very good pick is `npm` since jQuery itself is recommending and also `Bower` because it is very widely and simple to use.


## 3. Plugin should be actively maintained<a name="tip-3"></a>

Creating and publishing open source plugin is big contribution to jQuery community and a lot of work for sure. However making project open source we'll sooner or later encounter some feature that we can't live without or some nasty bug. Therefore maintaining the plugin such as
accepting pull request on GitHub, fixing bugs, support newer versions of jQuery core etc is definitely a big plus for the project.


## 4. Provide default settings<a name="tip-5"></a>

Plugins in most cases have some configuration. If user don't set these plugin should have set default values for easier and faster plugin implementation.

```javascript
$("#select").myPlugin({mode: 'brush', lineWidth: 3, color: '#c3c3c3'});
```

```javascript
var defaultSettings = {
    mode            : 'Pencil',
    lineWidth       : 2,
    color 			: '#ff0000'
};
```

## 5. Documentation<a name="tip-6"></a>

Always document your code by adding meaningful concise comments to the top of the plugin file and in cases of complex plugins creating separate `README` file or `doc` folder with deep explanations and demostration of the plugin. This helps people understand and use your plugin better.


## 6. Testing<a name="tip-7"></a>

Test your plugin in multiple browser.


## 7. Enable chaining

Unless your plugin returns a value, the last line of your plugin function should be:

```javascript
return this;
```

this enables chaining of method calls:

```javascript
$("div#myid").yourPlugin().anotherPlugin().yetAnotherPlugin();
```

## 8. Easy Usage

Plugin should be easy to use and should work out of the box withouth the need to browse the documentation, set options or editing plugin code.

If possible make sure that plugin can initialize itself:

```html
<div class="mySliderPlugin"></div>
```

without the need to add or edit any JavaScript:

```javascript
$('.mySliderPlugin').mySliderPlugin();
```

Plugin can initialize itself:

```javascript
$(function() {
    $(".myjqWidget").myjqWidget();
});
```
