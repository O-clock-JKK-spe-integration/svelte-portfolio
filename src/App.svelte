<script>
  import Router from "svelte-spa-router"
  import Contact from "./lib/pages/Contact.svelte"
  import Home from "./lib/pages/Home.svelte"
  import NotFound from "./lib/pages/NotFound.svelte"
  import MentionsLegales from "./lib/pages/MentionsLegales.svelte"
  import Portfolio from "./lib/pages/Portfolio.svelte"
  import Header from "./lib/components/Header.svelte"
  import Footer from "./lib/components/Footer.svelte"

const routes = {
  "/": Home,
  "/contact": Contact,
  "/portfolio": Portfolio,
  "/mentions-legales": MentionsLegales,
  "*": NotFound
}

</script>

<div class="container">

<Header />

<Router {routes} />

<Footer />

</div>

<style></style>