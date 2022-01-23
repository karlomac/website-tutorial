<template>
    <div>
        <div v-if="page == 1">
            <h1>This is a Store</h1>
            <pos-a-topimage 
                :imagelist="topimages"
                @showDetails="showDetails"
            />

            <v-row>
                <v-col cols=12>
                    <v-card
                        class="mx-2"
                        hover
                        @click="showDetails({arr: 'main', idx: 3})"
                    >
                        <v-card-title>{{images[3].title}}</v-card-title>
                        <v-img
                            v-bind:src="images[3].source"
                        >
                        </v-img>
                    </v-card>
                </v-col>
            </v-row>

            <pos-a-bottomimage 
                :imagelist="bottomimages"
                @showDetails="showDetails"
            />
        </div>

        <pos-m-storedetails  
            @backBtn="backButton"
            :detailContent="content"
            v-if="page == 2"
        />

    </div>
</template>

<script>
export default {
    data() {
        return {
            page: 1,
            images: [
                {source: '/images/titanfall01.jpeg'}, // 0
                {source: '/images/titanfall01.jpeg'}, // 1
                {source: '/images/titanfall01.jpeg'}, // 2
                {source: '/images/titanfall04.jpg', title: 'Titan Fall | 3'},  // 3
                {source: '/images/titanfall03.jpg'}, // 4
                {source: '/images/titanfall04.jpg'},  // 5
                {source: '/images/titanfall03.jpg'},  // 6
            ],
            topimages: [
                {
                    source: '/images/titanfall03.jpg', 
                    height: '300',
                    title: 'Titanfall - detailed review',
                    story: 'this is about the newest titan fall information --- etc etc'  
                }, //0
                {
                    source: '/images/titanfall04.jpg', 
                    height: '300',
                    title: 'Another review of titanfall 2',
                    story: 'this is a second review for titan fall story'
                },   //1
                {
                    source: '/images/titanfall01.jpeg', 
                    height: '300',
                    story: 'this is a third review without a title'
                },  //2 
            ],
            bottomimages: [
                {
                    source: '/images/titanfall03.jpg', 
                    height: '300',
                    title: 'Titanfall - bottom image review',
                    story: 'this is about the newest titan fall information --- etc etc'  
                }, //0
                {
                    source: '/images/titanfall04.jpg', 
                    height: '300',
                    title: 'Another bottom review of titanfall 2',
                    story: 'this is a second review for titan fall story'
                },   //1
                {
                    source: '/images/titanfall01.jpeg', 
                    height: '300',
                    title: 'bottom image review - ',
                    story: 'this is a third review without a title'
                },  //2 
            ],


            customer: [
                {
                    name: 'karlo',
                    address: '414 Citrine',
                    phone: '09279093433',
                    email: 'karlo@lithiumteck.com',
                },
                {
                    name: 'basti',
                    address: '414 Citrine',
                    phone: '09279093423',
                    email: 'slayer@lithiumteck.com',
                },
                {
                    name: 'enzo',
                    address: '414 Citrine',
                    phone: '09279092433',
                    email: 'velum.prismic@lithiumteck.com',
                },
            ]
        }
    },

    mount() {
        console.log(' what is the image -', images[3])
    },

    methods: {
        showMessage() {
            alert('this is a message');
        },

        showDetails(obj) {
            // this method will show the detail of the clicked photo
            console.log('what value was passed - ', obj)
            if(obj.arr == 'main'){
                this.content = this.images[obj.idx]
            }else if(obj.arr == 'top'){
                this.content = this.topimages[obj.idx]
            }else if(obj.arr == 'bottom'){
                this.content = this.bottomimages[obj.idx]
            }else {
                this.content = {
                    title: 'No details found',
                    story: 'please contact support - we did not find the details of this article'
                }
            }
            this.page = 2;
        },

        backButton() {
            // this will switch to the main page
            this.page = 1;
        }
    },
}
</script>