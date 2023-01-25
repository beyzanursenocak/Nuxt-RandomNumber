<template>
    <v-container class="container-scoped">
        <v-row justify="center" align="center">
            <v-col cols="12" sm="8" md="6">
                <div id="app" class="d-flex justify-spaced-around">
                    <v-text-field outlined clearable label="Code:" placeholder="Please click the button for the number value." type="text" v-model="randomNumber">
                    </v-text-field>

                    <!-- <button @click="change">Change Number</button> -->

                    <v-btn icon color="info" large @click="change">
                        <v-icon>mdi-cached</v-icon>
                    </v-btn>
                </div>
            </v-col>
        </v-row>
    </v-container>
</template>
  
<script>
import RandomComp from '../components/RandomComp.vue';
export default {
    name: "interger",
    components: {
        RandomComp
    },
    data() {
        return {
            randomNumber: null
        }
    },
    methods: {
        change: function () {
            this.randomNumber = Math.floor(Math.random() * 1000);
        }
    },
};
</script>

<style scoped>
.container-scoped {
    position: absolute;
    bottom: 150px;
}
</style>