<template>
    <div>
        <v-row>
            <v-col cols=12 md=6>
                <v-card
                    class="mx-2"
                    hover
                    @click="showDetails(0)"
                >
                    <v-img
                        :src="images[0].source"
                    >
                    </v-img>
                </v-card>
            </v-col>
            <v-col cols=12 md=6>
                <v-row>
                    <v-card
                        class="mx-2 my-2"
                        hover
                        @click="showDetails(1)"
                    >
                        <v-img
                            max-height="200"
                            :src="images[1].source"
                        >
                        </v-img>
                    </v-card>                
                </v-row>
                <v-row>
                    <v-card
                        class="mx-2 my-2"
                        hover
                        @click="showDetails(2)"
                    >
                        <v-img
                            max-height="200"
                            :src="images[2].source"
                        >
                        </v-img>
                    </v-card>
                </v-row>
            </v-col>
        </v-row>
    </div>
</template>

<script>
export default {
    props: {
        imagelist: {
            type: Array,
            required: false,
            default: []
        }
    },
    data(){
        return {
            images: this.imagelist
        }
    },

    mounted() {
        console.log('images -==', this.imagelist)
    },

    computed: {
        defaultImages() {
            return [
                {source: '/images/titanfall01.jpeg', height: '300' },
                {source: '/images/titanfall01.jpeg', height: '300' },
                {source: '/images/titanfall01.jpeg', height: '300' },
            ]
        }
    },

    methods: {
        showDetails(idx){
            this.$emit('showDetails', {arr: 'bottom', idx: idx});
        }

    }
}
</script>