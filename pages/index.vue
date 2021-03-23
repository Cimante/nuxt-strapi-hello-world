<template>
  <main>
   <table>
     <tr v-for="(item, idx) in testData" :key="idx">
       <td>{{ item.title }}</td>
       <td>{{ item.qty }}</td>
     </tr>
   </table>
  </main>
</template>

<script>
export default {
  data() {
    return {
      testData: null
    }
  },
  created() {
    fetch("http://localhost:1337/items")
      .then((response) => {
        return response.json()
      })
      .then((data) => {
        this.testData = data
      });
  }
}
</script>