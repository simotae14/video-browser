<template>
    <div>
        <SearchBar v-on:termChange="onTermChange"></SearchBar>
    </div>
</template>

<script>
import SearchBar from './components/SearchBar';
const API_KEY = 'AIzaSyBZD6IONSngNDHcmx6O1IUQNhVzkbevnso';

export default {
    name: 'App',
    components: {
        SearchBar
    },
    methods: {
        onTermChange(searchTerm) {
            console.log(searchTerm);
        }
    }
}
</script>
