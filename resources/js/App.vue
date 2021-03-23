<template>
    <ais-instant-search :search-client="searchClient" index-name="users">
        <ais-search-box />
        <ais-hits>
            <div slot="item" slot-scope="{ item }">
                <h2>{{ item.name }}</h2>
            </div>
        </ais-hits>
    </ais-instant-search>
</template>

<script>
import "instantsearch.css/themes/algolia-min.css";
import { instantMeiliSearch } from '@meilisearch/instant-meilisearch';

export default {
    data() {
        return {
            searchClient: instantMeiliSearch(
                "http://localhost:7702/"
            ),
        };
    },
};
</script>

<style>
body {
    font-family: sans-serif;
    padding: 1em;
}
</style>
