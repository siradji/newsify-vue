<template>
    <header class="header">
        <div class="header-inner">
        <h1 class="site-title"> Newsify </h1>
        <ul class="nav-links">
            <li class="link">Home</li>
            <li class="link">About App</li>
            <li class="link">Contact</li>
        </ul>
        </div>
    </header>
</template>

<script>
export default {
    name: "Header"
}
</script>

<style scoped>
header {
    color: #fff;
    padding: 15px 10px;
    background-color: #0a7a6b;
}
/* .site-title {
    
} */

.header-inner {
    max-width: 80%;
    margin: auto;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
}

.nav-links {

    display: flex;
    list-style: none;

}

.nav-links .link {
    margin: 0 5px;
}

.link {
    cursor: pointer;
    
}


</style>