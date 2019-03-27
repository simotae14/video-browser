<template>
    <div>
        <SearchBar v-on:termChange="onTermChange"></SearchBar>
    </div>
</template>

<script>
import axios from 'axios';
import SearchBar from './components/SearchBar';

export default {
    name: 'App',
    components: {
        SearchBar
    },
    methods: {
        onTermChange(searchTerm) {
            axios.get('https://googleapis.com/youtube/v3/search', {
                params: {
                    key: process.env.API_KEY,
                    type: 'video',
                    part: 'snippet',
                    q: searchTerm
                },
                 crossdomain: true
            }).then(response => console.log(response))
        }
    }
}
</script>
