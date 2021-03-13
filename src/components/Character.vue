<template>
    <div class='card' v-on:click="clickHandler">
          <div class='card-inner'>
            <div class='card-front'>
              <img v-bind:src="character.img" alt='' />
            </div>
            <div class='card-back'>
              <h1>{{character.name}}</h1>
              <ul>
                <li>
                  <strong>Actor Name:</strong> {{character.portrayed}}
                </li>
                <li>
                  <strong>Nickname:</strong> {{character.nickname}}
                </li>
                <li>
                  <strong>Birthday:</strong> {{character.birthday}}
                </li>
                <li>
                  <strong>Status:</strong> {{character.status}}
                </li>
              </ul>
            </div>
          </div>
        </div>
</template>

<script>



export default {
    name: 'Character',
    props: ['character'],
    methods:{
        clickHandler(){
            this.$emit('popup', this.character)
        }
    }
}
</script>

<style>

</style>