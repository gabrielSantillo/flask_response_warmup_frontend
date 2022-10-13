<template>
  <div>
    <input type="text" placeholder="Pokemon name" ref="name" />
    <input type="text" placeholder="Pokemon description" ref="description" />
    <input type="text" placeholder="Pokemon image url" ref="image_url" />
    <button @click="handle_submit">Submit</button>
  </div>
</template>

<script>
import axios from "axios"
export default {
  methods: {
    handle_submit() {
      axios
        .request({
          url: `http://127.0.0.1:5000/api/pokemon`,
          method: `POST`,
          /* data being sent */
          data: {
            name: this.$refs[`name`][`value`],
            description: this.$refs[`description`][`value`],
            image_url: this.$refs[`image_url`][`value`]
            
          },
        })
        .then((response) => {
          response;
        })
        .catch((error) => {
          error;
          alert("Sorry, an error occurred");
        });
    },
  },
};
</script>

<style scoped></style>
