<template>
    <q-layout view="hHh lpR fFf" class="bg-grey-1">
      <q-header elevated class="bg-white text-grey-8 q-py-xs" height-hint="58">
        <q-toolbar>
          <q-btn
            flat
            dense
            round
            @click="toggleLeftDrawer"
            aria-label="Menu"
            icon="menu"
          />
  
          <q-btn flat no-caps no-wrap class="q-ml-xs" v-if="$q.screen.gt.xs">
            <q-icon name="ti-heart" color="red" size="28px" />
            <q-toolbar-title shrink class="text-weight-bold">
              Clothes 4You
            </q-toolbar-title>
          </q-btn>
  
          <q-space />
  
          <div class="YL__toolbar-input-container row no-wrap">
            <q-input dense outlined square v-model="search" placeholder="Buscar Producto" class="bg-white col" />
            <q-btn  color="grey-3" text-color="red" icon="search" unelevated />
          </div>
  
          <q-space />
  
          <div class="q-gutter-sm row items-center no-wrap">
            
            <q-btn round dense flat color="grey-8" icon="apps" v-if="$q.screen.gt.sm">
              <q-tooltip>Catalogos</q-tooltip>
            </q-btn>
            <q-btn round dense flat color="grey-8" icon="message" v-if="$q.screen.gt.sm">
              <q-tooltip>Mensajes</q-tooltip>
            </q-btn>
            <q-btn round dense flat color="grey-8" icon="shopping_cart">
              <q-badge color="red" text-color="white" floating>
                2
              </q-badge>
              <q-tooltip>Carrito de Compras</q-tooltip>
            </q-btn>
            <q-btn round flat>
              <q-avatar size="26px">
                <img src="https://cdn.quasar.dev/img/avatar.png">
              </q-avatar>
              <q-tooltip>Mi cuenta</q-tooltip>
            </q-btn>
          </div>
        </q-toolbar>
      </q-header>
  
      <q-drawer
        v-model="leftDrawerOpen"
        show-if-above
        bordered
        class="bg-grey-2"
        :width="240"
      >
        <q-scroll-area class="fit">
          <q-list padding>
            <q-item v-for="link in links1" :key="link.text" v-ripple clickable>
              <q-item-section avatar>
                <q-icon color="grey" :name="link.icon" />
              </q-item-section>
              <q-item-section>
                <q-item-label>{{ link.text }}</q-item-label>
              </q-item-section>
            </q-item>
  
            <q-separator class="q-my-md" />
  
            <q-item v-for="link in links2" :key="link.text" v-ripple clickable>
              <q-item-section avatar>
                <q-icon color="grey" :name="link.icon" />
              </q-item-section>
              <q-item-section>
                <q-item-label>{{ link.text }}</q-item-label>
              </q-item-section>
            </q-item>
  
            <q-separator class="q-mt-md q-mb-xs" />
          
          </q-list>
        </q-scroll-area>
      </q-drawer>
  
      <q-page-container class="q-ma-md" style="height: 80vh;">
    <div class="q-pa-md" style="max-width: 80%; margin: 0 auto;">
      <q-carousel
        v-model="slide"
        transition-prev="slide-right"
        transition-next="slide-left"
        swipeable
        animated
        control-color="red"
        navigation
        padding
        arrows
        height="100%"
        class="bg-white-9 shadow-3 rounded-borders"
      >
        <q-carousel-slide :name="1" class="column no-wrap">
          <div class="row justify-center items-center q-gutter-xs q-col-gutter no-wrap">
            <q-card class="col-4 full-height">
              <q-img class="rounded-borders col-4 full-height" src="../../img_products/1-p.jpg" />
              <q-card-section class="text-center">
                <q-card-text>
                    <q-text tag="h4">
                      MANGO DRESS
                      <br>
                      $ 250.00
                    </q-text>
                    
                </q-card-text>
              </q-card-section>
            </q-card>

            <q-card class="col-4 full-height">
              <q-img class="rounded-borders col-4 full-height" src="../../img_products/3-p.jpg" />
              <q-card-section class="text-center">
                <q-card-text>
                  <q-text tag="h4">
                      MANGO DRESS
                      <br>
                      $ 129.00
                    </q-text>
                </q-card-text>
              </q-card-section>
            </q-card>

            <q-card class="col-4 full-height">
              <q-img class="rounded-borders col-4 full-height" src="../../img_products/2-p.jpg" />
              <q-card-section class="text-center">
                <q-card-text>
                  <q-text tag="h4">
                      MANGO DRESS
                      <br>
                      $ 144.00
                    </q-text>
                </q-card-text>
              </q-card-section>
            </q-card>
          </div>
        </q-carousel-slide>

        <q-carousel-slide :name="2" class="column no-wrap">
          <div class="row justify-center items-center q-gutter-xs q-col-gutter no-wrap">
            <q-card class="col-4 full-height">
              <q-img class="rounded-borders col-4 full-height" src="../../img_products/5.jpg" />
              <q-card-section class="text-center">
                <q-card-text>
                  <q-text tag="h4">
                      MANGO ONLY
                      <br>
                      $ 490.00
                    </q-text>
                </q-card-text>
              </q-card-section>
            </q-card>

            <q-card class="col-4 full-height">
              <q-img class="rounded-borders col-4 full-height" src="../../img_products/6.jpg" />
              <q-card-section class="text-center">
                <q-card-text>
                  <q-text tag="h4">
                      MANGO JACKET
                      <br>
                      $ 890.00
                    </q-text>
                </q-card-text>
              </q-card-section>
            </q-card>

            <q-card class="col-4 full-height">
              <q-img class="rounded-borders col-4 full-height" src="../../img_products/5.jpg" />
              <q-card-section class="text-center">
                <q-card-text>
                  <q-text tag="h4">
                      MANGO BUTTON
                      <br>
                      $ 380.00
                    </q-text>
                </q-card-text>
              </q-card-section>
            </q-card>
          </div>
        </q-carousel-slide>
      </q-carousel>
    </div>
  </q-page-container>
    </q-layout>
  </template>
  <script>
  import { ref } from 'vue'
  import { fabYoutube } from '@quasar/extras/fontawesome-v6'
  
  export default {
    name: 'MyLayout',
  
    setup () {

     
      const slide = ref(1) 
      const leftDrawerOpen = ref(false)
      const search = ref('')
        
      function toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
  
      return {
        fabYoutube,
        slide,
        leftDrawerOpen,
        search,
  
        toggleLeftDrawer,
  
        links1: [
          { icon: 'home', text: 'Inicio' },
          { icon: 'whatshot', text: 'Tendencias 2024' },
          { icon: 'subscriptions', text: 'Mis Suscripciones' }
        ],
        links2: [
          { icon: 'apps', text: 'Catálogos' },
          { icon: 'restore', text: 'Historial de Compras' },
          { icon: 'ti-user', text: 'Mi Cuenta' },
          { icon: 'thumb_up_alt', text: 'Mis Favoritos' },
          { icon: 'ti-control-record', text: 'Salir' }
          
        ]
      }
    }
  }
  </script>