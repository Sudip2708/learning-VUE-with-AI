<a id="top"></a>

# Podrobnější tahák od ChatGPT
[*zpět na readme*](https://github.com/Sudip2708/learning-VUE-with-the-help-of-AI#1-krok---sezn%C3%A1men%C3%AD-se-s-vue)   

## Obsah
1. [Installation](#installation)
2. [Instance](#instance)
3. [Template Syntax](#template-syntax)
4. [Directives](#directives)
5. [Computed Properties and Watchers](#computed-properties-and-watchers)
6. [Class and Style Bindings](#class-and-style-bindings)
7. [Conditional Rendering](#conditional-rendering)
8. [List Rendering](#list-rendering)
9. [Event Handling](#event-handling)
10. [Form Input Bindings](#form-input-bindings)
11. [Components](#components)

## Installation
### Via CDN
Použití Vue.js přes CDN.
```html
<script src="https://cdn.jsdelivr.net/npm/vue@2"></script>
```

### Via npm
Instalace Vue.js přes npm.
```bash
npm install vue
```

[*zpět na začátek*](#top) / [*zpět na readme*](https://github.com/Sudip2708/learning-VUE-with-the-help-of-AI#1-krok---sezn%C3%A1men%C3%AD-se-s-vue)   

## Instance
Vytvoření nové Vue instance.
```js
var app = new Vue({
  el: '#app',
  data: {
    message: 'Hello Vue!'
  }
});
```

[*zpět na začátek*](#top) / [*zpět na readme*](https://github.com/Sudip2708/learning-VUE-with-the-help-of-AI#1-krok---sezn%C3%A1men%C3%AD-se-s-vue)   

## Template Syntax
### Interpolations
Vložení hodnoty proměnné do HTML.
```html
<span>{{ message }}</span>
```

### Directives
Použití Vue.js direktiv.
```html
<p v-if="seen">Now you see me</p>
```

[*zpět na začátek*](#top) / [*zpět na readme*](https://github.com/Sudip2708/learning-VUE-with-the-help-of-AI#1-krok---sezn%C3%A1men%C3%AD-se-s-vue)   

## Directives
- `v-bind`: Vazba atributu
- `v-model`: Dvoucestné vázání dat
- `v-if`: Podmíněné vykreslování
- `v-else-if`: Else-if podmíněné vykreslování
- `v-else`: Else podmíněné vykreslování
- `v-for`: Smyčkové vykreslování
- `v-on`: Posluchač událostí
- `v-show`: Přepínání viditelnosti
- `v-pre`: Přeskočení kompilace pro tento prvek a všechny jeho podřízené prvky
- `v-cloak`: Udržuje prvek skrytý, dokud není dokončena kompilace Vue
- `v-once`: Vykreslí prvek a komponentu pouze jednou

[*zpět na začátek*](#top) / [*zpět na readme*](https://github.com/Sudip2708/learning-VUE-with-the-help-of-AI#1-krok---sezn%C3%A1men%C3%AD-se-s-vue)   

## Computed Properties and Watchers
### Computed Properties
Definování vypočítaných vlastností.
```js
var app = new Vue({
  el: '#app',
  data: {
    message: 'Hello'
  },
  computed: {
    reversedMessage: function () {
      return this.message.split('').reverse().join('')
    }
  }
});
```

### Watchers
Sledování změn v datech a reagování na ně.
```js
var app = new Vue({
  el: '#app',
  data: {
    question: '',
    answer: 'I cannot give you an answer until you ask a question!'
  },
  watch: {
    question: function (newQuestion, oldQuestion) {
      this.answer = 'Waiting for you to stop typing...'
      this.getAnswer()
    }
  },
  methods: {
    getAnswer: _.debounce(
      function () {
        if (this.question.indexOf('?') === -1) {
          this.answer = 'Questions usually contain a question mark. ;-)'
          return
        }
        this.answer = 'Thinking...'
        var vm = this
        axios.get('https://yesno.wtf/api')
          .then(function (response) {
            vm.answer = _.capitalize(response.data.answer)
          })
          .catch(function (error) {
            vm.answer = 'Error! Could not reach the API. ' + error
          })
      },
      500
    )
  }
});
```

[*zpět na začátek*](#top) / [*zpět na readme*](https://github.com/Sudip2708/learning-VUE-with-the-help-of-AI#1-krok---sezn%C3%A1men%C3%AD-se-s-vue)   

## Class and Style Bindings
### Object Syntax
Vázání tříd pomocí objektové syntaxe.
```html
<div v-bind:class="{ active: isActive }"></div>
```

### Array Syntax
Vázání tříd pomocí pole.
```html
<div v-bind:class="[isActive ? 'active' : '', errorClass]"></div>
```

### Inline Styles
Vázání stylů pomocí inline syntaxe.
```html
<div v-bind:style="{ color: activeColor, fontSize: fontSize + 'px' }"></div>
```

[*zpět na začátek*](#top) / [*zpět na readme*](https://github.com/Sudip2708/learning-VUE-with-the-help-of-AI#1-krok---sezn%C3%A1men%C3%AD-se-s-vue)   

## Conditional Rendering
Podmíněné vykreslování prvků.
```html
<h1 v-if="awesome">Vue is awesome!</h1>
<h1 v-else>Oh no 😢</h1>
```

## List Rendering
Vykreslování seznamů.
```html
<ul>
  <li v-for="item in items" v-bind:key="item.id">
    {{ item.text }}
  </li>
</ul>
```

[*zpět na začátek*](#top) / [*zpět na readme*](https://github.com/Sudip2708/learning-VUE-with-the-help-of-AI#1-krok---sezn%C3%A1men%C3%AD-se-s-vue)   

## Event Handling
### Listening to Events
Poslouchání událostí.
```html
<button v-on:click="doSomething">Click me</button>
```

### Methods in Inline Handlers
Použití metod v inline handlerech.
```html
<button v-on:click="doSomething('hello', $event)">Click me</button>
```

[*zpět na začátek*](#top) / [*zpět na readme*](https://github.com/Sudip2708/learning-VUE-with-the-help-of-AI#1-krok---sezn%C3%A1men%C3%AD-se-s-vue)   

## Form Input Bindings
### Text
Dvoucestné vázání pro textové vstupy.
```html
<input v-model="message" placeholder="edit me">
<p>Message is: {{ message }}</p>
```

### Checkbox
Dvoucestné vázání pro zaškrtávací políčko.
```html
<input type="checkbox" v-model="checked">
<p>Checked: {{ checked }}</p>
```

### Radio
Dvoucestné vázání pro radio tlačítka.
```html
<input type="radio" v-model="picked" value="One">
<input type="radio" v-model="picked" value="Two">
<p>Picked: {{ picked }}</p>
```

### Select
Dvoucestné vázání pro select box.
```html
<select v-model="selected">
  <option disabled value="">Please select one</option>
  <option>A</option>
  <option>B</option>
  <option>C</option>
</select>
<span>Selected: {{ selected }}</span>
```

[*zpět na začátek*](#top) / [*zpět na readme*](https://github.com/Sudip2708/learning-VUE-with-the-help-of-AI#1-krok---sezn%C3%A1men%C3%AD-se-s-vue)   

## Components
### Global Registration
Globální registrace komponenty.
```js
Vue.component('my-component', {
  template: '<div>A custom component!</div>'
});
```

### Local Registration
Lokální registrace komponenty.
```js
var Child = {
  template: '<div>A custom component!</div>'
};

var app = new Vue({
  el: '#app',
  components: {
    'my-component': Child
  }
});
```

### Props
Předávání dat do komponenty pomocí props.
```js
Vue.component('child', {
  props: ['message'],
  template: '<span>{{ message }}</span>'
});
```

### Custom Events
Vytváření vlastních událostí.
```js
Vue.component('button-counter', {
  data: function () {
    return {
      count: 0
    }
  },
  template: '<button v-on:click="count++">You clicked me {{ count }} times.</button>'
});
```

[*zpět na začátek*](#top) / [*zpět na readme*](https://github.com/Sudip2708/learning-VUE-with-the-help-of-AI#1-krok---sezn%C3%A1men%C3%AD-se-s-vue)   


