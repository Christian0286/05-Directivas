<template>

  <div>

    <h1>{{ titulo }}</h1>
 
    <hr />
    <h1>v-html</h1>

    <div v-html="html"></div>

    <hr>
    <h1>v-show</h1>
    <h3>Tu edad es: {{edad}}</h3>
    <h2 v-if="edad >= 18 && edad > 0 && edad < 100">Mayor de edad</h2>
    <h2 v-else-if="edad < 18 && edad > 0 && edad < 100">Menor de edad</h2>
    <h2 v-else>Edad invalida</h2>

    <button @click="inc()">Incrementar</button>
    <button @click="disc()">Disminuir</button>

    <hr>
    <h1>v-for</h1>
    <ul>
      <li>{{ usuarios[0] }}</li>
      <li>{{ usuarios[1] }}</li>
      <li>{{ usuarios[2] }}</li>
      <li>{{ usuarios[3] }}</li>
    </ul>
    <ul>
      <li v-for="usuario in usuarios">{{ usuario }}</li>
    </ul>

    <br>

    <ul>
      <li v-for="(usuario, index) in usuarios">{{ index }} - {{ usuario }} </li>
    </ul>

    <br>

    <ul>
      <li v-for="(usuario, index) in usuarios" :key="index">{{ index }}: {{ usuario }} </li>
    </ul>

    <br>

    <ul>
      <li v-for="(valor, clave) in uusuarios" :key="clave">{{ clave }}: {{ valor }} </li>
    </ul>    
    <hr>
    
    <h1> v-on</h1>
  <div @dblclick="click" class="contador"> Clicks: {{clicks}}
  </div>


  </div>

  
  

</template>

<script>
  export default {
    data: () => ({
      titulo: "Hola desde Vue.js 3",
      html: "<h3> Soy un H3 </h3>",
      edad: 0,
      usuarios: ["Melisa", "Fernando", "Raul", "Jose"],
      uusuarios: { nombre: "Yiris"},
      clicks: 0,
      url: "https://cdn.svgporn.com/logos/descript-icon.svg",
    }),
    methods: {
      inc (){
        this.edad++;
      },
      disc(){
        this.edad--;
      },
      click(){
        this.clicks++;
      }
    },
  }
</script>

<style scoped>

  div {
    text-align: center;
    margin: 0px 2rem;
  }
  h2 {
  color: tomato;
  }
 
  .contador{
    background: pink;
    color: snow;
    font-weight: bold;
    height: 400px;
  }


</style>