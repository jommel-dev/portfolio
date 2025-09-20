<template>
  <q-layout view="lHh Lpr lFf">
    <q-drawer
      class="q-pa-sm"
      v-model="leftDrawerOpen"
      show-if-above
    >
      <q-card
        flat
        class="my-card bg-grey-4"
        style="max-height: 50dvh;"
      >
        <q-img
          src="/portfolio/images/fwdslogo.png"
          alt="Profile"
          style="width: 100%; height: 100%; border-radius: 10px;"
          class="q-mr-sm"
        />
      </q-card>
      <q-card
        flat
        class="my-card bg-grey-1 q-mt-sm"
        style="max-height: 50dvh;"
      >
        <q-card-section class="text-center">
          <q-img
            src="/portfolio/images/profile.jpg"
            alt="Profile"
            style="width: 80px; height: 80px; border-radius: 50%; object-fit: cover; border: 2px solid #fff; box-shadow: 0 2px 8px rgba(0,0,0,0.1);"
            class="q-mb-sm"
          />
          <div class="text-h6">Jommel F. Cabiles <q-icon name="verified" color="primary" /></div>
          <div class="text-subtitle2">Owner/Web Developer</div>
        </q-card-section>
      </q-card>
      <q-btn class="q-mt-sm full-width" rounded label="Schedule a Meeting" icon="mdi-rocket-launch" no-caps color="primary"></q-btn>
      <q-list>
        <q-item-label
          class="text-bold"
          header
        >
          Informative Links
        </q-item-label>

        <EssentialLink
          v-for="link in linksList"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue'
import EssentialLink from 'components/EssentialLink.vue'

const linksList = [
  {
    title: 'About',
    caption: 'Information about business/team',
    icon: 'school',
    link: 'about'
  },
  {
    title: 'Projects',
    caption: 'Showcase of projects developed',
    icon: 'chat',
    link: 'projects'
  },
  // {
  //   title: 'Contact Us',
  //   caption: 'Get in touch with us',
  //   icon: 'record_voice_over',
  //   link: 'https://forum.quasar.dev'
  // },
  // {
  //   title: 'Ask for Quotation',
  //   caption: 'Get in touch with us',
  //   icon: 'record_voice_over',
  //   link: 'https://forum.quasar.dev'
  // },
]

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      linksList,
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
})
</script>


<style scoped>
.my-card{
  border-radius: 15px;
  /* box-shadow: 0px 0px 2px -1px !important; */
}
</style>
