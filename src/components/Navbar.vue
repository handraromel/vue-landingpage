<template>
    <transition name="fade" mode="out-in">
            <b-navbar toggleable="lg" type="dark" class="fixed-top navigation-clean" v-if="showNavbar">
                <b-navbar-brand class="navbar-brand" href="#"><img src="../assets/vuetify.png" alt="" width="20%"></b-navbar-brand>

                <b-navbar-toggle class="navbar-toggler" target="nav-collapse"></b-navbar-toggle>

                <b-collapse id="nav-collapse" is-nav>
                    <!-- Right aligned nav items -->
                    <b-navbar-nav class="ml-auto">
                        <b-nav-item class="nav-link" href="#">This is link 1</b-nav-item>
                        <b-nav-item class="nav-link" href="#">This is link 2</b-nav-item>
                        <b-nav-item class="nav-link" href="#">This is link 3</b-nav-item>
                    </b-navbar-nav>
                </b-collapse>
            </b-navbar>
    </transition>
</template>

<script>
    export default {
        data() {
            return {
                title: "Landing Page",
                showNavbar: false
            }
        },
        methods: {
            handleScroll () {
                window.pageYOffset > 0 ? this.showNavbar=true : this.showNavbar = false
            }
        },
        created() {
            window.addEventListener('scroll', this.handleScroll)
        },
        destroyed() {
            window.removeEventListener('scroll', this.handleScroll)
        }
    }
</script>

<style scoped>
    .navigation-clean {
        background: rgba(63, 63, 63, 0.81);
        padding: 0.6rem 6rem 0.6rem 6rem;
        color: #333;
        border-radius: 0;
        box-shadow: none;
        border: none;
        margin-bottom: 0;
    }

    .fade-enter-active {
        transition: all 1s;
    }

    .fade-leave-active {
        transition: all 0.5s;
    }

    .fade-enter, .fade-leave-to {
        opacity: 0;
    }
</style>