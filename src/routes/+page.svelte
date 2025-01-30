<script>
	import { goto } from "$app/navigation";
   
</script>
	<section>
		<img class="w-full" src="portada.png" alt="" />
	</section>

	<section class="h-[550px] justify-center items-center flex flex-col">
		<h1 class="m-16 text-center text-2xl font-bold">Nuestra Marca</h1>
        <p class="mx-36 text-2xl text-gray-500 leading-8 italic">"En nuestra empresa, el arte del crochet se transforma en elegancia y exclusividad. Cada bolso es una obra maestra tejida a mano, donde el diseño sofisticado se une con la sostenibilidad. Utilizamos lana de alta calidad y trapillo reciclado para crear piezas únicas que realzan cualquier estilo con un toque de glamour. Más que accesorios, son declaraciones de moda, fusionando lujo artesanal y conciencia ecológica en cada detalle."</p>
	    <button class="rounded-xl bg-black text-white h-12 w-36 m-16" 
        on:click={() => goto('/productos')}>
           Ver productos
        </button>
    </section>

