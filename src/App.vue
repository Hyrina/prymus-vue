<template>
  <div>
    <div>
      <h1>Participants list</h1>
      <ol>
        <li :key="string" v-for="string in osoby">{{string}}</li>
      </ol>
    </div>

    <h3>New participant</h3>
    <form @submit.prevent="addNewParticipant()">
      <label>Firstname</label>
      <input type="text" v-model="imie">
      <label>Lastname</label>
      <input type="text" v-model="nazwisko">
      <button>Add new participant</button>
    </form>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        osoby:[],
        imie:"",
        nazwisko:"",
      };
    },
    methods: {
      addNewParticipant() {
        if(this.imie!=""&&this.nazwisko!="")
        {
        this.osoby.push(this.imie+" "+this.nazwisko);
        this.imie="";
        this.nazwisko="";
        }
      }
    }
  };
</script>