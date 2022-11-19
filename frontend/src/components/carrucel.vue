<template>
    <v-container fluid>
        <v-theme-provider>
            <v-responsive>
                    <!-- <v-card> -->
                        <v-carousel :show-arrows="false" interval="2000" height="auto">
                            <v-carousel-item
                                src="https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg"
                            >
                            </v-carousel-item>
                            <v-carousel-item
                                src="https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg"
                            >
                            </v-carousel-item>
                            <v-carousel-item
                                src="https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg"
                            >
                            </v-carousel-item>
                        </v-carousel>
                        <template>   <!--FROMULARIO-->
                            <div class="text-center">
                                <v-dialog
                                v-model="dialog"
                                width="900"
                                >
                                <template v-slot:activator="{ on, attrs }">
                                    <v-btn
                                    color="red "
                                    dark
                                    v-bind="attrs"
                                    v-on="on"
                                    >
                                    INICIO
                                    </v-btn>
                                </template>

                                <v-card>
                                    <v-card-title class="text-h5 blue text-center ">
                                    Servicios
                                    </v-card-title>
                                    <v-form v-model="valid"> 
                                    <v-container>
                                    <v-row>
                                        <!-- nombre -->
                                        <v-col 
                                        cols="12"
                                        md="12"
                                        >
                                        <p>Nombre:</p>
                                        <v-text-field
                                            v-model="nombre"
                                            :rules="nameRules"
                                            :counter="30"
                                            label="Nombres"
                                            required
                                        ></v-text-field>
                                        </v-col>
                                        <!-- Apellido Paterno -->
                                        <v-col
                                        cols="12"
                                        md="6"
                                        >
                                        <p>Nombre:</p>
                                        <v-text-field
                                            v-model="apellidoP"
                                            :rules="nameRules"
                                            :counter="30"
                                            label="Apellido Paterno"
                                            required
                                        ></v-text-field>
                                        </v-col>
                                        <!-- Apellido Materno -->
                                        <v-col
                                        cols="12"
                                        md="6"
                                        >
                                        <v-text-field
                                            v-model="apellidoM"
                                            :rules="nameRules"
                                            :counter="30"
                                            label="Apellido Materno "
                                            required
                                        ></v-text-field>
                                        </v-col>
                                        <!-- numero -->
                                        <v-col
                                        cols="4"
                                        md="6">
                                            <v-text-field
                                        v-model="numeroTel"
                                        :rules="phoneRules"
                                        :counter="10"
                                        label="Número de télefono"
                                        required
                                        ></v-text-field>
                                        </v-col>
                                        <!-- correo -->
                                        <v-col
                                        cols="12"
                                        md="6"
                                        >
                                        <v-text-field
                                            v-model="email"
                                            :rules="emailRules"
                                            label="Correo"
                                            required
                                        ></v-text-field>
                                        </v-col>
                                        <!-- folio -->
                                        <v-col
                                        cols="12"
                                        md="5"
                                        
                                        >
                                        <v-text-field
                                            v-model="folio"
                                            :rules="folioRules"
                                            :counter="40"
                                            label="Folio"
                                            required
                                        ></v-text-field> <button
                                        color="black"
                                plain
                                rounded
                                x-large
                                v-bind="attrs"
                                v-on="on"><span class="mdi mdi-comment-question-outline"></span></button>
                                        </v-col> 
                                        <v-col
                                        cols="12"
                                        md="5">
                                        <v-select
                                        v-model="select"
                                        :items="items"
                                        :error-messages="errors"
                                        label="Servicio"
                                        data-vv-name="select"
                                        required></v-select>
                                        </v-col>
                                    </v-row>
                                    </v-container>
                                    <v-btn
                                        class="ma-4"
                                        type="submit"
                                        :disabled="invalid"
                                    >
                                        Enviar
                                    </v-btn>
                                    </v-form>
                                    

                                    <v-divider></v-divider>

                                    <v-card-actions>
                                    <v-spacer></v-spacer>
                                    <v-btn
                                        color="primary"
                                        text
                                        @click="dialog = false"
                                    >
                                        CERRAR
                                    </v-btn>
                                    </v-card-actions>
                                </v-card>
                                </v-dialog>
                            </div>
                        </template>
                    <!-- </v-card> -->
            </v-responsive>
        </v-theme-provider>
    </v-container>
</template>
<script>
    export default {
        name:'caroucelMpal',
        data: () => ({
      valid: false,
      nombre: '',
      apellidoP: '',
      apellidoM: '',
      nameRules: [
      v => !!v || 'Este campo es requerido',
      v => (v && v.length <= 30) || 'Este campo debe de tener menos de 30 caracteristicas',
      ],
      numeroTel: '',
      phoneRules:[
        
      ],


      email: '',
      emailRules: [
      v => !!v || 'Correo es requerido',
      v => /^(([^<>()[\]\\.,;:\s@']+(\.[^<>()\\[\]\\.,;:\s@']+)*)|('.+'))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/.test(v) || 'El correo no existe',
      ],
      select: null,
      items: [
        'Item 1',
        'Item 2',
        'Item 3',
        'Item 4',
      ],

    }),
        created(){
        },
        methods:{
        },
    }
</script>
<style scoped>
   
</style>