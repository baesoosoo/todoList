<template>
 <div>
          <input type="checkbox" :checked="todo.checked">
          <span class="ml-3">{{ todo.text }}</span>
</div>
</template>

<script>
export default {
  props:{
    todo:{ 
        type: Object,
        require: true
    }
  }
}
</script>

<style>

</style>