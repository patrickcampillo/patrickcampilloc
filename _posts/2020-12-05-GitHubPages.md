---
layout: post
author: Patrick
---
<b>En este post explicaré como alojar nuestra web personal en GitHub Pages.</b>
</br>
1. Crear nuestro repositorio en GitHub utilizando la siguiente sintaxis: "tu-nombre.github.io".</br>
<img src="assets/img/githubpages/1.png" alt="Primer paso"> </br>
2. Ahora deberemos clonar este repositorio en nuestro equipo local. En el lugar que deseemos, en mi caso cree la carpeta github para facilitar su identificación. Mediante el comando <b>"git clone [url de nuestro repositorio]"</b>.</br>
<img src="assets/img/githubpages/2.png" alt="Segundo paso"> </br>
3. Una vez clonado podremos crear, editar, mover y eliminar los archivos que deseemos. Como ejemplo, crearé un archivo <b>"index.html"</b> para mostrar el funcionamiento de GitHub Pages.</br>
<img src="assets/img/githubpages/3.png" alt="Tercer paso"> </br>
4. Finalmente, tendremos que subir el archivo modificado a nuestro repositorio de GitHub. Para esto utilizaremos los siguientes comandos: 
<ul>
    <li><b>git add --all, indicamos que queremos añadir a nuestro repositorio todo lo que hay en el reppositorio clonado.</b></li>
    <li><b>git commit -m "Initial commit"</b>, mediante este comando guardaremos las modificaciones indicando la razón mediante un pequeño comentario.</li>
    <li><b>git push -u origin master</b>, utilizando este comando subiremos los archivos, tras ejecutarlo nos pedriá nuestras credenciales de GitHub por seguridad.</li>
</ul></br>
<img src="assets/img/githubpages/4.png" alt="Cuarto paso"> </br>
Y comprobaremos que todo ha salido de forma correcta, introduciendo la dirección de nuestro repositorio en nuestro buscador.</br>
<img src="assets/img/githubpages/5.png" alt="Comprobación">