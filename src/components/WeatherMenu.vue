<script setup>

//  defineProps({
//     menuitems: Array
//     })


</script>

<script>
    export default { 
        components: {},
        // props: ['menuitems', 'activeitem'],
        emits: ['click'], // declare events that 

        data() {
                return {
                    // current_active: "",
                    menuitems: ["Temperature", "Forecast2Hour", "Forecast24Hour", "Forecast4Days"],
                    current_active: "Temperature"
                }
            },
        methods: {
            do_click(item) {
                this.current_active = item;
                this.$emit('click', item);
            }
        }, 
      
    }
</script>

<template>        
<!-- BS navbar: start -->
<nav class="navbar navbar-dark navbar-expand-sm bg-dark">
    <div class="container-fluid">
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse"
            data-bs-target="#sgWeatherNavbar" aria-controls="sgWeatherNavbar" aria-expanded="false"
            aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="sgWeatherNavbar">
            <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                <li class="nav-item"   v-for="item in menuitems">
                    <!-- <a :class="{ 'nav-link': true,  'active': current_active === item }" 
                            :aria-current="{'page': current_active === item}"
                            href='#' @click="do_click(item)"> -->
                    <router-link :to="'/' + item + '/'" 
                        :class="{ 'nav-link': true,  'active': current_active === item }" 
                        
                        @click="do_click(item)">
                        
                        {{item}}
                    </router-link>
                    <!-- </a> -->
                </li>
            </ul>
        </div>
    </div>
</nav>
</template>
