<script>
	let tareas = [];
    let nombreTarea = '';
    function agregarTarea(event){
        if(event.key === 'Enter'){
            const tarea = {
                nombre: nombreTarea,
                estado: false
            }
            tareas.push(tarea);
            console.log(tareas);
            tareas = tareas;
            nombreTarea = '';
        }
    }
    function deleteTarea(i){
        tareas.splice(i, 1);
        tareas = tareas;
    }
    function actualizarTarea(tarea, i){
        tareas[i].estado = !tarea.estado
    }
</script>

<main>
	<div class="container">
		<div class="row">
			<div class="col-lg-8 offset-lg-2 mt-5">
				<input 
					type="text" 
					class="form-control" 
					bind:value={nombreTarea} 
					on:keydown={agregarTarea}
					placeholder="Ingrese una nueva tarea"
				>
			</div>

			<div class="col-lg-6 offset-lg-3">
				{
					#if tareas.length === 0
				}
				<div class="card p-2">
					<h5>No hay tareas</h5>
				</div>
				{
					/if
				}

				<ul class="list-group">
					{#each tareas as tarea, i}
					<li class="list-group-item d-flex justify-content-between">
						<span class={tarea.estado === true ? 'text-success cursor' : 'cursor'} on:click={() => actualizarTarea(tarea, i)}>
							<i class={tarea.estado === true ? 'fas fa-check-circle' : 'far fa-circle'} ></i>
						</span>
						 <h5>{ tarea.nombre }</h5>
						 <span class="cursor text-danger" on:click={() => deleteTarea(i)}>
							 <i class="fas fa-trash-alt"></i>
						 </span>
					</li>
					{/each}
				</ul>
			</div>
		</div>
	</div>
</main>

<style>
	.cursor{
		cursor: pointer;
	}
</style>