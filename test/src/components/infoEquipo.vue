<template>
  <div>
      <div v-if="this.team.length>0">
          <h1>Mostrando info del equipo: {{team}}</h1>
          <p>Nombre del equipo: {{this.equipo}}</p>
          <p>Nombre corto del equipo: {{this.nombreCorto}}</p>
          <p>Año de formacion del equipo: {{this.anoFormacion}}</p>
          <p>Deporte del equipo: {{this.deporte}}</p>
          <p>Liga del equipo: {{this.liga}}</p>
      </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
    data(){
        return {
            equipo: '',
            nombreCorto: '',
            anoFormacion: '',
            deporte: '',
            liga: '',
        }
    },
    props:{
        team:{
        type: String,
        required: true,
        }
    },
    methods: {
        async getTeamDetails(){
            return axios.get(`https://www.thesportsdb.com/api/v1/json/1/searchteams.php?t=${this.team}`)
            .then((response) => {
                this.equipo = response.data.teams[0].strTeam;
                this.nombreCorto = response.data.teams[0].strTeamShort;
                this.anoFormacion = response.data.teams[0].intFormedYear;
                this.deporte = response.data.teams[0].strSport;
                this.liga = response.data.teams[0].strLeague;
            })
        }
    },
    watch:{
        team: async function(){
            await this.getTeamDetails();
        }
    }
}
</script>

<style>

</style>