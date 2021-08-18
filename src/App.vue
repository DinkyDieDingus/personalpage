<template>
    <nav class="navbar" role="navigation" aria-label="main navigation">
        <div class="navbar-brand">
            <a class="navbar-item" href="/">
                <figure class="image">
                    <img class="image is-rounded" src="./assets/binky.png">
                </figure>
                <p class="brand-name">
                    Sean Spiegl
                </p>
            </a>
        </div>
    </nav>

    <section class="section">
        <h2 class="subtitle" v-html="slogan"></h2>
        <h2 class="title">{{unit}} Help!</h2>
    </section>

    <section class="section list left-centered">
        <ul style="list-style-type:circle;">
            <li>Are your labs taking way too long to finish?</li>
            <li>Do you get stuck on errors for hours at a time?</li>
            <li>Does it feel like you have no idea what you are doing?</li>
        </ul>
    </section>

    <section class="section padded left-centered">
        <Vim :lines="aboutMe" :comment="commentStyle"/>
    </section>

    <section class="section">
        <nav class="level padded">
            <div class="level-item has-text-centered">
                <div>
                    <p class="heading">Group Session</p>
                    <p class="title is-1">${{groupPrice}}/hour</p>
                </div>
            </div>
            <div class="level-item has-text-centered">
                <div>
                    <p class="heading">1-on-1 Tutoring</p>
                    <p class="title is-1">${{indivPrice}}/hour</p>
                </div>
            </div>
        </nav>
    </section>

    
</template>

<script scoped>
import Vim from './components/Vim.vue'
export default {
name: 'App',
    data() {
        return {
            groupPrice: 20,
            indivPrice: 25,
            unit: "UCP",
            commentStyle: "//",
            unitFull: "Unix & C Programming",
            slogan: "Does <i>UCP</i> make you want to UC-<i>flee</i> you computing <i>degree</i>?",
        }
    },
    components: {
        Vim

    },
    computed: {
        aboutMe() {
            return [
                {content:"Hi! My name is Sean and I worked in the Curtin Computing Deparment for 2 years as a Lab Tutor", comment: true},
                {content:"I love coding and I love teaching students to code!",comment: false},
                {content:`I offer private tutoring for ${this.unitFull} and other first year computing units`, comment: false}
            ]
        }
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  text-align: center;
}

.list {
    font-size: 24px;
}

.left-centered {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: left;
}

.vim {
    font-family: monospace;
    background: black;
    color: lightgray;
    font-size: 15px;
    line-height: 130%;
}

.brand-name {
  margin-left: 0.5em;
  margin-top: 0.3em;
}

.padded {
    padding: 0 2em 0 2em;
}
</style>
