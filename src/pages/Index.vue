<template>
  <Layout>
    <header class="header">
      <h1 v-html="$page.metaData.siteName" />
      <h2 v-html="$page.metaData.siteDescription" />
    </header>
    <section class="docs">
      <DocList
        v-for="edge in $page.allDoc.edges"
        :key="edge.node.id"
        :doc="edge.node"
      />
    </section>
  </Layout>
</template>

<script>
import DocList from "@/components/DocList";
export default {
  components: {
    DocList
  },
  metaInfo: {
    title: "A simple blog"
  }
};
</script>

<page-query>
query {
  metaData {
    siteName
    siteDescription
  }
  allDoc {
    totalCount
    edges {
      node {
        id
        title
        timeToRead
        description
        date (format: "D MMMM YYYY")
        path
      }
    }

  }
}
</page-query>

<style>
.header {
  font-family: "Stylish";
  font-size: 35px;
  text-align: center;
  line-height: 20px;
  padding: 0.7em;
}

.header h2 {
  font-weight: 200;
  font-size: 35px;
}
</style>
