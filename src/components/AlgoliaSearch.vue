<template>
  <div class="rounded-3xl bg-white shadow-xl mt-10 p-10">
    <ais-instant-search
      index-name="highcanfly-development-index"
      :search-client="searchClient"
    >
      <ais-search-box placeholder="rechercher…">
        <template v-slot:submit-icon
          ><i class="fa-solid fa-magnifying-glass"></i
        ></template>
        <template v-slot:reset-icon><i class="fa-solid fa-ban"></i></template>
      </ais-search-box>
      <ais-hits :transform-items="transformAlgoliaHits">
        <template v-slot="{ items }">
          <ul>
            <li v-for="item in items" :key="item.objectID">
              <a
                :href="`https://dev.highcanfly-web.pages.dev/sanity-blog/${item.slug}`"
                >{{ item.title }}</a
              >
              <a
                :href="`https://dev.highcanfly-web.pages.dev/sanity-blog/${item.slug}`"
              >
                <p v-html="item._highlightResult.body.value" />
              </a>
            </li>
          </ul>
        </template>
      </ais-hits>
      <ais-powered-by class="flex justify-end" />
    </ais-instant-search>
  </div>
</template>

<script>
import algoliasearch from "algoliasearch/lite";
import {
  AisInstantSearch,
  AisSearchBox,
  AisHits,
  AisPoweredBy,
} from "vue-instantsearch/vue3/es";

export default {
  name: "AlgoliaSearch",
  props: {
    applicationId: String,
    searchKey: String,
    filter: {
      type: [String],
      default: "",
    },
  },
  data() {
    const algoliaClient = algoliasearch(
      this.$props.applicationId,
      this.$props.searchKey
    );
    const filter = this.$props.filter;
    const searchClient = {
      ...algoliaClient,
      search(requests) {
        if (requests.every(({ params }) => !params.query)) {
          return Promise.resolve({
            results: requests.map(() => ({
              hits: [],
              nbHits: 0,
              nbPages: 0,
              page: 0,
              processingTimeMS: 0,
            })),
          });
        }
        requests.forEach((request) => {
          request.params.filters = filter;
        });
        return algoliaClient.search(requests);
      },
    };
    return {
      searchClient: searchClient,
    };
  },
  methods: {
    transformAlgoliaHits(items) {
      return items;
    },
  },
  components: {
    AisInstantSearch,
    AisSearchBox,
    AisHits,
    AisPoweredBy,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
