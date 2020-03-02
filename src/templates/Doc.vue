<template>
  <Layout>
    <br />
    <g-link to="/" class="link"> &larr; Go Back</g-link>
    <div class="doc-title">
      <h1>{{ $page.doc.title }}</h1>
      <p class="doc-date">
        {{ $page.doc.date }} | {{ $page.doc.timeToRead }} min read
      </p>
    </div>
    <div class="doc-content">
      <p v-html="$page.doc.content" />
    </div>
  </Layout>
</template>

<page-query>
query Doc ($path: String!) {
   doc: doc (path: $path) {
    id
    title
    content
    date (format: "D MMMM YYYY")
    timeToRead
  }
}
</page-query>

<style>
.doc-title {
  text-align: center;
  font-size: 30px;
  line-height: 10px;
  padding: 2em 0;
  font-family: "Stylish";
}

.doc-date {
  font-size: 16px;
  font-weight: 400;
}

.doc-content {
  font-size: 20px;
}
</style>
