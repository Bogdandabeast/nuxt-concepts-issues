<script setup>
const msg = "Ejemplos de la sintaxis template de Vue";
const rawHtml = '<span style="color: red">This should be red.</span>';
const dynamicId = '5';
const isButtonDisabled = true;
const objectOfAttrs = {
    id: 'container',
    class: 'wrapper',
    style: 'background-color:green'
};
const number = 2;
const ok = true;
const message = "Ronald mensaje";
const id = 69;

const seen = ref(true)

const sumar = (a,b) => {
    return a + b;
}
</script>

<template>
    <h1>Hola desde index.vue</h1>
    <span>Message: {{ msg }}</span>
    <p>Using text interpolation: {{ rawHtml }}</p>
    <p>Using v-html directive: <span v-html="rawHtml"></span></p>
    <h2>Atr binding</h2>
    <h3>Mustaches cannot be used inside HTML attributes. Instead, use a v-bind directive:</h3>
    <div v-bind:id="dynamicId">the id of this div is 5</div>
    <div :id="dynamicId">the short version of v-bind:id</div>
    <h2>Boolean atrr</h2>
    <h3>Boolean attributes are attributes that can indicate true / false values by their presence on an element. For example, disabled is one of the most commonly used boolean attributes.</h3>
    <h3>v-bind works a bit differently in this case:</h3>
    <button :disabled="isButtonDisabled">Button</button>
    <h3>You can also bind a js object</h3>
    <div v-bind="objectOfAttrs">Hola</div>
    <h2>Using JavaScript Expressions
​

So far we've only been binding to simple property keys in our templates. But Vue actually supports the full power of JavaScript expressions inside all data bindings:</h2>

{{ number + 1 }}

{{ ok ? 'YES' : 'NO' }}

{{ message.split('').reverse().join('') }}

<div :id="`list-${id}`"></div>
<h2>Expressions Only</h2>
<h3>Each binding can only contain one single expression. An expression is a piece of code that can be evaluated to a value. A simple check is whether it can be used after return.

Therefore, the following will NOT work:</h3>
<!-- this is a statement, not an expression: -->


<!-- flow control won't work either, use ternary expressions -->
{{  sumar(1,5 )}}
<h2>Directives</h2>
<h3>Directives are special attributes with the v- prefix. Vue provides a number of built-in directives, including v-html and v-bind which we have introduced above.

Directive attribute values are expected to be single JavaScript expressions (with the exception of v-for, v-on and v-slot, which will be discussed in their respective sections later). A directive's job is to reactively apply updates to the DOM when the value of its expression changes. Take v-if as an example:</h3>

<p v-show="seen">Now you see me valor : {{ seen }}</p>
<button @click="seen = !seen">hide/show</button>


</template>