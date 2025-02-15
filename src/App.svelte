<svelte:options customElement={{
  tag: "xlgames-whmcs",
  props: {
    href_style: {type: 'String', attribute: 'href-style'}
  }
}}/>
<svelte:head>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com">
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@100;300;400;500&display=swap" rel="stylesheet">
</svelte:head>

<link rel="stylesheet" type="text/css" href={href_style}/>

<script>
  import {onMount} from "svelte";
  import AdminPage from "./lib/pages/AdminPage.svelte";
  
  let {href_style} = $props();

  onMount(() => {
    let contentarea = document.getElementById("contentarea");
    if (contentarea) {
      let h1_array = contentarea.getElementsByTagName("h1");
      if (h1_array.length > 0) h1_array[0].remove();
    }
  })
</script>

<div style="all: initial;">
  <div class="font-roboto font-light tracking-wide text-3xl">
    <AdminPage />
  </div>
</div>

<div class="min-h-[60rem]"></div>