<template>
<div>
    <b-form @submit="onSubmit" @reset="onReset" v-if="show">

    <b-form-group id="input-group-2" label="Summoner Name:" label-for="input-2">
        <b-form-input
            id="input-2"
            v-model="form.name"
            placeholder="Enter Summoner Name"
            required
        ></b-form-input>
        <Card :info=info></Card>
    </b-form-group>

    <b-button type="submit" variant="primary">Submit</b-button>
    <b-button type="reset" variant="danger">Reset</b-button>
    </b-form>
</div>
</template>

<script>
import axios from "axios";
import Card from "./Card.vue";

export default {
    data() {
        return {
            form: {
                name: "",
            },
            show: true,
            info: {}
        };
    },
    methods: {
        onSubmit(event) {
            event.preventDefault();
            const url = `http://localhost:3001/summoner/${this.form.name}`;
            axios
                .get(url)
                .then(response => {
                this.info = response.data;
                this.info.summonerName = this.form.name
            })
                .catch(error => {
                console.log(error);
                this.errored = true;
            })
                .finally(() => this.loading = false);
        },
        onReset(event) {
            event.preventDefault();
            // Reset our form values
            this.form.name = "";
            // Trick to reset/clear native browser form validation state
            this.show = false;
            this.$nextTick(() => {
                this.show = true;
            });
        }
    },
    components: { Card }
}
</script>