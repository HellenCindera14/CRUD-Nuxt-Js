<template>
    <div class="mt-5 container">
      <h1>Create Ships Page</h1>
      <div class="card">
        <div class="card-header">
            <h4>Create Ships
            <NuxtLink to="/ships" class="btn btn-danger float-end">Back</NuxtLink>
        </h4>
        </div>
        <div class="card-body">
            <div v-if="isLoading">
                <Loading :title="isLoadingTitle"/>
            </div>


            <form @submit.prevent="createShips">
                <div class="mb-3">
                    <label for="">Kapal</label>
                    <input type="text" v-model="ships.kapal" class="form-control">
                </div>
                <div class="mb-3">
                    <label for="">Asal</label>
                    <input type="text" v-model="ships.asal" class="form-control">
                </div>
                <div class="mb-3">
                    <label for="">Tujuan</label>
                    <input type="text" v-model="ships.tujuan" class="form-control">
                </div>
                <div class="mb-3">
                    <label for="">Muatan</label>
                    <input type="text" v-model="ships.muatan" class="form-control">
                </div>
                <div class="mb-3">
                 <button type="submit" class="btn btn-primary">Create</button>
                 <NuxtLink to="/ships"></NuxtLink>

                </div>
            </form>


        </div>
      </div>
    </div>
  </template>
  
  <script lang="ts">
  import axios from 'axios';
  
  export default {
    name: "CreateStudent",
    data() {
      return {
        ships: {
          kapal: '',
          asal: '',
          tujuan: '',
          muatan: '',
        },
        isLoading: false,
        isLoadingTitle: 'Loading',
      };
    },
    methods: {
  createShips() {
    this.isLoading = true;

    // Retrieve existing data from local storage or use an empty array if null
    const storedShips = JSON.parse(localStorage.getItem('ships') ?? '[]');
    
    // Push the new ship data into the array
    storedShips.push(this.ships);

    // Save the updated array back to local storage
    localStorage.setItem('ships', JSON.stringify(storedShips));

    // Notify the user that the ship data has been saved
    alert('Ship data has been saved to local storage.');

    // Reset the state and input form
    this.isLoading = false;
    this.ships.kapal = '';
    this.ships.asal = '';
    this.ships.tujuan = '';
    this.ships.muatan = '';
  },
},


  };
  </script>
  