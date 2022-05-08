<template>
    <nav id="navbar" class="px-4 py-4 sm:py-6 bg-white shadow sm:fixed w-full z-10 transition-colors duration-500"
        :class="{ 'sm:bg-transparent sm:shadow-none': !showWhiteBackground }">
        <div class="container mx-auto flex flex-col sm:flex-row items-center justify-between">
            <div class="w-full flex flex-row items-center justify-between">
                <div class="text-3xl font-bold">
                    <span :class="{'sm:text-white': !showWhiteBackground}">Qix</span>
                    <span class="text-primary">tips</span>
                </div>

                <div>
          <button v-show="!isVisible"
                  class="sm:hidden"
                  @click="toggle">
            <svg class="w-6 h-6"
                 fill="none"
                 stroke="currentColor"
                 viewBox="0 0 24 24"
                 xmlns="http://www.w3.org/2000/svg">
              <path stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M4 6h16M4 12h16M4 18h16"></path>
            </svg>
          </button>

          <button v-show="isVisible"
                  class="sm:hidden"
                  @click="toggle">
            <svg class="w-6 h-6"
                 fill="none"
                 stroke="currentColor"
                 viewBox="0 0 24 24"
                 xmlns="http://www.w3.org/2000/svg">
              <path stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M6 18L18 6M6 6l12 12"></path>
            </svg>
          </button>
        </div>
                
            </div>
            <div class="mt-4 sm:mt-0 w-full sm:space-x-4 sm:text-right sm:block"
                :class="{ 'hidden': !isVisible, 'sm:text-white': !showWhiteBackground }">
                <NavbarLink to="/" label="Home" />
                <NavbarLink to="/articles" label="Articles" />
                <NavbarLink to="/about" label="About" />
                <NavbarLink to="/contact" label="Contact" />
            </div>
        </div>
    </nav>
</template>

<script>
    import NavbarLink from "./NavbarLink.vue";
    import { useToggle } from "@/composables/useToggle";

    export default {
        components: {
            NavbarLink,
        },
        setup() {
            let { isVisible, toggle } = useToggle();

            return {
                isVisible,
                toggle,
            };
        }
    }
</script>

<style>

</style>