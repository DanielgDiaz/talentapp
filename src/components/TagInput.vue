<template>
  <label>Skills</label>
  <div class="tag-input">
    <div v-for="(tag, index) in tags" :key="tag" class="tag-input__tag">
      <span @click="removeTag(index)">x</span>
      {{ tag }}
    </div>
    <input
      v-model="skill"
      type="text"
      placeholder="Press intro to enter a skill"
      class="tag-input__text"
      @keydown="addTag"
    />
  </div>
</template>
<script>
export default {
  data() {
    return {
      tags: [],
    };
  },
  methods: {
    addTag(event) {
      if (event.code == "Comma" || event.code == "Enter") {
        event.preventDefault();
        let val = event.target.value.trim();

        if (val.length > 0) {
          this.tags.push(val);
          event.target.value = "";
        }
      }
    },
    removeTag(index) {
      this.tags.splice(index, 1);
    },
  },
};
</script>
<style scoped>
.tag-input__tag {
  height: 30px;
  float: left;
  margin-right: 10px;
  background-color: #eee;
  margin-top: 10px;
  line-height: 30px;
  padding: 0 5px;
  border-radius: 5px;
}

.tag-input__tag > span {
  cursor: pointer;
  opacity: 0.75;
}
</style>
