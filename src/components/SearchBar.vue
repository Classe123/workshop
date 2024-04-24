<template>
    <form class="form-inline" @submit.prevent="$emit('searchpalette', palette)">
        <div class="input-group">
            <select class=" form-control mr-sm-2" v-model="palette">
                <option value="">All</option>
                <option value="summer">Summer</option>
                <option value="fire">Fire</option>
            </select>
            <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
        </div>
    </form>

</template>

<script>
export default {
    name: 'SearchBar',
    data() {
        return {
            palette: ''
        }
    }
}
</script>

<style lang="scss" scoped></style>