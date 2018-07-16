<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      For guide and recipes on how to configure / customize this project,<br>
      check out the
      <a href="https://cli.vuejs.org" target="_blank">vue-cli documentation</a>.
    </p>
    <h3>My Work</h3>
    <ul>
      <li v-for="project in projects" v-bind:key="project.id">
        <a v-bind:href="project.link" target="_blank">{{project.name}}</a>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class HelloWorld extends Vue {
  @Prop() private msg!: string;
  
  public projects: Array<any>;
  
  constructor() {
    super();
    this.projects = [
      { id: 1, name: '650 Stories', link: 'http://650stories.com' },
      { id: 2, name: 'Stevens Connect', link: 'https://stevens-connect.com' },
      { id: 3, name: 'Weather Charts', link: 'http://micahcourey.com/weather-charts/' },
      { id: 4, name: 'Twaddler', link: 'http://micahcourey.com/twaddler/' },
    ];
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
