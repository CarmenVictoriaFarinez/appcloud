
<template>
    <v-card class="container-card">
      <v-card-title class="text-center">Datos usuarios</v-card-title>
        <v-expansion-panels
          v-model="panel"
            :disabled="disabled"
            multiple>
            <v-expansion-panel
              v-for="(user,i) in users"
              :key="i"
            >
              <v-expansion-panel-header>
                {{user.id}}.
                {{user.name}}
              </v-expansion-panel-header>
                <v-expansion-panel-content>
                    <v-icon>mdi-account-circle</v-icon>
                  {{user.email}}
                </v-expansion-panel-content>
            </v-expansion-panel>
        </v-expansion-panels>
      </v-card>
</template>
     

<script>
      import axios from 'axios';

      const REMOTE_WS = axios.create({
        baseURL: 'https://my-user-manager.herokuapp.com/'
      })


      export default {
        data () {   
          return {
            users: [],
          }
        },
        methods:{
          getUsers (){
          REMOTE_WS.get('users/')
            .then(response => {
              this.users = response.data
              //console.log(response.data)
            })
            .catch(err => {
              console.error(err)
            })
        } 
      },
      created(){
        this.getUsers();
      }
}
</script>



