<template>
  <div>
    this is head
    <button @click="a += 1">A=A+1</button>
    <button @click="b += 1">B=B+1</button>
    <p>A + number = {{addA()}} </p>
    <p>B + number = </p>
  </div>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      a: 0,
      b: 0,
      number: 20,
    };
  },
  watch: {
      // a: function(){
      //   alert("run "+this.a);  
      //   this.b +=1;        
      // },
      // b: function (newValu, oldValu) {
      //       console.log(' giá trị mới: ', newValu, ' giá trị cũ:', oldValu)
      //   },        
  },
  computed:{
    // addA() {
    //   console.log("addA run");
    //   return this.a + this.number;
    // },
    // addB() {
    //   console.log("addB run");
    //   return this.b + this.number;
    // }
  },
  methods: {
    addA() {
      // console.log("addA run");
      this.$emit("runA", "text run")
      return this.a + this.number;

    },
    addB() {
      console.log("addB run");
      return this.b + this.number;
    }
  },
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/* h3 {
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
} */
</style>
