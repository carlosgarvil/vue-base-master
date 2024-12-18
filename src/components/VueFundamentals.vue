<template>
    <h1>Vue fundamentals</h1>
    <p>Este es un componente de ejemplo. Aquí puedes encontrar los fundamentos de VueJS.</p>
    <p>
        El texto se ha generado casi en su totalidad usando Copilot, corrigiendo levemente algunos errores y agregando algunos detalles para simplificar los ejemplos. Para una explicación más detallada de los fundamentos de VueJS, puedes consultar la documentación oficial de VueJS en <a href="https://v3.vuejs.org/guide/introduction.html" target="_blank">https://v3.vuejs.org/guide/introduction.html</a>.
    </p>

    <h3>Attribute Bindings</h3>
    <p>
        Sirve para enlazar un atributo de un elemento HTML a una expresión de VueJS. En este caso, el atributo <code>src</code> de la imagen se enlaza a la variable <code>imageSrc</code> que se encuentra en el script del componente. Puedes usar <code>v-bind</code> o la forma abreviada<code>:</code> para hacer el enlace.
    </p>
    <p class="text-center">
        <code>&lt;img v-bind:src="imageSrc" alt="Vue logo" class="logo col-2" width="125" height="125" /&gt;</code>
    </p>
                
            

    <p class="text-center">
        <code>&lt;img :src="imageSrc" alt="Vue logo" class="logo col-2" width="125" height="125" /&gt;</code>
    </p>
    <h3>Form Bindings</h3>
    <p>
        Sirve para enlazar el valor de un elemento de formulario a una expresión de VueJS. En este caso, el valor del input se enlaza a la variable <code>message</code> que se encuentra en el script del componente. Puedes usar <code>v-model</code> para hacer el enlace.
    </p>
    <p class="text-center">
        <code>&lt;input v-model="message" type="text" /&gt;</code>
    </p>
    <h3>Event Bindings</h3>
    <p>
        Sirve para enlazar un evento de un elemento HTML a una expresión de VueJS. En este caso, el evento <code>click</code> del botón se enlaza a la función <code>reverseMessage</code> que se encuentra en el script del componente. Puedes usar <code>v-on</code> o la forma abreviada <code>@</code> para hacer el enlace.
    </p>
    <p class="text-center">
        <code>&lt;button v-on:click="reverseMessage"&gt;Reverse Message&lt;/button&gt;</code>
    </p>
    <p class="text-center">
        <code>&lt;button @click="reverseMessage"&gt;Reverse Message&lt;/button&gt;</code>
    </p>
    <h3>Computed Properties</h3>
    <p>
        Sirve para definir propiedades computadas. En este caso, la propiedad computada <code>reversedMessage</code> se calcula a partir de la propiedad <code>message</code> que se encuentra en el script del componente. Puedes usar <code>computed</code> para definir propiedades computadas.
    </p>
    <p class="text-center">
        <code>computed: { reversedMessage() { return this.message.split('').reverse().join('') } }</code>
    </p>
    <h3>Conditional Rendering</h3>
    <p>
        Sirve para renderizar condicionalmente un elemento HTML. En este caso, el elemento <code>p</code> se renderiza si la propiedad <code>message</code> que se encuentra en el script del componente es mayor a 5. Puedes usar <code>v-if</code> para renderizar condicionalmente un elemento HTML.
    </p>
    <p class="text-center">
        <code>&lt;p v-if="message.length &gt; 5"&gt;Mensaje mayor a 5 caracteres&lt;/p&gt;</code>
    </p>
    <h3>List Rendering</h3>
    <p>
        Sirve para renderizar una lista de elementos HTML. En este caso, el elemento <code>li</code> se renderiza por cada elemento del arreglo <code>fruits</code> que se encuentra en el script del componente. Puedes usar <code>v-for</code> para renderizar una lista de elementos HTML.
    </p>
    <p class="text-center">
        <code>&lt;li v-for="fruit in fruits" :key="fruit"&gt;{{ fruit }}&lt;/li&gt;</code>
    </p>
    <h3>Mounted (Lifecycle)</h3>
    <p>
        Sirve para ejecutar una función cuando el componente se monta en el DOM. En este caso, la función <code>mounted</code> se ejecuta cuando el componente se monta en el DOM. 
    </p>
    <p class="text-center">
        <code>mounted() { console.log('Componente montado') }</code>
    </p>
    <h3>Emits</h3>
    <p>
        Sirve para emitir un evento desde el componente hijo al componente padre. En este caso, el componente hijo emite el evento <code>reverse-message</code> cuando el usuario hace click en el botón. Puedes usar <code>emits</code> para emitir un evento desde el componente hijo al componente padre.
    </p>
    <p class="text-center">
        <code>computed: { reversedMessage() { return this.message.split('').reverse().join('') } }</code>
    </p>

    <h3>Watchers</h3>
    <p>
        Sirve para ejecutar una función cuando una propiedad del componente cambia. En este caso, la función <code>watch</code> se ejecuta cuando la propiedad <code>message</code> cambia. Puedes usar <code>watch</code> para ejecutar una función cuando una propiedad del componente cambia.
    </p>
    <p class="text-center">
        <code>watch: { message() { console.log('Propiedad message cambiada') } }</code>
    </p>
    <div class="alert alert-info">
    <h4>Diferencia entre Watchers y Computed Properties</h4>
    <p>
        Las <code>computed properties</code> se utilizan para <strong>calcular y devolver un valor</strong> basado en propiedades reactivas. Solo se recalculan cuando las dependencias específicas cambian, y Vue almacena el resultado en caché para mejorar la eficiencia.
    </p>
</div>
    <p>
        Los <code>watchers</code>, en cambio, se utilizan para <strong>ejecutar lógica específica</strong> cuando una propiedad cambia. No devuelven ningún valor y son útiles para tareas asíncronas o efectos secundarios, como llamadas a una API o manipulación de datos.
    </p>
    <h5>Resumen de la Diferencia:</h5>
    <table border="1" cellspacing="0" cellpadding="8" style="width: 100%; text-align: left; border-collapse: collapse;">
        <thead>
            <tr>
                <th>Característica</th>
                <th>Computed Properties</th>
                <th>Watchers</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td><strong>Función principal</strong></td>
                <td>Calcular y devolver un valor.</td>
                <td>Ejecutar lógica específica.</td>
            </tr>
            <tr>
                <td><strong>Devuelve un valor</strong></td>
                <td>Sí</td>
                <td>No</td>
            </tr>
            <tr>
                <td><strong>Uso común</strong></td>
                <td>Transformación de datos.</td>
                <td>Tareas asíncronas o efectos secundarios.</td>
            </tr>
            <tr>
                <td><strong>Eficiencia</strong></td>
                <td>Almacena en caché el resultado.</td>
                <td>No almacena en caché.</td>
            </tr>
        </tbody>
    </table>
    <h5>Ejemplo Básico:</h5>
    <p><strong>Computed Property:</strong></p>
        <code-highlight language="javascript">
            <pre>
computed: {
  fullName() {
    return this.firstName + ' ' + this.lastName;
  }
}
</pre>
</code-highlight>
    <p><strong>Watcher:</strong></p>
    <code-highlight language="javascript">
            <pre>

watch: {
  firstName(newVal, oldVal) {
    console.log(`El nombre ha cambiado de ${oldVal} a ${newVal}`);
  }
}
</pre>
</code-highlight>

    <h3>Methods</h3>
    <p>
        Sirve para definir métodos del componente. En este caso, la función <code>reverseMessage</code> se ejecuta cuando el usuario hace click en el botón. Puedes usar <code>methods</code> para definir métodos del componente.
    </p>
    <p class="text-center">
        <code>methods: { reverseMessage() { this.message = this.message.split('').reverse().join('') } }</code>
    </p>
    <h3>Props</h3>
    <p>
        Sirve para definir propiedades del componente. En este caso, la propiedad <code>message</code> se define en el componente padre y se pasa al componente hijo como una propiedad. Puedes usar <code>props</code> para definir propiedades del componente.
    </p>
    <p class="text-center">
        <code>props: { message: String }</code>
    </p>



            
</template>

<script setup>
import CodeHighlight from "vue-code-highlight/src/CodeHighlight.vue";
import "vue-code-highlight/themes/duotone-sea.css";
import "vue-code-highlight/themes/window.css";
</script>

<style lang="scss" scoped>
h1 {
    text-decoration: underline;
}
h3 {
    margin-top: 20px;
}
</style>
