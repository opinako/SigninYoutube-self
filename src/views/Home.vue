<template>
    <v-container>
        <v-row align="center" justify="center">
            <v-col cols="12" md="8">
                <v-card>

                    <v-window v-model="step">
                        <v-window-item :value="1">

                            <v-row>
                                <v-col cols="12" md="8">
                                    <v-card-text>
                                        <h1 class="text-center teal--text text--accent-3 mt-md-12">Sign in to Diprelia</h1>
                                    </v-card-text>
                                    <v-card-actions class="justify-center mr-2">
                                        <v-btn icon outlined color="black">
                                            <v-icon>fab fa-facebook-f</v-icon>
                                        </v-btn>
                                        <v-btn icon outlined color="black">
                                            <v-icon>fab fa-google-plus-g</v-icon>
                                        </v-btn>
                                        <v-btn icon outlined color="black">
                                            <v-icon>fab fa-linkedin-in</v-icon>
                                        </v-btn>
                                    </v-card-actions>

                                    <v-card-text>
                                        <v-text-field label="Email" name="Email" prepend-icon="email" color="teal accent-3"></v-text-field>
                                        <v-text-field label="Password" name="password" prepend-icon="lock" color="teal accent-3"></v-text-field>
                                        <h4 class="text-center">Forget your password ?</h4>
                                    </v-card-text>
                                    <v-card-actions class="justify-center">
                                        <v-btn rounded  color="teal accent-3" dark>Sign in</v-btn>
                                    </v-card-actions>
                                    
                                </v-col>
                                <v-col cols="12" md="4" class="teal accent-3">
                                    <v-card-text class="mt-12 white--text">
                                        <h1 class="text-center">Hello, Friend !</h1>
                                        <h4>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Adipisci dicta corporis, maxime obcaecati hic asperiores iusto, facilis minima distinctio sunt autem, suscipit minus exercitationem enim cumque debitis in beatae sequi!</h4>
                                    </v-card-text>
                                    <v-card-actions class="justify-center">
                                        <v-btn rounded dark outlined @click="step++">Sign in</v-btn>
                                    </v-card-actions>
                                </v-col>
                            </v-row>
                        </v-window-item>

                        <v-window-item :value="2">
                            <v-row>
                                <v-col cols="12" md="4" class="teal accent-3">
                                    <v-card-text class="justify-center white--text">
                                        <h1 class="text-center">Welcome Back !</h1>
                                        <h4>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Fugit nostrum hic quo perspiciatis vel obcaecati. Sed vitae placeat dolor dignissimos facilis, debitis, ea fugit, explicabo provident dolorum animi nesciunt optio.</h4>
                                    </v-card-text>
                                    <v-card-actions class="justify-center">
                                        <v-btn rounded outlined dark @click="step--">Sign in</v-btn>
                                    </v-card-actions>
                                </v-col>
                                <v-col cols="12" md="8">
                                    <v-card-text>
                                        <h1 class="text-center">Create Account</h1>
                                    </v-card-text>
                                    <v-card-actions class="justify-center mr-2">
                                        <v-btn fab outlined>
                                            <v-icon>fab fa-facebook-f</v-icon>
                                        </v-btn>
                                        <v-btn fab outlined>
                                            <v-icon>fab fa-google-plus-g</v-icon>
                                        </v-btn>
                                        <v-btn fab outlined>
                                            <v-icon>fab fa-linkedin-in</v-icon>
                                        </v-btn>
                                    </v-card-actions>

                                    <v-card-text>
                                        <h4 class="text-center">Ensure your email for registrasion</h4>
                                        <v-text-field label="Name" type="text" prepend-icon="person" color="teal accent-3"></v-text-field>
                                        <v-text-field label="Email" type="email" prepend-icon="email" color="teal accent-3"></v-text-field>
                                        <v-text-field label="Password" type="password" prepend-icon="lock" color="teal accent-3"></v-text-field>
                                    </v-card-text>
                                    <v-card-actions class="justify-center">
                                        <v-btn rounded color="teal accent-3" dark>Sign in</v-btn>
                                    </v-card-actions>
                                </v-col>
                            </v-row>
                        </v-window-item>

                        <v-window-item :value="3">
                            <div class="pa-4 text-center">
                                <v-img class="mb-4" contain height="128" src="https://cdn.vuetifyjs.com/images/logos/v.svg"></v-img>
                                <h3 class="title font-weight-light mb-2">Welcome to Vuetify</h3>
                                <span class="caption grey--text">Thanks for signing up!</span>
                            </div>
                        </v-window-item>
                    </v-window>

                    <v-divider></v-divider>

                    <v-card-actions>
                        <v-btn :disabled="step === 1" text @click="step--">
                            Back
                        </v-btn>
                        <v-spacer></v-spacer>
                        <v-btn :disabled="step === 3" color="primary" depressed @click="step++">
                            Next
                        </v-btn>
                    </v-card-actions>
                </v-card>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
    export default {
        data: () => ( {
            step: 1,
        } ),

        computed: {
            currentTitle() {
                switch ( this.step ) {
                    case 1:
                        return 'Sign-up'
                    case 2:
                        return 'Create a password'
                    default:
                        return 'Account created'
                }
            },
        },
    }
</script>