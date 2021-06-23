<script>
	import { onMount } from "svelte"
	onMount(() => {
		let theme,
	        bodyE = document.querySelector("body")


	    theme = localStorage.getItem("colorTheme")
		function establishingTheme () {
		    if(theme === "Claro") {
		        bodyE.classList.remove("dark")
		        bodyE.classList.add("light")
		    } else if (theme === "Oscuro") {
		        bodyE.classList.remove("light")
		        bodyE.classList.add("dark")
		    }
		}
		establishingTheme()
	})
</script>
<!-- routify:options preload="proximity" -->
<slot />
