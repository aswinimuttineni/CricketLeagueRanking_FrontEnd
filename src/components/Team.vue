<template>
        <!-- <td>{{ team.rank }}</td> -->
        <td>
            <span>{{ team.team_name }}</span>
            <img :src="team.team_image" alt="team_img" class="team_img">
        </td>
        <td>{{ team.matches }}</td>
        <td>{{ team.wins }}</td>
        <td>{{ team.losses }}</td>
        <td>{{ team.points }}</td>
        <td>{{ team.run_rate }}</td>
        <!-- <td>{{ team.recent_form }}</td> -->
</template>

<script>

export default {
    props: {
        team: Object
    }
}

</script>
<style>
.team_img{
    width: 24px;
    height: 24px;
    margin-left: 10px;
}
td{
    color: #202124;
    font-size: 14px;
    line-height: 0;
    height: 40px;
    padding: 20px 15px;
    vertical-align: middle;
}
td:nth-child(1){
    display: flex;
    align-items: center;
}
td:not(:nth-child(1)){
    text-align: center;
}

</style>