<script setup>

defineProps({
    info: Object,
})

</script>

<template>
    <div>
        <b-card
            :title=info.summonerName
            :img-src=info.iconUrl
            img-alt="Image"
            img-top
            tag="article"
            style="max-width: 15rem;"
            class="mb-2"
        >
            <b-card-text>
                <div class="summonerLevel">{{info.summonerLevel}}</div>
                <div class="tier">{{info.tier}}</div>
                <div class="rank">{{info.rank}}</div>
                <div class="wins">{{info.wins}}</div>
                <div class="losses">{{info.losses}}</div>
                <div class="queueType">{{info.queueType}}</div>
                <div class="winRate">{{info.winRate}}</div>
            </b-card-text>
        </b-card>
    </div>
</template>