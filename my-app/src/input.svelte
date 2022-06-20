<!-- Logica -->
<script>
    let value = "";
    let datos = [];

    const handlerInput = (event) => (value = event.target.value);

    $: if (value.length > 3) {
        console.log(value);
        fetch("https://www.omdbapi.com/?s=" + value + "&apikey=17d0ae7")
            .then((response) => response.json())
            .then((data) => {
                console.log(data);
                datos = data.Search || [];
            });
    }

    $: datos.length > 0 ? console.log(datos) : console.log("no hay datos");
</script>

<!-- HTML -->
<input placeholder="Buscar pelicula..." {value} on:input={handlerInput} />
<p>Encontradas: {datos.length}</p>

<!--desestructuracion y bucle-->
{#each datos as {Title,Poster,Year}}
    <p>{Title} - {Year}</p>
    <img src={Poster} alt="{Title}" />
    <br />
{/each}

<!-- Estilos -->
<style>
    :root {
        --pink: #f1062d;
        --white: #ffffff;
    }
    p {
        color: var(--pink);
    }
</style>
