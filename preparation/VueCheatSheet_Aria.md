# Stručný tahák od Aria

#### Instance Vue
- Vytvořte instanci Vue: `new Vue({ options })`
- Připojte instanci Vue k elementu: `vm.$mount(element)`

#### Vazba dat
- Interpolace: `{{ data }}`
- Dvoucestná vazba: `v-model="data"`

#### Direktivy
- `v-bind:`: Vazba dat k atributu
- `v-on:`: Připojení posluchačů událostí
- `v-if`: Podmíněné vykreslování

#### Metody
- Definujte metody v opci `methods`
- Zavolejte metody v šabloně pomocí `v-on:click="methodName"`

#### Vypočítané vlastnosti
- Definujte vypočítané vlastnosti v opci `computed`
- Vypočítané vlastnosti jsou ukládány do mezipaměti na základě jejich závislostí

#### Životní cykly
- `beforeCreate`, `created`, `beforeMount`, `mounted`, `beforeUpdate`, `updated`, `beforeDestroy`, `destroyed`

#### Komponenty
- Zaregistrujte komponentu: `Vue.component('component-name', { options })`
- Použijte komponenty v šablonách: `<component-name></component-name>`

#### Vlastnosti
- Předávejte data z rodičovských do dětských komponent pomocí vlastností
- Vlastnosti jsou definovány v opci `props` dětské komponenty

#### Události
- Vydávejte vlastní události z dětských komponent pomocí `$emit(eventName, data)`
- Naslouchejte vlastním událostem v rodičovských komponentách pomocí `v-on:eventName="method"`

#### Sledovací mechanismy
- Sledujte změny v datových vlastnostech
- Definujte sledovací mechanismy v opci `watch`

[*zpět na readme*](https://github.com/Sudip2708/learning-VUE-with-the-help-of-AI#1-krok---sezn%C3%A1men%C3%AD-se-s-vue)   

