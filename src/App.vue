<template>
  <div id="app">
    <new-sponsorship-page></new-sponsorship-page>
    <portal-target name="modals" multiple></portal-target>
  </div>
</template>

<script>
import NewSponsorshipPage from '@/components/NewSponsorshipPage'

export default {
  name: 'App',
  components: {
      NewSponsorshipPage,
  },
  
}
</script>
