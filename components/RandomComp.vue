<template>
  <div>{{ randomNum }}</div>
</template>
  
<script>
export default {
  name: "RandomComp",
  props: {
    randomNum: Number
  }
};
</script>