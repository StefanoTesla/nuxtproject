<script setup>
const { locale, locales } = useI18n()
const switchLocalePath = useSwitchLocalePath()
const availableLocales = computed(() => {
  return (locales.value).filter(i => i.code !== locale.value)
})
</script>


<template>

    <nav class="nav">
        <div class="nav_logo">logo</div>
        <div class=""></div>
        <div class="nav_menu">
            <div class="nav_large">
                <ul class="menu_portait_items">
                    <li><NuxtLink to="/">Home</NuxtLink></li>
                    <li><NuxtLink to="/vini">Vini</NuxtLink></li>
                    <li><a href="">Vieni a trovarci</a></li>
                    <li><a href="">Shop</a></li>
                    <li><a href="">News</a></li>
                    <li><a href="">Contatti</a></li>
                    <li><a href="">IN</a></li>
                    <li><a href="">FA</a></li>
                    <li><NuxtLink v-for="locale in availableLocales" :key="locale.code" :to="switchLocalePath(locale.code)">{{locale.name}}</NuxtLink></li>
                    <li><a href="">CA</a></li>
                </ul>
            </div>
            <div class="nav_mobile">mobile</div>
        </div>
    </nav>
</template>


<style scoped>
.nav {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: horizontal;
  -webkit-box-direction: normal;
      -ms-flex-direction: row;
          flex-direction: row;
  -ms-flex-wrap: nowrap;
      flex-wrap: nowrap;
  -webkit-box-pack: justify;
      -ms-flex-pack: justify;
          justify-content: space-between;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  padding-top: 1em;
  padding-bottom: 1em;
  background: rgba(255, 255, 255, 0.3);
}

.nav_logo {
  margin-left: 1.4em;
  background: #f00;
}

.nav_menu {
  margin-right: 1.4em;
}

.menu_portait_items {
  display: -webkit-inline-box;
  display: -ms-inline-flexbox;
  display: inline-flex;
  -webkit-box-orient: horizontal;
  -webkit-box-direction: normal;
      -ms-flex-direction: row;
          flex-direction: row;
  -ms-flex-wrap: nowrap;
      flex-wrap: nowrap;
  gap: 22px;
  text-transform: uppercase;
}

.nav_large{
  display:none;
}


@media (min-width: 768px) { 
  .nav_large{
    display:block;
  }
  .nav_mobile{
    display:none;
  }
}
</style>