<template>
  <div class="q-pa-md" style="width: 100%;">
    <div class="row">
      <div class="col-12 col-md-12 q-pa-xs">
        <p class="text-h5 text-bold">Hi, I'm Jommel F. Cabiles,</p>
        <p class="">Web Developer with 7+ years of experience specializing in front-end development and UI/UX design. Skilled in building scalable web applications using Vue.js, Quasar, and modern frameworks. Strong background in API integration, database platforms, and Agile collaboration, with proven ability to deliver efficient and user-friendly solutions.</p>
        <p class="">As a freelance web developer and founder of a growing software business, I help startups, SMEs, and entrepreneurs bring their digital visions to life. From custom web apps to business-driven platforms, I focus on creating efficient, scalable, and visually engaging solutions. With a client-first approach, I combine technical expertise in Vue.js, Quasar, and database systems with Agile collaboration to deliver projects on time and aligned with business goals. Whether it’s developing a product MVP, integrating APIs, or optimizing user experiences, I ensure every solution adds measurable value.</p>
      </div>
      <div class="col-12 col-md-12 q-pa-xs">
        <q-card
          flat
          class="my-card bg-grey-1 overflow-auto"
          style="max-height: 50dvh;"
        >
          <q-card-section class="row items-center no-wrap" style="z-index: 999999;">
            <q-avatar
              size="md"
              color="black"
              text-color="white"
              icon="mdi-cog-outline"
            />
            <div class="q-ml-md text-weight-bold">Services</div>
            <q-space />
            <div class="q-ml-md text-caption">Offered Services by the Team</div>
          </q-card-section>
          <div class="row q-pa-sm">
            <div
              v-for="(item, idx) in services"
              :key="idx"
              class="col-3 col-xs-12 col-sm-4 col-md-3 q-pa-xs"
            >
              <q-card
                flat
                class="my-card-item"
                :class="item.color"
              >
                <q-card-section>
                  <div class="row items-center no-wrap">
                    <q-avatar
                      size="lg"
                      :color="item.iconBg"
                      text-color="white"
                      :icon="item.icon"
                    />
                    <span class="q-ml-sm text-blue-grey-9" >{{item.title}}</span>
                  </div>
                </q-card-section>
              </q-card>
            </div>
          </div>
        </q-card>
      </div>
      <div class="col-12 col-md-4 q-pa-xs">
        <q-card
          flat
          class="my-card bg-grey-1 q-pa-sm overflow-auto"
          style="max-height: 50dvh;"
        >

          <div class="row items-center no-wrap q-pa-sm">
            <q-avatar
              size="md"
              color="black"
              text-color="white"
              icon="mdi-information-variant-circle"
            />
            <div class="q-ml-md text-weight-bold">Contact Information</div>
            <q-space />
            <q-icon name="mdi-linkedin" color="light-blue" size="md" />
            <q-icon name="mdi-facebook" color="blue-10" size="md" />
          </div>

          <q-card-section>
            <span class="text-bold">Email:</span> <span>jommelcabiles.dev@gmail.com</span> <br/>
            <span class="text-bold">Mobile:</span> <span>0991-507-0977</span> <br/>
            <span class="text-bold">Viber:</span> <span>0926-369-3909</span>
          </q-card-section>
        </q-card>
        <q-card
          flat
          class="my-card bg-grey-1 q-pa-sm overflow-auto q-mt-sm"
          style="max-height: 50dvh;"
        >

          <div class="row items-center no-wrap q-pa-sm">
            <q-avatar
              size="md"
              color="black"
              text-color="white"
              icon="groups_3"
            />
            <div class="q-ml-md text-weight-bold">My Professional Team</div>
            <q-space />
            View All
          </div>

          <q-list >
            <q-item v-for="contact in teamList" :key="contact.id" class="q-mb-sm" clickable v-ripple>
              <q-item-section avatar>
                <q-avatar>
                  <q-icon name="mdi-account-circle" size="xl"/>
                </q-avatar>
              </q-item-section>

              <q-item-section>
                <q-item-label>{{ contact.name }}</q-item-label>
                <q-item-label caption class="text-bold" lines="1">{{ contact.position }}</q-item-label>
                <q-item-label caption lines="1">{{ contact.email }}</q-item-label>
              </q-item-section>

              <q-item-section side>
                <q-icon name="mdi-email-fast" color="warning" />
              </q-item-section>
            </q-item>
          </q-list>
        </q-card>
      </div>
      <div class="col-12 col-md-8 q-pa-xs">
        <q-card
          flat
          class="my-card bg-grey-1 overflow-auto"
          style="max-height: 50dvh;"
        >
          <q-card-section class="row items-center no-wrap" style="z-index: 999999;">
            <q-avatar
              size="md"
              color="black"
              text-color="white"
              icon="code"
            />
            <div class="q-ml-md text-weight-bold">Skills</div>
            <q-space />
            <div class="q-ml-md text-caption">Professional Skills</div>
          </q-card-section>
          <div class="row q-pa-sm">
            <div
              v-for="(item, idx) in dashCards"
              :key="idx"
              class="col-3 col-xs-12 col-sm-4 col-md-3 q-pa-xs"
            >
              <q-card
                flat
                class="my-card-item"
                :class="item.color"
              >
                <q-card-section>
                  <div class="row items-center no-wrap">
                    <q-avatar
                      size="lg"
                      :color="item.iconBg"
                      text-color="black"
                      :icon="item.icon"
                    />
                    <span class="q-ml-sm text-blue-grey-9" >{{item.title}}</span>
                  </div>
                </q-card-section>
              </q-card>
            </div>
          </div>
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
        dashCards: [
          {
            title: 'Javascript',
            icon: 'mdi-language-javascript',
            color: 'bg-yellow-2',
            iconBg: 'yellow-5',
          },
          {
            title: 'PHP',
            icon: 'mdi-language-php',
            color: 'bg-indigo-2',
            iconBg: 'indigo-5',
          },
          {
            title: 'HTML/CSS',
            icon: 'mdi-language-html5',
            color: 'bg-orange-2',
            iconBg: 'orange-5',
          },
          {
            title: 'VueJS',
            icon: 'mdi-vuejs',
            color: 'bg-green-2',
            iconBg: 'green-5',
          },
          {
            title: 'Google Firebase',
            icon: 'mdi-firebase',
            color: 'bg-amber-2',
            iconBg: 'amber-5',
          },
          {
            title: 'ReactJS',
            icon: 'mdi-react',
            color: 'bg-blue-2',
            iconBg: 'blue-5',
          },
          {
            title: 'NuxtJS',
            icon: 'mdi-nuxt',
            color: 'bg-light-green-2',
            iconBg: 'light-green-5',
          },
          {
            title: 'Git',
            icon: 'mdi-git',
            color: 'bg-teal-2',
            iconBg: 'teal-5',
          },
          {
            title: 'Cloud Servers',
            icon: 'mdi-google-cloud',
            color: 'bg-light-blue-2',
            iconBg: 'light-blue-5',
          },
          {
            title: 'NodeJS',
            icon: 'mdi-nodejs',
            color: 'bg-light-green-2',
            iconBg: 'green-5',
          },
        ],

        teamList: [
          {
            profile: '',
            name: 'Adrian Guillermo',
            contact: '09260696155',
            email: 'test@email.com',
            position: 'Senior Sofware Engineer'
          },
          {
            profile: '',
            name: 'Gerald Hope Ecaruan',
            contact: '',
            email: 'test@email.com',
            position: 'Wordpress Developer'
          },
          {
            profile: '',
            name: 'Ernest Alferez',
            contact: '',
            email: 'test@email.com',
            position: 'Robotics Engineer'
          },
          {
            profile: '',
            name: 'Ronald Fernando',
            contact: '',
            email: 'test@email.com',
            position: 'Software Engineer'
          },
          // {
          //   profile: '',
          //   name: 'John Vincent Paragas',
          //   contact: '',
          //   email: 'test@email.com',
          //   position: 'Web Developer'
          // },
          // {
          //   profile: '',
          //   name: 'John Levi Magdaraog',
          //   contact: '',
          //   email: 'test@email.com',
          //   position: 'Marketing'
          // },
          // {
          //   profile: '',
          //   name: 'Erwin Joseph Tantoco',
          //   contact: '',
          //   email: 'test@email.com',
          //   position: 'Marketing'
          // },
        ],
        services: [
          {
            title: 'Wordpress & Web Development',
            icon: 'mdi-web',
            color: 'bg-light-blue-2',
            iconBg: 'blue-5',
          },
          {
            title: 'Mobile App Development',
            icon: 'mdi-cellphone-link',
            color: 'bg-light-blue-2',
            iconBg: 'blue-5',
          },
          // {
          //   title: 'Robotics and Arduino',
          //   icon: 'mdi-language-javascript',
          //   color: 'bg-yellow-2',
          //   iconBg: 'yellow-5',
          // },
          {
            title: 'Information & Accounting Systems',
            icon: 'mdi-calculator-variant',
            color: 'bg-light-blue-2',
            iconBg: 'blue-5',
          },
          {
            title: 'Digital Marketing Services',
            icon: 'mdi-handshake',
            color: 'bg-light-blue-2',
            iconBg: 'blue-5',
          },
        ]
      }
  },
}
</script>
<style scoped>
.my-card{
    border-radius: 15px;
    /* box-shadow: 0px 0px 2px -1px !important; */
}
.my-card-item{
    border-radius: 10px;
}
</style>
