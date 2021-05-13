# Built-in Event

At the beginning of the design of HeiGoBackTop, some usage scenarios were considered for developers. With the help of built-in events, developers can meet their project needs more quickly.

The built-in events of HeiGoBackTop are mainly divided into two types, one is [one-time temporary event](#), and the other is [continuous event](#).

## one-time temporary event

[onBeforeCreate](/configuration) and [onAfterCreate](/configuration) events are typical one-time temporary events. If you bind the corresponding event, it will be triggered automatically before the initialization of HeiGoBackTop or at the end of the initialization, and will be automatically destroyed after the trigger.

```javascript
let example = new HeiGoBackTop();

example.onBeforeCreate(function(){
	console.log('I am preparing to create');
});

example.onAfterCreate(function(){
	console.log('created');
});
```

## Continuing event

[onShow](/configuration) and [onHide](/configuration) are typical continuous events. If you bind the corresponding event, each time the button is displayed or hidden Triggered when.

```javascript
example.onShow(function(){
	console.log('The button is displayed, what do you want to do?');
});

example.onHide(function(){
	console.log('The button is being hidden, what do you want to do?');
});
```

For more events, please see [Configuration](/configuration)