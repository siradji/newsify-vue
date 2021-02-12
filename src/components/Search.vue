<template>
    <div class="search">
        <div class="search-inner">

        <form>
            <div class="shared-col">
                <p class="text">Popular by?</p>
            <div  class="shared-btn-wrapper">
                <label for='shared' class="btn-orange">
                <input v-model="filterBy" @change="filter" type="radio" id="shared" name="shared" value="emailed">
                Emailed
                </label>
                <label for='shared2' class="btn-white">
                <input v-model="filterBy" @change="filter" type="radio" id="shared2" name="shared" value="shared">
                Shared
                </label>
                <label for='shared3' class="btn-blue">
                <input v-model="filterBy" @change="filter" type="radio" id="shared3" name="shared" value="viewed">
                Viewed
                </label>
            </div>
            </div>
        </form>
    </div>
        </div>
</template>

<script>
export default {
    name: "Search",
    data(){
        return {
            filterBy: ''
        }
    },
    methods: {
        filter() {
            this.$emit('filter', this.filterBy);
        }
    }
}
</script>

<style  scoped>
.search {
    background-color: #1e2023;
    padding: 9px;
    
}

.search-inner {
    max-width: 85%;
    margin: auto;
}
form {
    width:100%;
    display: flex;
    align-items: baseline;
    justify-content: space-between;
}
label {
    display: flex;
    color: #fff;
    outline: none;
    border: none;
    padding: 8px 5px;
    align-items: center;
    cursor: pointer;
    height:auto;

}

label input {
    margin-right: 3px;
}
.btn-orange {
    background-color: #f78968
}

.btn-blue {
    background-color: #4e336fdb;
}

.btn-white {
    background-color: #EF2D56;
    color: #fff;
}

.shared-btn-wrapper {
    display: flex;
}

label {
    flex:1;
}

.shared-col {
    display: flex;
}
.text {
    font-size: 18px;
    color: #000;
    padding: 10px 5px;
    background-color: white;
}
</style>