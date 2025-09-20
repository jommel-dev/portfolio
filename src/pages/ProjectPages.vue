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
        <span class="text-h5 text-bold">Owned/Team Developed Projects</span>
      </div>

      <div v-for="(item, indx) in projects" :key="indx" class="col-12 col-sm-6 col-md-4 col-xl-3 q-pa-sm">
        <q-card class="my-card" flat bordered>
          <q-img :src="item.banner" />

          <q-card-section>
            <q-btn
              fab
              color="primary"
              icon="data_object"
              class="absolute"
              style="top: 0; right: 12px; transform: translateY(-50%);"
            />

            <div class="row no-wrap items-center">
              <div class="col text-h6 ellipsis">
                <a class="text-green cursor-pointer">{{ item.title }}</a>
                <q-tooltip class="custom-tooltip">
                  {{ item.title }}
                </q-tooltip>
              </div>
              <div class="col-auto text-grey text-caption q-pt-md row no-wrap items-center">
                <q-icon name="place" />
                {{ item.abbr }}
              </div>
            </div>

            <q-rating v-model="item.rating" color="primary" :max="5" size="18px" />
          </q-card-section>

          <q-card-section class="q-pt-none">
            <div class="text-caption text-grey ellipsis">
              {{ item.description }}
              <q-tooltip class="custom-tooltip">
                {{ item.description }}
              </q-tooltip>
            </div>
            <div class="text-subtitle1">
              <q-icon name="person" size="xs" />
              <q-chip v-for="(dev) in item.developer" :key="dev" outline size="sm" color="primary" text-color="white">
                {{ dev }}
              </q-chip>
            </div>
            <table style="width: 100%;">
              <tr>
                <td style="width: 35%;">UI/Framework:</td>
                <td>
                  <q-chip v-for="(dev) in item.ui" :key="dev" size="sm" color="primary" text-color="white">
                    {{ dev }}
                  </q-chip>
                </td>
              </tr>
              <tr>
                <td style="width: 35%;">Backend Services:</td>
                <td>
                  <q-chip v-for="(dev) in item.backend" :key="dev" size="sm" color="secondary" text-color="white">
                    {{ dev }}
                  </q-chip>
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
          banner: '/portfolio/images/dashboard.jpg',
          title: "Pawnshop Management Information System",
          abbr: "PSMIS",
          description: "Manages pawnshop operations including customer loans, ticket generation, auction item listing, and transaction report exports.",
          rating: 4.5,
          ui: ["Quasar Framework", "MDC"],
          backend: ["PHP", "CodeIgniter 4"],
          features: [
            "Customer Loan Management",
            "Pawn Ticket Generation",
            "Auction Item Listing",
            "Transaction Report Export",
            "Accounting Report Export",
          ],
          developer: ["Jommel Cabiles"]
        },
        {
          banner: '/portfolio/images/dashboard.jpg',
          title: "Molecular Laboratory Information System",
          abbr: "MLIS",
          description: "Handles molecular lab processes such as recording patient RT-PCR and Antigen results, report printing.",
          rating: 4.5,
          ui: ["Nuxt.js", "Bootstrap", "AntD"],
          backend: ["PHP", "CodeIgniter 4"],
          features: [
            "Dashboard",
            "Patient Record Management",
            "RT-PCR/Antigen Result Logging",
            "Printable Lab Reports",
            "Designed User Workflow",
          ],
          developer: ["Jommel Cabiles", "Erwin Joseph Tantoco"]
        },
        {
          banner: '/portfolio/images/dashboard.jpg',
          title: "Surgical Pathology Consultation Report System",
          abbr: "SPCRIS",
          description: "Extension of MLIS designed for pathology reporting, generating specialized surgical pathology consultation reports.",
          rating: 4.5,
          ui: ["Nuxt.js", "Vuetify Components"],
          backend: ["PHP", "CodeIgniter 4"],
          features: [
            "Specialized pathology reports",
            "Integration with MLIS",
            "Consultation record management"
          ],
          developer: ["Jommel Cabiles", "Erwin Joseph Tantoco"]
        },
        {
          banner: '/portfolio/images/dashboard.jpg',
          title: "Distribution and Sales Inventory System",
          abbr: "DSIS",
          description: "Inventory and sales management platform with mobile app, online/offline syncing, and secure API integration.",
          rating: 4.5,
          ui: ["Quasar Framework (Web + Mobile)"],
          backend: ["PHP CodeIgniter 4", "JWT Auth"],
          features: [
            "Inventory management",
            "Sales order processing",
            "Mobile app with online/offline sync",
            "Secure API with JWT authentication"
          ],
          developer: ["Jommel Cabiles"]
        },
        {
          banner: '/portfolio/images/dashboard.jpg',
          title: "Grammar App (AI-Powered)",
          abbr: "GrammarApp",
          description: "AI-powered application that generates grammar corrections and restructures user content in real-time.",
          rating: 4.5,
          ui: ["Quasar Framework", "TailwindCSS"],
          backend: ["Firebase", "OpenAI API"],
          features: [
            "Grammar correction",
            "Sentence restructuring",
            "Content improvement suggestions",
            "Real-time AI feedback"
          ],
          developer: ["Jommel Cabiles", "Alex Alfon"]
        },
        {
          banner: '/portfolio/images/dashboard.jpg',
          title: "Inventory & Sales Management System (with Barcode Scan)",
          abbr: "ISMS",
          description: "Tracks inventory, sales, and deliveries while generating accounting reports with integrated barcode scanning.",
          rating: 4.5,
          ui: ["Quasar Framework"],
          backend: ["Firebase"],
          features: [
            "Barcode scanning support",
            "Stock tracking",
            "Sales management",
            "Delivery scheduling",
            "Accounting report generation"
          ],
          developer: ["Jommel Cabiles"]
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
