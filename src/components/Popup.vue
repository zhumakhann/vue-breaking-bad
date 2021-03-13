<template>
    <div>
        <div class="overflow" v-bind:class="{ active: popup.active }" v-on:click="clickHandler" />
        <div class="popup" v-bind:class="{ active: popup.active }">
            <button class="popup__close" v-on:click="clickHandler">
                X
            </button>
            <div class="popup__content">
                <img v-bind:src="popup.character.img" alt="" class="popup__content-img">
                <div class="popup__content-text">
                    <h3 class="popup__title">
                        {{ popup.character.name }}
                    </h3>
                    <h4 class="popup__subtitle">
                        {{ popup.character.nickname }}
                    </h4>
                    <p v-if="popup.character.birthday">Date of birth: {{ popup.character.birthday.split('-').join(' ') }}</p>

                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Popup',
    props: ['popup'],
    methods: {
        clickHandler(){
            this.$emit('closePopup')
        }
    },
    mounted(){
        // const { name, nickname, img, birthday } = popup.character
    }

}
</script>


