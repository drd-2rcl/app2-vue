<template>
  <div class="component">
    <h1>The User Component</h1>
    <p>I'm an awesome User!</p>
    <button @click="changeName">Change my Name</button>
    <p>Name is {{ name }} </p>
    <p>Age is {{ age }} </p>
    <hr>
    <div class="row">
      <div class="col-xs-12 col-sm-6">
        <app-user-detail 
          :myName="name" 
          @nameWasReset="name=$event" 
          :resetFn="resetName"
          :userAge="age"
        >
        </app-user-detail>
      </div>
      <div class="col-xs-12 col-sm-6">
        <app-user-edit 
          :userAge="age"
          @ageWasEdited="age=$event"
        >
        </app-user-edit>
      </div>
    </div>
  </div>
</template>

<script>
import UserDetail from './UserDetail.vue';
import UserEdit from './UserEdit.vue';

export default {
  data() {
    return {
      name: 'Diogo',
      age: 26
    };
  },
  methods: {
    changeName() {
      this.name = 'Judite';
    },
    resetName() {
      this.name = 'Diogo';
    }
  },
  components: {
    appUserDetail: UserDetail,
    appUserEdit: UserEdit
  }
}
</script>

<style>
div {
  background-color: lightblue;
}
</style>