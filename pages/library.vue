<template>
    <div>
        <h1>Library</h1>
        <pos-a-topimage />
        <v-card
            color="white"
            light
            class="my-3"
        >
            <v-img
                src="https://cdn.vuetifyjs.com/images/parallax/material.jpg"
                height="500"
            >
            </v-img>
            
            <div class="white pa-5">
                <span class="header mx-2">This is my title</span>
                <div class="d-flex justify-space-between align-center">
                    <div >
                       <span class="black--text">This is the proper title </span>

                    </div>
                    <v-btn
                        color="blue"
                        class=""
                    >
                        <span>Home</span>
                    </v-btn>
                </div>

            </div>

            <v-card-text>
                <h2>This is in v-card-text</h2>
            </v-card-text>
       
        </v-card>
        <pos-a-bottomimage />
    </div>
</template>

<style scoped>
.header {
    font-size: 4rem;
    color: black;
    font-weight: bold;
}
</style>