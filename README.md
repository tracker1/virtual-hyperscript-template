# virtual-hyperscript-template
ES6 tagged-template handler to convert html to virtual-dom object

This is a placeholder for me to work against, the goal is to get something as [described here](https://github.com/Raynos/mercury/issues/130) for mercury working...

```js
var t = require('virtual-hyperscript-template');
App.render = function render(state) {
  return t`
    <div class="counter">
      The state <code>clickCount</code>
      has value: ${state.value}.
      <button ${t.click(hg.send(state.channels.clicks))}>Click me!</button>
    </div>
  `;
};
```

This will require ES6, may also require virtual-dom and mercury as peer dependencies... will have to work through this as time permits.  If the processing time takes more than 300% of the time for just using virtual-dom directly, I likely won't be using this technique.  Or may come up with something else for a mapping structure.

May be able to cache the converted templates to improver performance.

```
t(this)`
  ...
`
```

Could reference a pre-computed template, and simply update the virtual dom tree as it stands... need to test.
