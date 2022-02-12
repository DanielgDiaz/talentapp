<template>
  <form>
    <label>Email</label>
    <input type="email" required v-model="email" />

    <label>Name</label>
    <input type="name" required v-model="name" />

    <label>Rol:</label>
    <select v-model="rol">
      <option value="Freont Developer">Front Developer</option>
      <option value="Back Developer">Back Developer</option>
      <option value="Mobile Developer">Mobile Developer</option>
      <option value="Data Engineer">Data Engineer</option>
    </select>

    <label>Description</label>
    <input type="text" required v-model="description" />

    <country-input />

    <label>City</label>
    <input type="city" required v-model="city" />
    <tag-input />

    <div class="submit">
      <button>Create user</button>
    </div>
  </form>
  <p>Email: {{ email }}</p>
  <p>name: {{ name }}</p>
  <p>Rol: {{ rol }}</p>
  <p>Description {{ description }}</p>
  <p>Skills: {{ tag }}</p>
  <p>Country: {{ country }}</p>
  <p>City: {{ city }}</p>
</template>

<script>
import CountryInput from "./CountryInput.vue";
import TagInput from "./TagInput.vue";
export default {
  components: { CountryInput, TagInput },
  data() {
    return {
      email: "",
      name: "",
      rol: "",
      description: "",
      tempSkill: "",
      skills: [],
      city: "",
      country: "",
    };
  },
  methods: {
    handleSubmit() {
      // name validation
      {
        console.log("email: ", this.email);
        console.log("name: ", this.name);
        console.log("role: ", this.role);
        console.log("skills: ", this.skills);
        
      }
    },
  },
};
</script>

<style>
form {
  max-width: 420px;
  margin: 30px auto;
  background: white;
  text-align: left;
  padding: 40px;
  border-radius: 10px;
}
label {
  color: #aaa;
  display: inline-block;
  margin: 25px 0 15px;
  font-size: 0.6em;
  text-transform: uppercase;
  letter-spacing: 1px;
  font-weight: bold;
}
input,
select {
  display: block;
  padding: 10px 6px;
  width: 100%;
  box-sizing: border-box;
  border: none;
  border-bottom: 1px solid #ddd;
  color: #555;
}
input[type="checkbox"] {
  display: inline-block;
  width: 16px;
  margin: 0 10px 0 0;
  position: relative;
  top: 2px;
}
.pills {
  display: flex;
  flex-wrap: wrap;
  gap: 5px;
  margin-top: 10px;
}
.pills .pill {
  background: rgba(34, 130, 255, 0.15);
  padding: 5px 10px;
  border-radius: 15px;
  color: rgb(34, 130, 255);
  letter-spacing: 1px;
  display: flex;
  align-items: center;
}
.pills .pill span {
  margin-left: 10px;
  font-size: 20px;
  cursor: pointer;
}
.submit {
  text-align: center;
  margin-top: 20px;
}
.submit button {
  background: rgb(34, 130, 255);
  border: none;
  border-radius: 5px;
  color: white;
  padding: 15px 25px;
  font-size: 18px;
}
.error {
  color: #ff0062;
  margin-top: 10px;
  font-size: 0.8em;
  font-weight: bold;
}
</style>
