<script>
  // @ts-nocheck
  import NavBar from "./components/NavBar/NavBar.svelte";
  import Router from "svelte-spa-router";
  import Route from "svelte-spa-router";
  import Header from "./components/Header/Header.svelte";
  import Footer from "./components/Footer/Footer.svelte";
  import Home from "./components/Home/Home.svelte";
  import ResourceHub from "./components/ResourceHub/ResourceHub.svelte";
  import SelfCareTools from "./components/SelfCareTools/SelfCareTools.svelte";
  import CommunityForum from "./components/CommunityForum/CommunityForum.svelte";
</script>

<NavBar />

<Router>
  <Route path="/" component={Home} />
  <Route path="/resource-hub" component={ResourceHub} />
  <Route path="/community-forum" component={CommunityForum} />
  <Route path="/self-care-tools" component={SelfCareTools} />
</Router>

<Footer />
