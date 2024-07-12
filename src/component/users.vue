<script>
import user from './user.vue'
    export default{
        data(){
            return{
                users : [ 
                { summary: "sabero", EmailAdress: "saber@gmail", phonenumber: "23232322", location: "tunis", tags: "important" },
                { summary: "ahmed", EmailAdress: "ahmed@gmail", phonenumber: "23200322", location: "ariana", tags: "customer" },
                { summary: "asma", EmailAdress: "asma@gmail", phonenumber: "28800322", location: "bEJA", tags: "lead" }
                ],
                filtred : false ,
                filtredUsers : [],
                inputV : ''
                
            }
        },
        components : {
            user
        },
        methods : {
            handleFilter(){
                this.filtred = true
                this.filtredUsers = []
                for ( let user of this.users){
                    if ( user.summary.startsWith(this.inputV)){
                        this.filtredUsers.push(user)
                    }
                }
            }
        }
       
    }
</script>
<template>
    <table class="users">
            <tr>
            <th> Summary </th>
            <th> Email_Adress </th>
            <th> phone number </th>
            <th> Location </th>
            <th> Tags </th>
        </tr>
        <template v-for=" user in (filtred ? filtredUsers : users)" :key="user.id">
            <user :user="user" />
        </template>
          
    </table>
<br>

    <input type="text" placeholder="find user " ref="inputV" v-model="inputV" @change="handleFilter">
    
    

</template>

<style>
    .users 
{ 
  text-align: center;
  border : 1px solid black;
  border-collapse: separate;
  border-spacing: 10px;
  margin: 0 auto;
}
</style>