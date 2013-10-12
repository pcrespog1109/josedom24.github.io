---
layout: index

title: Servicios de Red e Internet
tagline: CFGS ASIR
---
### Ejercicio: Mapear URL a ubicaciones de un sistema de ficheros

1) Crea un nuevo host virtual que es accedido con el nombre 
www.mapeo.com, cuyo [DocumentRoot](http://httpd.apache.org/docs/2.2/mod/core.html#documentroot) sea /srv/mapeo. En este host virtual no se va ejecutar ningun script CGI, no es necesario que se visualice la documentación del sistema.

2) [Alias](http://httpd.apache.org/docs/2.2/mod/mod_alias.html#alias): 
Crea un alias en el host virtual default, que mi permita entrar en la 
URL http://localhost/documentos y visualice los ficheros del 
/home/usuario/Documentos. En la sección Directory... pon las mismas directivas que tiene la sección Directory del directorio DocumentRoot.

3) [Options](http://httpd.apache.org/docs/2.2/mod/core.html#options): Determina para que sirven las siguientes opciones de funcionamieno:

* All
* FollowSymLinks
* Indexes
* MultiViews
* SymLinksOwnerMatch
* ExecCGI

Detemina como funciona si delante de las opciones pongo el signo + o -.

   3.1) Crea un enlace directo dentro de /home/usuario/document y comprueba si es posible seguirlo. Cambia las opciones del directorio para que no siga los enlaces símbolicos.

   3.2) Deshabiliata la opción de que se listen los archivos 
   existentes en la carpeta cuando no existe un fichero definido en la 
   directiva [DirectoryIndex](http://httpd.apache.org/docs/2.2/mod/mod_dir.html#directoryindex).

   3.3) MultiViews: Para saber más sobre el negociado de contenido: 
   [http://httpd.apache.org/docs/2.2/content-negotiation.html](http://httpd.apache.org/docs/2.2/content-negotiation.html). Siguiendo el ejemplo de esta página realiza un fichero de bienvenida en español e inglés y compruba como se visualiza.

4) Usando la directiva [Redirect](http://httpd.apache.org/docs/2.2/mod/mod_alias.html#redirect) realiza una redirección, que permita que caundo entre a tu servidor http://nombre_servidor, salte a http://nombre_servidor/web

5) Con la directiva  se puede crear [Respuesta de error personalizadas](http://httpd.apache.org/docs/2.2/custom-error.html). Todo esto se puede llevar a cabo en el fichero /etc/apache2/conf.d/localized-error-pages. Después de leer sobre el tema realiza los siguientes ejercicios.

> 5.1) Cuando no se encuentre una página (error 404) por un mensje de error.

> 5.2) Crea un alias llamado a error que corresponda a /srv/mapeo/error. Dentro de ese directorio crea páginas personalizadas para visualizar cuando se produzca un error 404 y cuando se tenga un forbidden (403). Configura el sistema para que se redireccione a estas páginas cuando se produce un error.

> 5.3) Descomenta en el fichero localized-error-pages las líneas adecuadas para tener los mensajes de error traducidos a los diferentes idiomas. Para que funcione tienes que hacer dos cosas:

    * Activar el módulo include.
    * Si quieres los mensajes en español modifica adecuadamente la directiva LanguagePriority del módulo negotiation.


[Volver](index)