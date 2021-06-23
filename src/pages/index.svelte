<script>
    import { metatags } from '@roxi/routify'
    import { onMount } from "svelte"
    metatags.title = 'Eduardo'
    let theme = localStorage.getItem("colorTheme")
    function establishingTheme () {
        if(theme === "Claro") {
            bodyE.classList.remove("dark")
            bodyE.classList.add("light")
        } else if (theme === "Oscuro") {
            bodyE.classList.remove("light")
            bodyE.classList.add("dark")
        }
    }
    function handleSelect (e) {
        theme = e.target.value
        localStorage.setItem("colorTheme", theme)
        establishingTheme()
    }
    if(localStorage.getItem("colorTheme") === null) {
        localStorage.setItem("colorTheme", "Claro")
        establishingTheme()
    } else {
    }
    establishingTheme()
</script>
<h1>
    {theme}
</h1>
<a href="1">Prueba de que el tema se mantiene</a>
<select on:click={handleSelect} id="test">
    <option>Claro</option>
    <option>Oscuro</option>
</select>