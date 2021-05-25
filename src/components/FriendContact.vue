<template>
  <li>
    <h2>{{ name }} {{localIsFavrt ? '(👍)' : '(👎)' }}</h2>
    <button @click="toggleDetails">{{ detailsAreVisible ? 'Hide' : 'Show' }} Details</button> 
    <button @click="toggleFavrt">{{ localIsFavrt ? 'Dislike👎' : 'Like👍' }} </button>
    <ul v-if="detailsAreVisible">
      <li>
        <strong>Phone:</strong>
        {{ phoneNumber }}
      </li>
      <li>
        <strong>Email:</strong>
        {{ emailAddress }}
      </li>
    </ul>
  </li>
</template>

<script>
export default {
  //use this or : props : simple

  // props:[
  //   'name',
  //   'phoneNumber',
  //   'emailAddress'
  // ],

  //like this : props as validator
  props:{
    name:{
      type:String,
      required:true,
      default:"Arjun Sachin Tendulkar"
    },
    phoneNumber:String,
    emailAddress:String,
    isFavrt:Boolean
  }, 
  data() {
    return {
      detailsAreVisible: false,
      localIsFavrt: this.isFavrt
      // friend: {
      //   id: "manuel",
      //   name: "Manuel Lorenz",
      //   phone: "0123 45678 90",
      //   email: "manuel@localhost.com",
      // },
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFavrt(){
      this.localIsFavrt= !this.localIsFavrt
    }
  }
};
</script>

<style scoped>
button{
  margin: .5rem;
}
</style>