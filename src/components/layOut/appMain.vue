<template>
    <div>
        <keep-alive>
            <router-view :key="key"></router-view>

        </keep-alive>
    </div>

</template>
<script>
export default{
    data() {
        return{

        }
    },
    computed:{
        key(){
            return this.$route.name ? this.$route.name+ +new Date() : this.$route+ +new Date()
        }
    }
}
</script>
<style scoped>
</style>