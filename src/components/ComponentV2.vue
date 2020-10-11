<template>
  <h2>This is the Vue 2 style implementation</h2>
  <div>
      <ul v-if="items.length > 0">
          <li v-for="(item, index) in items" :key="index">{{item.value}}</li>
      </ul>
      <form @submit.prevent="addItem">
        <input type="text" v-model="newitem" placeholder="Add new item" />
        <button type="submit">Add Item</button>
      </form>
  </div>

</template>

<script>
export default {
    name: 'ComponentV2',
    data() {
        return {
            newitem: '',
            items: [
                
            ]
        }
    },
    methods: {
        addItem() {
            this.items.push({value: this.newitem});
            this.newitem = '';
        }
    }
}
</script>

<style scoped>

div {
    padding: 50px;
}
form {
    margin-top: 20px;
}
form button {
    margin-left: 30px;
}
</style>