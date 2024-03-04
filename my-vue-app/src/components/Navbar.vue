<script>

export default {
    data() {
        return {
            activePage: 0,
            useDarkNavbar: false,
            pages: [
                {
                    link: { text: 'Home', url: 'index.html' },
                    pageTitle: 'Home Page',
                    content: 'This is the home content'
                },
                {
                    link: { text: 'About', url: 'about.html' },
                    pageTitle: 'About Page',
                    content: 'This is the about content'
                },
                {
                    link: { text: 'Contact', url: 'contact.html' },
                    pageTitle: 'Contact Page',
                    content: 'This is the contact content'
                }
            ]
        }
    },
    computed: {
        navbarClasses() {
            return {
                'navbar-light': !this.useDarkNavbar,
                'bg-light': !this.useDarkNavbar,
                'navbar-dark': this.useDarkNavbar,
                'bg-dark': this.useDarkNavbar
            }
        }
    }


}
</script>

<template>
    <!-- Binding CSS Classes using Object Properties -->
    <nav :class="{ 'navbar-ligt bg-light': !useDarkNavbar, 'navbar-dark bg-dark': useDarkNavbar }"
        class="navbar navbar-expand-lg mb-4">
        <div class="container-fluid">
            <a class="navbar-brand" href="#">Navbar</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavDropdown"
                aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNavDropdown">
                <ul class="navbar-nav">
                    <li v-for="(page, index) in pages" class="nav-item">
                        <a class="nav-link" :class="{ active: active == index }" @click.prevent="activePage = index"
                            aria-current="page" :href="page.link.url">{{ page.link.text }}</a>
                    </li>
                </ul>
                <form class="d-flex">
                    <button class="btn btn-primary" @click.prevent="useDarkNavbar = !useDarkNavbar">Toggle</button>
                </form>
            </div>
        </div>
    </nav>

    <!-- Binding CSS Classes using Computed Properties -->
    <nav :class="navbarClasses" class="navbar navbar-expand-lg">
        <div class="container-fluid">
            <a class="navbar-brand" href="#">Navbar</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavDropdown"
                aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNavDropdown">
                <ul class="navbar-nav">
                    <li v-for="(page, index) in pages" class="nav-item">
                        <a class="nav-link" :class="{ active: active == index }" @click.prevent="activePage = index"
                            aria-current="page" :href="page.link.url">{{ page.link.text }}</a>
                    </li>
                </ul>
                <form class="d-flex">
                    <button class="btn btn-primary" @click.prevent="useDarkNavbar = !useDarkNavbar">Toggle</button>
                </form>
            </div>
        </div>
    </nav>

    <div id="content">
        <h1>{{ pages[activePage].pageTitle }}</h1>
    </div>

</template>

<style scoped></style>
