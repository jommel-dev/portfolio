<template>
  <div class="q-pa-md" style="width: 100%;">
    <q-carousel
      arrows
      infinite
      animated
      v-model="slide"
      height="400px"
    >
      <q-carousel-slide name="first" img-src="https://cdn.quasar.dev/img/mountains.jpg">
        <div class="absolute-bottom custom-caption">
          <div class="text-h2">First stop</div>
          <div class="text-subtitle1">Mountains</div>
        </div>
      </q-carousel-slide>
      <q-carousel-slide name="second" img-src="https://cdn.quasar.dev/img/parallax1.jpg">
        <div class="absolute-bottom custom-caption">
          <div class="text-h2">Second stop</div>
          <div class="text-subtitle1">Famous City</div>
        </div>
      </q-carousel-slide>
      <q-carousel-slide name="third" img-src="https://cdn.quasar.dev/img/parallax2.jpg">
        <div class="absolute-bottom custom-caption">
          <div class="text-h2">Third stop</div>
          <div class="text-subtitle1">Famous Bridge</div>
        </div>
      </q-carousel-slide>
    </q-carousel>
    <div class="row q-mt-md">
      <div class="col-12 q-mb-sm">
        <span class="text-h5 text-bold">My Team</span>
      </div>

      <div v-for="(item, indx) in projects" :key="indx" class="col-12 col-sm-6 col-md-4 col-xl-3 q-pa-sm">
        <q-card class="my-card" flat bordered>
          <q-img :src="item.profile" style="height: 250px;" />

          <q-card-section>
            <q-btn
              fab
              color="primary"
              icon="alternate_email"
              class="absolute"
              style="top: 0; right: 12px; transform: translateY(-50%);"
            />

            <div class="row no-wrap items-center">
              <div class="col text-h6 ellipsis">
                <a class="text-green cursor-pointer">{{ item.name }}</a>
                <q-tooltip class="custom-tooltip">
                  {{ item.name }}
                </q-tooltip>
              </div>
              <div class="col-auto text-grey text-caption q-pt-md row no-wrap items-center">
                <q-icon name="place" />
                {{ item.abbr }}
              </div>
            </div>

            <!-- <q-rating v-model="item.rating" color="primary" :max="5" size="18px" /> -->
          </q-card-section>

          <q-card-section class="q-pt-none">
            <div class="text-subtitle1">
              <q-icon name="alternate_email" size="xs" />
              <q-chip outline size="md" color="primary" text-color="white">
                {{ item.email }}
              </q-chip>
            </div>
            <div class="text-subtitle1">
              <q-icon name="call" size="xs" />
              <q-chip outline size="md" color="primary" text-color="white">
                {{ item.contact || 'No Contact' }}
              </q-chip>
            </div>
            <table style="width: 100%;">
              <tr>
                <td style="width: 15%;">Skills:</td>
                <td>
                  coming soon!
                  <!-- <q-chip v-for="(dev) in item.ui" :key="dev" size="sm" color="primary" text-color="white">
                    {{ dev }}
                  </q-chip> -->
                </td>
              </tr>
            </table>
            <div class="text-subtitle1">
              <span class="text-sm"></span>

            </div>
            <div class="text-subtitle1">
              <span class="text-sm"></span>

            </div>

          </q-card-section>

          <q-separator />

          <!-- <q-card-actions>
            <q-btn flat round icon="event" />
            <q-btn flat color="primary">

            </q-btn>
          </q-card-actions> -->
        </q-card>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data(){
    return {
      slide: "first",
      showService: false,
      serviceDetails: {},
      projects: [
        {
          profile: '/portfolio/images/adrian.jpg',
          name: 'Adrian Guillermo',
          contact: '09260696155',
          email: 'adrianguillermo@gmail.com',
          position: 'Senior Sofware Engineer'
        },
        {
          profile: '/portfolio/images/gerald.jpg',
          name: 'Gerald Hope Ecaruan',
          contact: '',
          email: 'ghemzler.dev@gmail.com',
          position: 'Wordpress Developer'
        },
        {
          profile: '/portfolio/images/louie.jpg',
          name: 'Ernest Alferez',
          contact: '',
          email: 'louieflores16@gmail.com',
          position: 'Digital Marketing'
        },
        {
          profile: '/portfolio/images/ronald.png',
          name: 'Ronald Fernando',
          contact: '',
          email: 'ronaldfernando.dev@gmail.com',
          position: 'Shopify Developer'
        },
      ]
    }
  },
  methods:{
    showServiceDesc(item){
      this.showService = true;
      this.serviceDetails = item
    }
  }
}
</script>
<style lang="sass" scoped>
.custom-caption
  text-align: left
  padding: 12px
  color: white
  background-color: rgba(0, 0, 0, .3)

.custom-tooltip
  background: #1976d2;
  color: #fff;
  font-weight: bold;
  font-size: 1rem;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.15);
  padding: 8px 16px;
  letter-spacing: 0.5px;

</style>
