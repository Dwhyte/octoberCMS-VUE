<template>
  <div class="container">
    <div class="row justify-content-center">
      <div class="col-md-8">
        <div class="card card-default">
          <div class="card-header">{{ title }}</div>

          <div class="card-body">
            You did it D!
            <p>{{ message }}</p>
            <span class="person">{{ person }}</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    person: {
      type: String,
      default: null
    }
  },
  data() {
    return {
      title: "My first Vue Component",
      message: "Awesome Job Setting up Vue in October!"
    };
  },
  mounted() {
    console.log("Component mounted.");
  }
};
</script>
