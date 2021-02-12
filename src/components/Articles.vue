<template>
    <div>
        <div v-for="newsItem in news" v-bind:key="newsItem.id">
            {{newsItem.title}}
        </div>
    </div>
</template>

<script>
export default {
    name: "Articles", 
    props: ['news']
}
</script>

<style scoped>

</style>