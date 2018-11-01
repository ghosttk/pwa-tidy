<template>
  <div class="hello">
    <div v-for="pi in tdata"> {{ pi.place }} 
      <button v-for="item in pi.items"> {{ item }} </button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      tdata: ''
    }
  },
  mounted: function () {
    var mydate = new Date()
    this.tdata = [{place: '01', items: ['01'], dates: [mydate.toLocaleString()], unsaved: [true]}]
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
h1, h2 {
  font-weight: normal;
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
  color: #35495E;
}
</style>
