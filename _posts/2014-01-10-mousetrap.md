---
layout: post
title: Mousetrap
description: "Using knockout the easy way"
modified: 2014-01-08
tags: [Mousetrap,javascript,library,shortcuts ]
image:
  feature: abstract-10.jpg
  credit: dargadgetz
  creditlink: http://www.dargadgetz.com/ios-7-abstract-wallpaper-pack-for-iphone-5-and-ipod-touch-retina/
comments: true
share: true  
---
[Mousetrap](http://craig.is/killing/mice) is a simple library for handling keyboard shortcuts in Javascript. It works like a charm. Just include it in your Javascript and you can bind certain functions to shortcuts.

~~~ javascript
// single keys
Mousetrap.bind('4', function() { highlight(2); });
Mousetrap.bind('x', function() { highlight(3); }, 'keyup');

// combinations
Mousetrap.bind('command+shift+k', function(e) {
    highlight([6, 7, 8, 9]);
    return false;
});

Mousetrap.bind(['command+k', 'ctrl+k'], function(e) {
    highlight([11, 12, 13, 14]);
    return false;
});

// gmail style sequences
Mousetrap.bind('g i', function() { highlight(17); });
Mousetrap.bind('* a', function() { highlight(18); });

// konami code!
Mousetrap.bind('up up down down left right left right b a enter', function() {
    highlight([21, 22, 23]);
});
~~~

### [Bind dictionary](https://github.com/ccampbell/mousetrap/tree/master/plugins/bind-dictionary)
The bind dictionary extension makes it even possible to bind multiple combinations in a single bind call.

~~~ javascript 
Mousetrap.bind({
    'a': function() { console.log('a'); },
    'b': function() { console.log('b'); }
});
~~~