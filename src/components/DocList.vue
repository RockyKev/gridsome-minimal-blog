<template>
  <div class="doc-list">
    <hr class="line" />
    <p class="date" v-html="doc.date" />
    <h3 class="title" v-html="doc.title" />
    <p class="description" v-html="doc.description" />
    <b>{{ doc.timeToRead }} min read</b> &nbsp;
    <g-link :to="doc.path" class="read"
      >Read More
      <span class="visuallyhidden">about {{ doc.title }}</span></g-link
    >
  </div>
</template>

<script>
export default {
  props: ["doc"]
};
</script>

<style>
.line {
  border: 0.5px solid #cdc8c5;
  margin: 30px 0;
}

.date {
  font-weight: 300;
}

.read {
  padding: 7px;
  color: #333;
  text-decoration: none;
  border: 2px dashed #fecd43;
}

.visuallyhidden {
  position: absolute !important;
  width: 1px;
  height: 1px;
  padding: 0;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  clip-path: inset(50%);
  border: 0;
}
.visuallyhidden:focus {
  display: inline-block;
  padding: 15px 23px 14px;
  width: auto;
  height: auto;
  clip: auto;
  color: #000000;
  background-color: #ffffff;
  clip-path: unset;
}
</style>
