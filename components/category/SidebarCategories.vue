<template>
  <ul v-if="isCorrectChild">
    <li v-for="item in categories" :key="item.id">
      <a>{{ item.name }}</a>
      <Resucrsive
        v-if="recursiveCat(item, categories)"
        :categories="recursiveCat(item, categories)"
        :itemParent="item"
      ></Resucrsive>
    </li>
  </ul>
</template>

<script>
export default {
  name: 'Resucrsive',
  props: {
    categories: {
      type: Array,
      default: () => []
    },
    itemParent: {
      type: [Object, Array],
      default: () => []
    }
  },

  computed: {
    isCorrectChild() {
      let flag = false
      if (this.itemParent.length === 0) return true
      console.log(this.itemParent, this.categories)
      this.categories.forEach((item) => {
        if (this.itemParent.id === item.parentId) flag = true
      })
      return flag
    }
  },

  methods: {
    recursiveCat(itemCurrent, arr) {
      let isChild = false
      const newArr = []
      arr.forEach((itemArr) => {
        if (
          itemArr.id !== itemCurrent.id &&
          itemArr.parentId === itemCurrent.id
        )
          isChild = true
        if (itemArr.id !== itemCurrent.id) newArr.push(itemArr)
      })
      return isChild ? newArr : isChild
    }
  }
}
</script>
