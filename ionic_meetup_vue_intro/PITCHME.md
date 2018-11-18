# Vue.js primer for Ionic / Angular Devs

Stephan Gieffers

IONIC Meeting Berlin, November 14th, 2018

---
#### Vue.js - Why do we care?
- buzz
- sick of angular but not sick enough for react
- Ionic 4 && Vue.js
- beginners mind

---
#### Pages / Templates

```
<span>Message: {{ msg }}</span>

<span v-html="rawHtml"></span>

<button v-bind:disabled="isButtonDisabled">Button</button>

<p v-if="seen">Now you see me</p>

<a v-on:click="doSomething"> ... </a>

<form @submit.prevent="onSubmit"> ... </form>

<div :class="{ active: isActive }"></div>

<li v-for="item in items">
  {{ item.message }}
</li>
```

*all examples from https://vuejs.org/v2/guide/* 

---
#### Components - as Pages

```
export default {
  data: () => {
    message: 'Hello',
    guests: [
      {id: 1, name: 'Peter', stars: 0},
      {id: 2, name: 'Paul', stars: 0 },
      {id: 3, name: 'Marry', stars: 0},
    ]
  },
  computed: {
    guestsSorted() {
      return this.guests.sort();
    }
  }
  methods: {
    addStar(guest) {
      guest.stars += 1;
    }
  }
}

```
---

#### Components - as components
```
<my-list :sortBy="sortCriteria" v-on:like="startFireworks()"></my-list>

export default {
  props: {
    sortBy: String,
  }
  data: () => { ... },
  computed: { ... }
  methods: { ... $emit('like', data) .. }
}

# some advanced stuff: scoped slots
<todo-list v-bind:todos="todos">
  <template slot-scope="slotProps">
    <span v-if="slotProps.todo.isComplete">✓</span>
    {{ slotProps.todo.text }}
  </template>
</todo-list>

```
---
#### Event Handling - Data Flow

- within components: two way binding
- between components: unilateral data flow
  - downward via "properties"
  - upward via Events
- global Events are an option

---
#### Services / Providers
- nope - vue.js doesn't care!
- use vanilla JS
- challenge: intercomponent communication
  - EventBus
  - Router
  - Vuex
  - RX-Js
  - ...

---
#### Build Environment
- not required - vue can be loaded from cdn
- usually Webpack
- brand new: Vue-CLI-3
  - webpack v4
  - plugins for unit-test, e2e-test, lint, ...
    
    => no need to eject

---
#### Meet the family
- Vue Router
- Vuex
- Vue-Test-Utils

---
#### Eco-System
- great baseline documentation
- community driven - less commercial
- "me too" on everything react

---
#### Buzzwords
*discussion on demand - maybe at end of session*

- single file components
- Vue-CLI-3
- SSR
- NUXT
- Vuepress
- Vuetify
- BootstrapVue
- Vue Native
- Vue DevTools

---
 
#### Main differences to Angular?
*highly subjective*
- easier to get started
- Vanilla JS is just fine
- testing is straightforward
- components rule


**but if you need to solve a complex problem you will end up with a complex Vue App!**

---

#### Dump Angular?

	?

---

##### Thank you
**sg@vs-5.de**

Getting started:

- https://vuejs.org/
- https://cli.vuejs.org/



