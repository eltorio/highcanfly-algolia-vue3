<template>
  <div
    class="min-w-screen min-h-screen bg-blue-100 flex items-center overflow-hidden relative flex-col"
  >
    <div class="rounded-3xl bg-white shadow-xl mt-10 p-10 flex-col">
      <h1 class="text-6xl text-watermelon-600 text-center">High Can Fly</h1>
      <h3 class="text-xl text-watermelon-300 text-center">search test with</h3>
      <h1 class="text-6xl text-blue-700 text-center">
        search by <i class="fa-brands fa-algolia"></i> algolia
      </h1>
    </div>
    <algolia-search
      applicationId="FBJQ44A01A"
      searchKey="a2a5298ced7dcf728fd1125d97676913"
      filter="type:post"
    />
    <basic-card :msg="`Hello Vue ${app.version} in CodeSandbox!`" />
  </div>
</template>

<script>
import BasicCard from "@/components/BasicCard";
import AlgoliaSearch from "@/components/AlgoliaSearch";

export default {
  name: "App",
  data() {
    return { app }; //eslint-disable-line no-undef
  },
  components: {
    BasicCard,
    AlgoliaSearch,
  },
};
</script>

<style>
</style>
