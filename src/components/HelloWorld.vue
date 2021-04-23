<template> 
    <div>
        <div>
            THis is the home page
        </div>
        <div>
          <button @click="loadAPI()">Load</button>
            {{ user }}
        </div>
    </div> 
</template>

<script>

export default {
    async setup(){

      function wait(ms, value) {
          return new Promise(resolve => setTimeout(resolve, ms, value));
      }

      const user = await fetch('https://api.publicapis.org/entries')
          .then(response =>response.json()); 

        return{
            user
        }
    }

}
</script>

<style>

</style>