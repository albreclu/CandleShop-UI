<template>
    <footer class="p-4 bg-[#6a6a6a] text-white flex justify-between items-center">
        <p>Copyright &copy; {{ copyRight }}</p>

        <div class="flex gap-6">
            <footer-button v-for="button in footerButtons" :text="button.text" :route="button.route" />
        </div>
    </footer>
</template>

<script lang="ts" setup>
    interface FooterButton {
        text: string
        route: string
    }

    import { computed, ref } from 'vue'
    import FooterButton from './FooterButton.vue'

    const footerButtons = ref<FooterButton[]>([
        { text: 'Impressum', route: '/impressum' },
        { text: 'Kontakt', route: '/kontakt' },
        { text: 'Datenschutz', route: '/datenschutz' },
    ])

    const copyRight = computed(() => {
        return new Date().getFullYear()
    })
</script>
