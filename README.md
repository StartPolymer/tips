# Polymer Tips

## Debugging

### 1. Data binding

#### Two-way data binding problems?

- For `<my-element foo={{bar}}>` make sure `foo` is a notifying property! ➡️ `notify: true`

#### Binding to a dataset attribute not working?

- Make sure you're using `$=` attribute binding! ➡️ `<button data-index$=[[bar]]>`

### 2. Is your custom element firing an event but you can't seem to listen to it from the outside?

➡️ Make sure it's bubbling!
- `this.dispatchEvent(new CustomEvent('meow', {bubbles: true, composed: true}));`

### 3. Made a pretty 💣 element but can't see it on the page? 🙀

➡️ Check your superclass methods!
- call `super()` if you're in the constructor
- and `super.connectedCallback()` for the connected callback
- and don't forget about the tricky `super.ready()` too! Or nothing will happen.

---

### Resources

- [twitter.com/polymer](https://twitter.com/polymer)
