<template>
  <div id="app">
    Hi {{ fullName }} <br />
    Number of articles: {{ articleCount }} <br />

    <button @click="addArticle">Add Article</button>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      articleCount: 0,
      person: {
        firstName: 'John1',
        lastName: 'Citizen',
      },
    };
  },

  computed: {
    fullName() {
      return `${this.person.firstName} ${this.person.lastName}`;
    },
  },

  methods: {
    addArticle() {
      this.articleCount++;
    },
  },

  watch: {
    articleCount(newArticleCount, oldArticleCount) {
      if (newArticleCount !== oldArticleCount) {
        console.log('New article added');
      }
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
