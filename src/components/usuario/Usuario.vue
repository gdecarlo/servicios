<template>
  <div>
    <h1>Usuarios</h1>
    <button @click="inicializar">Traer usuarios</button>
    <button @click="saveUsuario">Save usuario</button>
    <button @click="deleteUsuario">Delete usuario</button>
    <!-- <samp>{{ usuarios }}</samp> -->
    <ul>
      <li v-for="usuario in usuarios" :key="usuario.id">
        {{ usuario.id +'-'+ usuario.username }}
      </li>
    </ul>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    
    return {
      usuarios: [],
      url: "https://60b40b584ecdc10017480255.mockapi.io/api/usuarios",
    };
  },
  methods: {
    async inicializar(){
      await this.getUsuarios()
    },
    async getUsuarios() {
      try {
        let response = await axios.get(this.url);
        this.usuarios = response.data;
      } catch (error) {
        console.log(error);
      }
    },
    async saveUsuario(){
      const usuario = {
        username:'Jose'
      }
      let respuesta = await axios.post(this.url,usuario)
      console.log(respuesta)
    },
    async deleteUsuario(){
      let respuesta = await axios.delete(this.url+'/1')
      console.log(respuesta)
    }
  },
};
</script>

<style></style>
