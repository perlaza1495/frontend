<script>
	let productName = '';
	let description = '';
	let price;
	let image = '';
	let type = '';

	// async function createProduct() {
	// 	try {
	// 		const res = await fetch('http://localhost:4000/producto', {
	// 			method: 'POST',
	// 			headers: {
	// 				'Content-Type': 'application/json'
	// 			},
	// 			body: JSON.stringify({
	// 				productName: productName,
	// 				description: description,
	// 				price: price,
	// 				image: image,
	// 				type: type
	// 			})
	// 		});
	// 		const data = await res.json();

	// 		console.log('Estado de la transaccion', data);
    //         alert('Estado de la transaccion', data);
	// 	} catch (error) {
	// 		console.log('Error al guardar', error);
	// 	}
	// }

    async function createProduct() {
    try {
        const res = await fetch('http://localhost:4000/producto', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json'
            },
            body: JSON.stringify({
                productName,
                description,
                price,
                image,
                type
        })
        });

        const text = await res.text(); // Obtén la respuesta como texto
        if (res.ok) {
            productName = '';
	        description = '';
	        price;
	        image = '';
	        type = '';
        }
        console.log("Respuesta completa del servidor:", text);

        try {
            const data = JSON.parse(text); // Intenta parsearlo como JSON
            console.log('Estado de la transacción:', data);
            alert(`Estado de la transacción: ${JSON.stringify(data)}`);
        } catch (jsonError) {
            console.error("Error al parsear JSON:", jsonError);
        }
    } catch (error) {
        console.error('Error al guardar:', error);
    }
}
</script>

<div class="flex h-screen flex-col items-center justify-center">
	<h1 class="m-12 text-4xl">Crear Producto</h1>

	<form class="flex flex-col items-center justify-center">
		<input
			type="text"
			placeholder="Nombre del producto"
			class="m-2 w-64 rounded-xl border-2 border-solid border-gray-400 p-2"
			bind:value={productName}
		/>
		<input
			type="text"
			placeholder="Descripción del producto"
			class="m-2 w-64 rounded-xl border-2 border-solid border-gray-400 p-2"
			bind:value={description}
		/>
		<input
			type="number"
			placeholder="Precio del producto"
			class="m-2 w-64 rounded-xl border-2 border-solid border-gray-400 p-2"
			bind:value={price}
		/>
		<input
			type="text"
			placeholder="URL de la imagen"
			class="m-2 w-64 rounded-xl border-2 border-solid border-gray-400 p-2"
			bind:value={image}
		/>
		<button on:click={createProduct} class="m-12 rounded-xl bg-black px-4 py-2 text-white"
			>Crear Producto</button
		>
	</form>
</div>
