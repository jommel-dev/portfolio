<template>
  <div>
    <q-list class="rounded-borders">
      <q-item
        clickable
        tag="a"
        active-class="text-light-blue-6 text-bold"
        :to="{name: link}"
      >
        <q-item-section
          v-if="icon"
          avatar
        >
          <q-icon :name="icon" />
        </q-item-section>

        <q-item-section>
          <q-item-label>{{ title }}</q-item-label>
        </q-item-section>
      </q-item>
    </q-list>
  </div>
</template>

<script>
import { LocalStorage } from 'quasar'
import { defineComponent } from 'vue'

export default defineComponent({
    name: 'SideNavigation',
    props: {
        title: {
            type: String,
            required: true
        },

        link: {
            type: String,
            default: '#'
        },

        icon: {
            type: String,
            default: ''
        },

        code: {
          type: Number
        },
    },
    computed: {
      user: function(){
        let profile = LocalStorage.getItem('userData');
        return profile;
      }
    },
})
</script>
