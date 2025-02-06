<script>
</script>

<div class="content">
	<!-- Seu conteúdo aqui -->
	<h1>Bem-vindo ao meu site</h1>
	<p>Conteúdo da página...</p>
</div>

<div class="background-container">
	<img src="/fundo.jpg" alt="Imagem de fundo" class="background-image" />
</div>

<style>
	.background-container {
		position: relative;
		width: 100%;
		height: 500px; /* Ajuste o tamanho conforme necessário */
		overflow: hidden;
	}

	.background-image {
		width: 100%;
		height: auto;
		position: absolute;
		top: 0;
		left: 0;
		z-index: -1; /* Garante que a imagem não sobreponha o conteúdo */
	}

	/* Estilos para o conteúdo abaixo da imagem */
	.content {
		padding: 20px;
	}
</style>
