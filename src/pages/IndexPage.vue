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
          <q-card-section class="row items-center no-wrap">
            <q-avatar
              size="md"
              color="black"
              text-color="white"
              icon="mdi-cog-outline"
            />
            <div class="q-ml-md text-h6 text-weight-bold">Services</div>
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
                class="my-card-item cursor-pointer"
                :class="item.color"
                @click="showServiceDesc(item)"
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
                    <q-space />
                    <!-- <q-icon
                      @click="showServiceDesc(item)"
                      :name="showService ? 'mdi-eye-off' : 'mdi-eye'"
                      :color="showService ? 'negative' : 'primary'"
                      size="sm"
                    /> -->
                  </div>
                </q-card-section>
              </q-card>
            </div>
            <div v-if="showService" class="col-12">
              <q-banner inline-actions rounded class="bg-light-blue-4 text-white">
                <p>{{ serviceDetails.subTitle }}</p>
                {{ serviceDetails.description }}

                <template v-slot:action>
                  <q-btn flat round icon="close" @click="showService = !showService" />
                </template>
              </q-banner>
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
            <div class="q-ml-md text-h6 text-weight-bold">Contact Information</div>
            <q-space />
            <q-btn
              flat
              icon="mdi-linkedin"
              color="primary"
              type="a"
              :href="'https://www.linkedin.com/in/cabiles-jommel-38741b207/'"
              target="_blank"
            />
            <q-btn
              flat
              icon="mdi-facebook"
              color="blue-10"
              type="a"
              :href="'https://www.facebook.com/jommel.f.cabiles'"
              target="_blank"
            />
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
            <div class="q-ml-md text-h6 text-weight-bold">My Professional Team</div>
            <q-space />
            View All
          </div>

          <q-list >
            <q-item v-for="contact in teamList" :key="contact.id" class="q-mb-sm" clickable v-ripple>
              <q-item-section avatar>
                <q-avatar>
                  <q-img :src="contact.profile" />
                  <!-- <q-icon name="mdi-account-circle" size="xl"/> -->
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
          <q-card-section class="row items-center no-wrap">
            <q-avatar
              size="md"
              color="black"
              text-color="white"
              icon="code"
            />
            <div class="q-ml-md text-h6 text-weight-bold">Skills</div>
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

        <q-card
          flat
          class="my-card bg-grey-1 q-mt-sm overflow-auto"
          style="max-height: 50dvh;"
        >
          <q-card-section class="row items-center no-wrap">
            <q-avatar
              size="md"
              color="black"
              text-color="white"
              icon="mdi-briefcase"
            />
            <div class="q-ml-md text-h6 text-weight-bold">Experience</div>
            <q-space />
            <div class="q-ml-md text-caption">Work experiences to the industries and corporate</div>
          </q-card-section>
          <div class="row q-pa-sm">
            <div
              v-for="(item, idx) in experience"
              :key="idx"
              class="col-3 col-xs-12 col-sm-4 col-md-6 q-pa-xs"
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
                    <span class="q-ml-sm text-blue-grey-9" >
                      <span class="text-bold">{{item.title}}</span><br />
                      {{item.yearStarted}} - {{ item.status === 'current' ? 'Current' : item.yearEnded }}
                    </span>
                    <q-space />
                    <q-btn
                      flat
                      color="primary"
                      type="a"
                      label="Details"
                      no-caps
                      @click="showExpDetails(item)"
                    />
                  </div>
                </q-card-section>
              </q-card>
            </div>
          </div>
        </q-card>
      </div>
    </div>

    <q-drawer
      side="right"
      v-model="detailsExperience"
      bordered
      overlay
      :width="900"
    >
      <q-card
        flat
        class=" bg-white"
      >
        <q-card-section class="row items-center no-wrap" style="z-index: 999999;">
          <div>
            <div class="text-h5 text-weight-bold">Experience Details in <span :class="`text-${expDetails.iconBg}`">{{ expDetails.title }}</span></div><br />
            {{ expDetails.subTitle }}
          </div>
          <q-space />

          <q-btn size="sm" round color="red" icon="close" @click="detailsExperience = !detailsExperience" />
        </q-card-section>
        <q-separator />
        <q-card-section>
          <div>
            <div class="text-h6 ">
              Projects:
              <q-chip v-for="(proj) in expDetails.projects" :key="proj" outline color="primary" text-color="white" icon="apps">
                {{ proj }}
              </q-chip>
            </div>
          </div>
          <br/>
          <div>
            <div class="text-h6 ">Role and Responsibilities: </div>
             <q-list>
              <q-item v-for="(r, indx) in expDetails.role" :key="indx">
                <q-item-section>
                  <q-item-label><q-icon name="rebase_edit" size="sm" color="primary" /> {{ r }}</q-item-label>
                </q-item-section>


              </q-item>
            </q-list>
          </div>
        </q-card-section>
      </q-card>
    </q-drawer>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data(){
      return {
        detailsExperience: false,
        showService: false,
        serviceDetails: {},
        expDetails: {},
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
            email: 'louieflores16@gmail.com ',
            position: 'louieflores16@gmail.com '
          },
          {
            profile: '/portfolio/images/ronald.png',
            name: 'Ronald Fernando',
            contact: '',
            email: 'ronaldfernando.dev@gmail.com',
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
            show: false,
            subTitle: 'Wordpress, Web Base System',
            description: 'We craft stunning, user-friendly websites that don’t just look good—they perform. From business portfolios to e-commerce stores, we design responsive, SEO-ready, and scalable solutions that help you stand out online.',
          },
          {
            title: 'Mobile App Development',
            icon: 'mdi-cellphone-link',
            color: 'bg-light-blue-2',
            iconBg: 'blue-5',
            show: false,
            subTitle: 'Mobile Application for Web Apps',
            description: 'ransform your ideas into powerful mobile apps. Our team builds fast, secure, and engaging applications for Android and iOS that provide seamless user experiences and help your business stay connected with customers on the go.',
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
            show: false,
            subTitle: 'Information Systems, Inventory, Accounting, etc.',
            description: 'Simplify your operations with custom-built systems that automate processes, track data, and provide actionable insights. From inventory to accounting, we deliver reliable solutions tailored to your business needs.',
          },
          {
            title: 'Digital Marketing Services',
            icon: 'mdi-handshake',
            color: 'bg-light-blue-2',
            iconBg: 'blue-5',
            show: false,
            subTitle: 'Promotional, SEO, etc.',
            description: 'Grow your brand and reach the right audience with data-driven strategies. From social media management to SEO and online advertising, we create campaigns that increase visibility, drive traffic, and boost conversions.',
          },
        ],
        experience: [
          {
            title: 'Accenture Inc. Philippines',
            status: 'current',
            yearStarted: 'Sept 2021',
            yearEnded: '',
            icon: 'mdi-greater-than',
            color: 'bg-deep-purple-2',
            iconBg: 'deep-purple-5',
            show: false,
            subTitle: 'Serving as a UI Developer on a team using the Vue.js and Quasar Framework, working in an Agile methodology environment.',
            role: [
              'Developed and maintained UI components, ensuring consistency and responsiveness across multiple enterprise applications.',
              'Collaborated with the UX Team to transform design mockups into functional and user-friendly interfaces.',
              'Built reusable and configurable components, reducing development time for future projects.',
              'Integrated APIs for module processes to streamline system interoperability.',
              'Led proof-of-concept (POC) efforts for module pods, validating feasibility before deployment.',
              'Acted as Business Analyst for Access Management, optimizing workflows and automating processes.',
              'Designed and created wireframes for new workflows, aligning with business needs.'
            ],
            projects: 'ASTD (Analytical Studio), Intient Patient, Intient Unify, Access Management',
          },
          {
            title: 'Telcom Live Content Inc.',
            status: 'past',
            yearStarted: 'Jan 2019',
            yearEnded: 'July 2021',
            icon: 'mdi-alpha-t-box-outline',
            color: 'bg-amber-2',
            iconBg: 'amber-5',
            show: false,
            subTitle: 'Worked as a Frontend Developer specializing in PHP CodeIgniter, Nuxt.js, and Vue.js, with additional roles in graphic design and task management.',
            role: [
              'Designed and developed responsive front-end modules with modern frameworks',
              'Utilized Git/Bitbucket for version control and JIRA/Trello for Agile project management.',
              'Provided client data support with MySQL, including database queries and troubleshooting.',
              'Designed UI elements with Adobe Photoshop to enhance user experience.',
              'Gained exposure to cloud instances for deployment and system hosting.'
            ],
            projects: 'PayLoro (Merchant/Admin/Dashboard), PCIMS (Product Certification Information Management System), IA Permits & Clearances Portal, IA SSO Frontend, UPCDD BMD Portal, IA Ticketing',
          },
          {
            title: 'IFormat Logic',
            status: 'past',
            yearStarted: 'Nov 2017',
            yearEnded: 'Jan 2019',
            icon: 'mdi-alpha-f-box',
            color: 'bg-cyan-2',
            iconBg: 'cyan-5',
            show: false,
            subTitle: 'Worked on WordPress, Magento, and CodeIgniter projects with both front-end and back-end responsibilities.',
            role: [
              'Maintained and updated client websites, ensuring quality and timely delivery.',
              'Designed banners, icons, and digital assets to support client branding.',
              'Customized and extended features on CMS-based platforms.',
            ],
            projects: 'WordPress Sites, Magento Sites, CodeIgniter Projects',
          },
          {
            title: 'Easysoft Software Solutions',
            status: 'past',
            yearStarted: 'Nov 2017',
            yearEnded: 'Jan 2019',
            icon: 'mdi-alpha-e-box',
            color: 'bg-blue-2',
            iconBg: 'blue-5',
            show: false,
            subTitle: 'Worked on WordPress, Magento, and CodeIgniter projects with both front-end and back-end responsibilities.',
            role: [
              'Maintained and updated client websites, ensuring quality and timely delivery.',
              'Designed banners, icons, and digital assets to support client branding.',
              'Customized and extended features on CMS-based platforms.',
            ],
            projects: 'EasyResto, EasyLoan',
          },
        ]
      }
  },
  methods:{
    showServiceDesc(item){
      this.showService = true;
      this.serviceDetails = item
    },
    showExpDetails(item){
      this.detailsExperience = true;
      item.projects = item.projects.split(', ')
      this.expDetails = item
    }
  }
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
