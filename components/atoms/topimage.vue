<template>
    <div>
        <v-row>
            <v-col 
                cols=12 md=4 xs=12
                v-for="(image, idx) in images" :key="idx"
            >
                <v-card
                    class="mx-2"
                    @click="showDetails(idx)"
                >
                    <v-img
                        :max-height="image.height"
                        :aspect-ratio="16/9"
                        :src="image.source"
                    ></v-img>
                </v-card>                
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
            this.$emit('showDetails', {arr: 'top', idx: idx});
        }

    }
}
</script>