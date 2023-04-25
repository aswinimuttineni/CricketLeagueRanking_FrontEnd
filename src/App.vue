<script >
import Navbar from './components/Navbar.vue';
import TeamsList from './components/TeamsList.vue'
    export default {
        data(){
            return {
                allTeams: []
            }
        },
        components: { TeamsList, Navbar },
        methods: {
            async fetchAllTeamsData() {
                const response = await fetch('https://cricket-ranking-league.netlify.app/.netlify/functions/api');
                return await response.json();
            }
        },
        mounted() {
            this.fetchAllTeamsData().then(res => {
                console.log('res ====>', res)
                if(res){
                    this.allTeams = res.data;
                }
                
            })
        }
    }
</script>

<template>
    <div class="container">
        <Navbar />
        <TeamsList :teamsList="this.allTeams" />
    </div>
</template>

<style >
    .container {
        display: flex;
        flex-direction: column;
    }
</style>
