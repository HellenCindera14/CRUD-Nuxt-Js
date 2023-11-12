<!-- YourComponent.vue -->

<template>
    <div>
      <div class="card container mt-5">
        <div class="card-header">
          <h4>Ships List
            <NuxtLink to="/ships/create" class="btn btn-primary float-end">Add Ships</NuxtLink>
          </h4>
        </div>
        <div class="card-body">
          <table class="table table-striped table-bordered">
            <thead>
              <tr>
                <th>ID</th>
                <th>KAPAL</th>
                <th>ASAL</th>
                <th>TUJUAN</th>
                <th>MUATAN</th>
                <th>Action</th>
              </tr>
            </thead>
            <tbody>
              <!-- Iterasi melalui setiap item di dalam savedShips dan tampilkan di tabel -->
              <tr v-for="(ship, index) in savedShips" :key="index">
                <td>{{ index + 1 }}</td>
                <td>{{ ship.kapal }}</td>
                <td>{{ ship.asal }}</td>
                <td>{{ ship.tujuan }}</td>
                <td>{{ ship.muatan }}</td>
                <td>
                  <!-- Tombol Hapus -->
                  <button @click="deleteShip(index)" class="btn btn-danger" style="margin-right: 10%; margin-left: 9%;">Delete</button>
                  <!-- Tombol Perbarui -->
                  <button @click="editShip(index)" class="btn btn-warning" style="margin-left: 9%;">Edit</button>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
  
      <!-- Modal untuk form edit -->
      <div v-if="isEditModalActive" class="modal-container">
        <div class="modal-content">
          <h2>Edit Ship</h2>
          <!-- Form edit -->
          <form @submit.prevent="updateShip">
<!-- ... -->
<form @submit.prevent="updateShip">
  <div class="form-group">
    <label for="kapal">Kapal</label>
    <input v-model="editedShip.kapal" type="text" class="form-control" id="kapal" placeholder="Nama Kapal">
  </div>
  <div class="form-group">
    <label for="asal">Asal</label>
    <input v-model="editedShip.asal" type="text" class="form-control" id="asal" placeholder="Asal">
  </div>
  <div class="form-group">
    <label for="tujuan">Tujuan</label>
    <input v-model="editedShip.tujuan" type="text" class="form-control" id="tujuan" placeholder="Tujuan">
  </div>
  <div class="form-group">
    <label for="muatan">Muatan</label>
    <input v-model="editedShip.muatan" type="text" class="form-control" id="muatan" placeholder="Muatan">
  </div>
  <button type="submit" class="btn btn-primary">Update</button>
</form>
          </form>
        </div>
      </div>
    </div>
  </template>
  
  <script lang="ts">
  export default {
    name: "YourComponent",
    data() {
      return {
        savedShips: JSON.parse(localStorage.getItem('ships') || '[]') as YourShipType[],
        isEditModalActive: false,
        editingIndex: -1,
        editedShip: {
          kapal: '',
          asal: '',
          tujuan: '',
          muatan: '',
        } as YourShipType,
      };
    },
    methods: {
      deleteShip(index: number) {
        this.savedShips.splice(index, 1);
        this.saveShipsToLocalStorage();
      },
      editShip(index: number) {
        this.isEditModalActive = true;
        this.editingIndex = index;
        this.editedShip = { ...this.savedShips[index] };
      },
      updateShip() {
        if (this.editingIndex !== -1) {
          this.savedShips.splice(this.editingIndex, 1, { ...this.editedShip });
          this.saveShipsToLocalStorage();
          this.isEditModalActive = false;
          this.editingIndex = -1;
          this.editedShip = {
            kapal: '',
            asal: '',
            tujuan: '',
            muatan: '',
          };
        }
      },
      saveShipsToLocalStorage() {
        localStorage.setItem('ships', JSON.stringify(this.savedShips));
      },
    },
  };
  
  interface YourShipType {
    kapal: string;
    asal: string;
    tujuan: string;
    muatan: string;
  }
  </script>
  
  <style scoped>
  .modal-container {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    display: flex;
    align-items: center;
    justify-content: center;
  }
  
  .modal-content {
    background: white;
    padding: 20px;
    border-radius: 10px;
    margin-left: 40%;
    margin-right: 40%;
  }

  .form-group {
  margin-bottom: 15px;
}

label {
  display: block;
  margin-bottom: 5px;
}

input {
  width: 100%;
  padding: 8px;
  box-sizing: border-box;
}
  </style>
  