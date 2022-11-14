<template>
  <!-- <home-welcome/> -->
  <button @click="toogle">Toogle</button>
 <component :is='MyComponent'/>

 
  <!-- bu şekilde de çağırabiliriz 
    <Counter/>
  <component :is='Counter'/> 
   şeklinde de çağırabiliriz
  -->
  <!--
      iki farklı şekilde de kullanılabliyor,
     <HomeWelcome/>
     <Counter/>
  -->
</template>

<script setup>
  const MyComponent = shallowRef(resolveComponent('Counter'));

  function toogle(){
    console.log(MyComponent.value)
    MyComponent.value = resolveComponent('HomeWelcome');
  }
</script>

<!-- İKİ FARKLI KULLANIMI VAR -->
<!--
<script>
  export default{
    data(){
      return{
        count: 0,
      };
    },
    methods: {
      increment(){
        this.count++;
      },
      decrement(){
        this.count--;
      },
    },  
  };


</script>
-->