<template>
    <div>
        <h1>this is store details</h1>
        <v-card>
            <v-card-title>
                <v-btn
                    icon
                    @click="backButton"
                    class="mr-2"
                >
                    <v-icon>mdi-arrow-left</v-icon>
                </v-btn>
                {{details.title}}
            </v-card-title>
            <v-card-text>
                <v-img
                    :src="details.source"
                    class="mb-5"
                ></v-img>
                <p>
                    {{details.story}}
                </p>
            </v-card-text>
        </v-card>
    </div>
</template>

<script>
export default {
    props: {
        detailContent: {
            type: Object,
            require: true,
            default: {}
        }
    },
    data() {
        return {
            details: this.detailContent,
        }
    },

    mounted() {

    },

    methods: {
        backButton() {
            this.$emit('backBtn', true);
        }
    }
}
</script>