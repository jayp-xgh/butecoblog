<template>
    <div :class="{'overflow-hidden': showMenu}">
        <section class="bg-[#FF8A00] w-full h-[40vw] min-h-[30vh] max-h-[70vh] absolute top-0 z-[-1000]"></section>
        <div v-if="isMobile" class="sticky top-0 bg-[#FF8A00] w-full flex justify-between items-center p-4 z-50">
            <div class="flex items-center">
                <<img src="/public/img/logo.png" alt="butecodosdevs">
            </div>
            <button @click="toggleMenu" class="p-4 focus:outline-none transition-transform duration-300">
                <svg v-if="!showMenu" xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7" />
                </svg>
                <svg v-else xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                </svg>
            </button>
            <div class="fixed top-0 right-0 w-[70%] h-full bg-white opacity-95 transition-transform duration-500 ease-in-out transform z-40" :class="{'translate-x-full': !showMenu, 'translate-x-0': showMenu}">
                <div class="p-4">
                    <button @click="toggleMenu" class="p-4 focus:outline-none transition-transform duration-300 fixed top-4 right-4 z-50">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 text-black" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                        </svg>
                    </button>
                    <ul class="flex flex-col items-start p-8 mt-12">
                        <li class="text-[#FF8A00] font-black text-2xl mb-4 transition-transform duration-300" @click="toggleMenu">Aulas</li>
                        <li class="text-[#FF8A00] font-black text-2xl mb-4 transition-transform duration-300" @click="toggleMenu">Destaques</li>
                        <li class="text-[#FF8A00] font-black text-2xl mb-4 transition-transform duration-300" @click="toggleMenu">Doação</li>
                        <li class="text-[#FF8A00] font-black text-2xl mb-4 transition-transform duration-300" @click="toggleMenu">
                            <button class="bg-[#404EED] text-white font-bold p-2 rounded-lg flex items-center gap-4">Entrar no Discord
                                <svg width="38" height="30" viewBox="0 0 38 30" fill="none" xmlns="http://www.w3.org/2000/svg">
                                    <path d="M31.1421 4.08983C31.1319 4.0709 31.115 4.05631 31.0946 4.04882C28.8326 3.02449 26.4456 2.29379 23.9933 1.87499C23.9713 1.871 23.9486 1.87395 23.9283 1.88341C23.9081 1.89288 23.8914 1.90838 23.8805 1.92772C23.5553 2.51032 23.26 3.10873 22.9958 3.72069C20.351 3.32452 17.6607 3.32452 15.0158 3.72069C14.7506 3.10722 14.4513 2.50865 14.1193 1.92772C14.1078 1.90895 14.091 1.89394 14.0709 1.88455C14.0509 1.87517 14.0284 1.87185 14.0065 1.87499C11.5499 2.29191 9.15873 3.02266 6.89333 4.04882C6.87346 4.05713 6.85681 4.0715 6.84583 4.08983C2.32146 10.7637 1.08052 17.2676 1.68614 23.6953C1.68786 23.7115 1.69297 23.7271 1.70114 23.7412C1.70932 23.7554 1.72039 23.7677 1.73364 23.7773C4.36909 25.701 7.31639 27.1692 10.4499 28.1191C10.4724 28.126 10.4966 28.1257 10.5189 28.1184C10.5413 28.111 10.5607 28.0969 10.5746 28.0781C11.2469 27.1749 11.8427 26.2185 12.3558 25.2187C12.3627 25.205 12.3665 25.19 12.3672 25.1747C12.3679 25.1594 12.3654 25.1441 12.3598 25.1298C12.3542 25.1155 12.3457 25.1025 12.3348 25.0916C12.3239 25.0807 12.3109 25.0721 12.2965 25.0664C11.3551 24.7104 10.4438 24.2813 9.57114 23.7832C9.55572 23.7739 9.5428 23.761 9.53346 23.7458C9.52411 23.7305 9.51863 23.7132 9.51747 23.6954C9.5163 23.6776 9.51949 23.6598 9.52677 23.6434C9.53404 23.6271 9.54519 23.6127 9.55927 23.6015C9.74333 23.4668 9.92739 23.3262 10.0996 23.1855C10.1148 23.1724 10.1334 23.1637 10.1534 23.1606C10.1734 23.1575 10.1938 23.1601 10.2124 23.168C15.9243 25.7402 22.1111 25.7402 27.7577 23.168C27.7757 23.1593 27.7959 23.1558 27.8158 23.1578C27.8358 23.1599 27.8547 23.1675 27.8705 23.1797C28.0427 23.3203 28.2268 23.4668 28.4108 23.6015C28.4249 23.6127 28.4361 23.6271 28.4433 23.6434C28.4506 23.6598 28.4538 23.6776 28.4526 23.6954C28.4515 23.7132 28.446 23.7305 28.4366 23.7458C28.4273 23.761 28.4144 23.7739 28.399 23.7832C27.5286 24.2839 26.6169 24.7112 25.6736 25.0605C25.6592 25.0662 25.6462 25.0748 25.6353 25.0857C25.6244 25.0966 25.6159 25.1096 25.6103 25.1239C25.6047 25.1382 25.6022 25.1535 25.6029 25.1688C25.6036 25.1841 25.6074 25.1991 25.6143 25.2129C26.1364 26.2077 26.7317 27.1634 27.3955 28.0723C27.4094 28.0911 27.4288 28.1052 27.4512 28.1125C27.4735 28.1199 27.4977 28.1201 27.5202 28.1133C30.6628 27.1676 33.6186 25.6992 36.2602 23.7715C36.2737 23.7621 36.285 23.7499 36.2932 23.7357C36.3014 23.7215 36.3064 23.7057 36.3077 23.6894C37.0321 16.2656 35.0846 9.81444 31.1421 4.08983ZM13.2108 19.7812C11.489 19.7812 10.0758 18.2226 10.0758 16.3125C10.0758 14.4023 11.4652 12.8379 13.2108 12.8379C14.9743 12.8379 16.3755 14.4082 16.3458 16.3066C16.3458 18.2226 14.9565 19.7812 13.2108 19.7812ZM24.8127 19.7812C23.0908 19.7812 21.6777 18.2226 21.6777 16.3125C21.6777 14.4023 23.0611 12.8379 24.8127 12.8379C26.5761 12.8379 27.9774 14.4082 27.9477 16.3066C27.9477 18.2226 26.5702 19.7812 24.8127 19.7812Z" fill="white"/>
                                </svg>
                            </button>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
        <Navbar v-else />
        <main>
            <img
                class="mb-8 w-[92vw] max-w-[1368px] sm:w-[95vw] md:w-[92vw] lg:w-[91vw] xl:w-[92vw] max-w-7xl bg-[#4A393C] mx-auto translate-y-[25%] rounded-2xl shadow-2xl shadow-slate-900/40"
                src="/public/img/bar_moe.jpg"
                alt="Hero Image"
            />
        </main>
        <main class="max-w-7xl mx-auto mt-[200px] grid grid-cols-1 sm:grid-cols-2 gap-[3.5rem] p-4">
            <section class="col-span-1 sm:col-span-2">
                <h1 class="font-black text-xl text-[#FF8A00]">COMUNIDADE E FAMILIA</h1>
                <p class="text-3xl md:text-6xl text-[#000] font-black mt-4">
                    Sua nova casa para codificar e trocar ideias — Buteco dos Devs!
                </p>
            </section>
            <section class="w-full flex flex-col bg-[#1231] gap-[20px] p-4 rounded-lg">
                <img src="/public/img/ingles_aula.png" alt="Aula de Inglês" class="rounded-md aspect-video" />
                <h1 class="font-black text-xl text-[#FF8A00]">Aulas de Inglês</h1>
                <p class="text-xl text-[#2D3352] font-black">
                    Sexta é dia de inglês e resenha com o prof. Gustavo no Buteco!
                </p>
            </section>
            <section class="w-full flex flex-col bg-[#1231] gap-[20px] p-4 rounded-lg">
                <img src="/public/img/designer_pattern.png" alt="Aula de Inglês" class="rounded-md aspect-video" />
                <h1 class="font-black text-xl text-[#FF8A00]">Aulas Designer Pattern</h1>
                <p class="text-xl text-[#2D3352] font-black">
                    Toda terça feira é dia de aprender sobre padrões de design no Buteco!
                </p>
            </section>
        </main>
        <Footer />
    </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Footer from "./components/Footer.vue";

export default {
    name: "App",
    components: {
        Navbar,
        Footer,
    },
    data() {
        return {
            showMenu: false,
            isMobile: window.innerWidth <= 800,
        };
    },
    methods: {
        toggleMenu() {
            this.showMenu = !this.showMenu;
            document.body.style.overflow = this.showMenu ? 'hidden' : 'auto';
        },
        checkMobile() {
            this.isMobile = window.innerWidth <= 800;
        },
    },
    mounted() {
        window.addEventListener("resize", this.checkMobile);
    },
    beforeDestroy() {
        window.removeEventListener("resize", this.checkMobile);
    },
};
</script>

<style scoped>
.app-container {
    text-align: center;
    margin-top: 50px;
}
</style>
