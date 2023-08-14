<template>
  <div>
    <ul>
      <li v-for="(item, idx) in items" :key="idx">
        {{ item.name }} - {{ item.price }}
      </li>
    </ul>
    <button @click="addAndUpdate">Add and update</button>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      items: [
        { name: "Alph", price: 1 },
        { name: "Beta", price: 2 },
      ],
    };
  },

  methods: {
    addAndUpdate() {
      const newItem = { name: "New", price: "-" };
      this.items.push(newItem);
      console.log(this.items);

      setTimeout(() => {
        newItem.price = "over 9000";
      }, 3000);
    },
  },
};
</script>
