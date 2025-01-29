<script>
	import { onMount } from "svelte";
	import { on } from "svelte/events";

    onMount(() => {
        console.log("se inicio")
        getProducts()
    })
let productos = []

function getProducts() {
    fetch('http://localhost:4000/productos')
    .then(response => response.json())
    .then(data => {
        console.log(data)
        productos = data
    })
    .catch(error => {
        console.log(error)
    })}

</script>
<section>
<img class="w-full" src="portada.png" alt="">
</section>

<div class="grid grid-cols-4 gap-4 items-center justify-center justify-self-center">
    {#each productos as producto}
        <div class="w-[188px] h-[390px] border-2x border-solidx p-4 m-8 rounded-xl shadow-2xl ">   
            <img src={producto.image} alt={producto.productName} class="w-64 h-56 object-cover">
            <p class="font-bold text-gray-800">{producto.productName}</p>
            <p class="text-sm text-gray-500">{producto.description}</p>
            <p class="font-bold text-red-400x">${producto.price}</p>
        </div>
    {/each}
</div>
