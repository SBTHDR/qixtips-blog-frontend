<template>
    <div>
        <Navbar />
        <router-view/>
        <footer>
            Footer
        </footer>
    </div>
</template>

<script>
import Navbar from '@/components/layout/Navbar.vue'

export default {
  components: {
    Navbar,
  },
}
</script>
