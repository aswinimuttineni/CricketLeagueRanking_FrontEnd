<template>
    <section>
        <h1 class="heading">Team Table</h1>
        <table class="teams-table">
            <tbody>
                <tr class="table-headings">
                    <!-- <th class="team rank">R</th> -->
                    <th class="team team-name">Team</th>
                    <th class="team matches">Mat</th>
                    <th class="team wins">Won</th>
                    <th class="team losses">Lost</th>
                    <th class="team points">Pts</th>
                    <th class="team run-rate">N/R</th>
                    <!-- <th class="team recent-mts">Last 5</th> -->
                </tr>
                <tr v-for="team in teamsList" :key="team.id" >
                    <Team :team="team" />
                </tr>
            </tbody>
        </table>
    </section>
</template>

<script>
import Team from './Team.vue'
export default {
    components: {Team},
    props: {
        teamsList: Array
    }
}

</script>
<style>
.table-headings{
    background-color: #2ea1cd !important;
}
.heading{
    text-align: center;
    padding: 10px 0px;
}
.teams-table{
    border-collapse: separate;
    border-spacing: 0;
    /* width: 80%; */
    padding: 15px;
    margin: auto;
    border-radius: 8px;
    z-index: 9997;
    background-color: #fff;
    white-space: normal;
    overflow: hidden;
    box-shadow: 0px 5px 26px 0px rgba(0,0,0,0.22), 0px 20px 28px 0px rgba(0,0,0,0.3);
}
.team{
    color: #fff;
    font-size: 14px;
    font-weight: bold;
    height: 12px;
    line-height: 12px;
    padding: 15px;
    vertical-align: middle;
}
.team-name{
    /* min-width: 190px; */
    text-align: left;
}
.rank, .matches, .wins, .losses, .run-rate, .points, .recent-mts{
    width: 50px;
    min-width: 50px;
    padding-left: 3px;
    padding-right: 3px;
    text-align: center;
}

.run-rate{
    width: 50px;
    min-width: 50px;
}
.recent-mts{
    width: 100px;
    min-width: 100px;
}
tr:nth-child(odd) {
  background-color: #dce9f9;
}
</style>