<template>
    <v-footer
            v-bind="localAttrs"
            :padless="padless"
    >
        <v-card
                flat
                tile
                width="100%"
                class="white lighten-1 text-center"
        >

            <v-card-text class="black--text">
                {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
            </v-card-text>

            <v-card-text>
                <v-btn
                        v-for="icon in icons"
                        :key="icon"
                        class="mx-4"
                        icon
                >
                    <v-icon size="24px">{{ icon }}</v-icon>
                </v-btn>
            </v-card-text>
        </v-card>
    </v-footer>
</template>

<script>
    export default {
        data: () => ({
            icons: [
                'fa fa-facebook fa-lg',
                'fa fa-twitter fa-lg',
                'fa fa-google-plus fa-lg',
                'fa fa-linkedin fa-lg',
                'fa fa-instagram fa-lg',
            ],
            items: [
                'default',
                'absolute',
                'fixed',
            ],
            padless: true,
            variant: 'default',
        }),
        computed: {
            localAttrs () {
                const attrs = {}

                if (this.variant === 'default') {
                    attrs.absolute = false
                    attrs.fixed = false
                } else {
                    attrs[this.variant] = true
                }
                return attrs
            },
        },
    }
</script>

<style scoped>

</style>