<script lang="ts">
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  function event(documentName: string) {
      console.log("emitting event, button pressed: " + documentName);
      dispatch('documentSelection', {
          document: documentName
      });
  }
</script>

<div class="sidebar">
  <div class="links_to_pages">
      <ul>
          <li><a href="#" on:click={() => event("Welcome")}>Welcome</a></li>
      </ul>
      <h5 class="sidebar-title">Propositional Logic</h5>
      <ul>
      <li ><a href="#" on:click={() => event("Syntax")}>Syntax</a></li>
      <li ><a href="#" on:click={() => event("Semantics")}>Semantics</a></li>
      <li ><a href="#"on:click={() => event("NaturalD")}>Natural deduction</a></li>
      </ul>
      <ul>
          <li class="sidebar-subgroup"><a href="#" on:click={() => event("Conjunction")}>Conjunction</a></li>
          <li class="sidebar-subgroup"><a href="#" on:click={() => event("Conditional")}>Conditional</a></li>
          <li class="sidebar-subgroup"><a href="#" on:click={() => event("Disjunction")}>Disjunction</a></li>
          <li class="sidebar-subgroup"><a href="#" on:click={() => event("Negation")}>Negation</a></li>
          <li class="sidebar-subgroup"><a href="#" on:click={() => event("CombinedRules")}>Combinations</a></li>
      </ul>
  </div>
</div>

<style>
  .sidebar {
      position: fixed;
      width: 10vw;
      border-right: 1px solid #000000;
      background: white;
      color: #0d0d0d;
      text-align: left;
      left: 2px;
      top: 5px;
      bottom:5px;
      padding-top: 20px; /* Adjust top padding as needed */
      padding-right: 5px;
      transition: all ease .3s;
      overflow-y: hidden;
  }

  .sidebar-title{
      font-size: 17px; /* Adjust font size as needed */
      text-align: left;
      margin: 10px 0;
      border-top: 1px solid hsl(0, 0%, 60%);
      border-bottom: 1px solid hsl(0, 0%, 60%);
      padding: 8px 16px;
  }

  .sidebar-subgroup {
      font-size: 15px; /* Adjust font size as needed */
	font-style: italic;
	font-weight: normal;
      text-align: left;
      margin: 10px 0;
      padding: 8px 10px;
      
  }

  .links_to_pages ul {
      list-style-type: none;
      padding: 0;
      margin: 0;
  }

  .links_to_pages li {
      margin-bottom: 10px;
  }

  .links_to_pages a {
      display: block;
      padding: 8px 16px;
      color: black;
      text-decoration: none;
      text-align: left;
      border-radius: 4px;
      transition: background-color 0.3s;
  }

  .links_to_pages a:hover {
      background-color: #f0f0f0;
  }
</style>
