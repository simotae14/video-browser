<template>
    <div>
        <SearchBar v-on:termChange="onTermChange"></SearchBar>
        <VideoList :videos="videos"></VideoList>
    </div>
</template>

<script>
import axios from 'axios';
import SearchBar from './components/SearchBar';
import VideoList from './components/VideoList';

export default {
    name: 'App',
    components: {
        SearchBar,
        VideoList
    },
    data() {
        return {
            videos: []
        }
    },
    methods: {
        onTermChange(searchTerm) {
            axios.get('https://www.googleapis.com/youtube/v3/search', {
                params: {
                    key: process.env.VUE_APP_API_KEY,
                    type: 'video',
                    part: 'snippet',
                    q: searchTerm
                }
            }).then(response => {
                this.videos = response.data.items;
            })
        }
    }
}
</script>
