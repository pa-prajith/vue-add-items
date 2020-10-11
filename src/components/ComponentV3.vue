<template>
  <h2>This is the Vue 3 style implementation</h2>
  <div>
      <ul v-if="state.items.length > 0">
          <li v-for="(item, index) in state.items" :key="index">{{item.value}}</li>
      </ul>
      <form @submit.prevent="addItem">
        <input type="text" v-model="state.newitem" placeholder="Add new item" />
        <button type="submit">Add Item</button>
      </form>
  </div>

</template>

<script>
import {reactive} from 'vue';

export default {
    name: 'ComponentV3',
    setup() {
        const state = reactive({
            newitem: '',
            items: [
                
            ]
        });

        const addItem = () => {
            state.items.push({value: state.newitem});
            state.newitem = '';
        }

        return {
            state,
            addItem
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