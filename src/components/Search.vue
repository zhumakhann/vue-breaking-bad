<template>
     <section class="search">
            <form>
                <input 
                    type="text"
                    class="form-control"
                    placeholder="Search characters"
                    autoFocus
                    v-model.trim="title"
                    v-on:input="changeHandler"
                />
            </form>
        </section>
</template>

<script>
export default {
    name: 'Search',
    data(){
        return{
            title: ''
        }
    },
    methods: {
        changeHandler(){
            console.log(this.title);
            this.$emit('search', this.title)
        }
    }
}
</script>