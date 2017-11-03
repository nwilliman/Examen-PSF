<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>PSF-Examen</title>
	<script type="text/javascript" src="C:\Users\LosWilly\Downloads\jquery-3.2.1.js"></script>
</head>
<body>
	<form id="form" method="post" enctype="multipart/form-data" >
		Ingrese su nombre: <input type="text" name="name" id="name"><br>
		Ingrese su apellido: <input type="text" name="lastname" id="lastname"><br>
		Ingrese su mail: <input type="text" name="email" id="email"><br>
		Foto: <input type="file" name="image" id="image"><br>
		<input type="submit" value="Enviar" id="enviar" name="enviar">
		<div id="respuesta" name="respuesta"></div>
	</form>
	<script>
		$("#form").submit(function(event){
			var formObj = $(this);
			var formData = new FormData(this);
			$.ajax({
				url:"http://servicio.psf-it.com.ar/servicio.php",
				type: "POST",
				data: formData,
				mimeType:"multipart/form-data",
				contentType: false,
        		cache: false,
        		processData:false,
				success: function(resultado){
					$("#respuesta").html(resultado);
				}
			})
		});
	</script>
</body>
</html>
