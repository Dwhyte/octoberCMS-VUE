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
            <ul>
              <li v-for="user in fakeData" :key="user.id">
                <h5>{{ user.name }}</h5>
              </li>
            </ul>
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
      default: null,
    },
  },
  data() {
    return {
      title: "My first Vue Component",
      message: "Awesome Job Setting up Vue in October!",
      fakeData: null,
    };
  },
  mounted() {
    console.log("Component mounted.");
    this.getFakeJson();
  },
  methods: {
    async getFakeJson() {
      try {
        let res = await axios.get("https://jsonplaceholder.typicode.com/users");
        if (res.data) {
          this.fakeData = res.data;
          console.log(res.data);
        }
      } catch (error) {
        console.log(error);
      }
    },
  },
};
</script>
