# DescargarAnimeAuto

## Aplicaciones utilizadas
* [Sonarr](https://github.com/MunchiA/DescargarAnimeAuto/edit/main/README.md#sonar) (Gestor de videos)
* [Jackett](https://github.com/MunchiA/DescargarAnimeAuto/edit/main/README.md#jackett) (Índice de torrents)
* [qbitTorrent](https://github.com/MunchiA/DescargarAnimeAuto/edit/main/README.md#qbittorrent) (Descargas por torrent)
# Configuración

## qbitTorrent

Este paso es el más facil, ya que solo hay que instalarlo y no hace falta hacer ninguna configuración extraña.
Lo que hay que tener en cuenta y recordar es:
* Saber la IP junto al puerto donde tenemos **qbitTorrent**.
* Tener a mano el usuario y la contraseña.
  
Con esto ya podriamos pasar al siguiente paso.

## Jackett
Instalamos **Jackett**.

Una vez ya lo tenemos instalado, accedemos al panel web de jackett, seleccionamos **Add Indexer** y buscamos **Nyaa.si** y le damos al boton verde para añadirlo <img src="https://github.com/user-attachments/assets/cd201849-fb61-4b64-9c25-8e7a650966d5" width="20" />.
![Configured Indexers](https://github.com/user-attachments/assets/70c6deb4-dfa8-402d-a3db-a3e4bf0b48f7)

Una vez agregado nos tiene que saler en el menú de abajo.

![Nyaa introducido](https://github.com/user-attachments/assets/39d52cfe-d37e-42b3-944c-5afc5915c386)

Luego procedemos a configurar el indexer con esta configuración y pulsamos el botón de **OK** para guardar la configuración.

![Menu Nyaa](https://github.com/user-attachments/assets/8b6ef5b7-6cd0-4b7a-99a2-bddd24190038)

Nos aseguramos de haber guardado y para comprobar que funciona le damos al botón de **Test** para probar la conectividad ![image](https://github.com/user-attachments/assets/ae458d50-850f-4568-8d5f-65811ebcf8fa)

Si nos sale con el **tick verde** significa que lo hemos configurado correctamente! ![Test Nya](https://github.com/user-attachments/assets/a8545fdc-f729-455f-a642-d0be44a8a897)

Ahora tenemos que ir a **Sonarr** para añadirlo como **Indexer**.

## Sonar

Una vez que hemos instalado correctamente **Sonarr** tenemos que añadir la/las carpetas de root que serán las que utilizaremos, hay que darle al botón de **Add Root Folder** y seleccionamos las que queramos. Una vez hecho nos tienen que salir en pantalla las que hemos añadido.

![Root Folder](https://github.com/user-attachments/assets/2ba708d5-cee5-40ce-8bab-54606199f693)

Ahora vamos a añadir un cliente para descargar, así que iremos a **Settings -> Download Clients**

Una vez dentro le daremos al + gigante para añadir la configuración.
Nos tendria que quedar algo así 

![qbitTorrent Config](https://github.com/user-attachments/assets/724ec6b1-c764-4c8a-8d83-744331ba7cb3)

Es recomendable darle al botón de **Test** para ver si tenemos conectividad con el programa de Torrent.

Ahora procedemos a añadir el **Indexer** que creamos anteriormente con *Jackett*

Tenemos que ir a **Settings -> Indexers**

Hay que darle al + gigante para añadir una entrada nueva.

Ahora tendriamos que configurarlo con nuestros datos, así que hay que volver a **Jackett** para consguir estos datos, que son:
* **URL**
  * Tenemos que darle al botón **Copy Torznab Feed**. ![URL Torznab](https://github.com/user-attachments/assets/36ba0b23-c018-42d0-a398-36c46335fa2d)
* **API Key**
  * Arriba a la derecha de la aplicación de **Jackett** tenemos la *API Key*.  ![API Key Jackett](https://github.com/user-attachments/assets/4fcbe879-7bea-434c-b713-6dc50d151f4b)

Así nos tendria que quedar una vez configurado ![Indexer Config](https://github.com/user-attachments/assets/3efa455f-0235-48f4-9dc0-9de268bb7b44)

### Configuraciones para descargar

Ahora ya tenemos todo configurado para descargar, pero nos falta lo más importante, que és descargar con el idioma que nosotros queramos.

En este caso nos tenemos que ir a **Settings -> Profiles**

El primer apartado de **Quality Profiles** es para la calidad en la que vamos a querer los videos descargados, aquí ya es elección de cada uno.

En el segundo apartado **Language Profiles** es donde tenemos que modificar un poco.

Para poder descargar con substitulos en español yo he creado un perfil con varios idiomas, que son **Italiano, Frances, Ingles, Japones y Español**. Esto es solo el principio, ya que ahora vamos a hacer una seleccion por **TAG** para especificar la descarga.

Tenemos que ir al apartado de abajo del todo **Release Profiles**

Aqui al crear uno, tendremos que ir modificando a nuestro gusto los campos de **Must Contain** y **Must Not Contain**

Esta es la configuración que tengo yo. 

![Release Profiles](https://github.com/user-attachments/assets/48797c4f-66fc-4b6e-967e-9d05e76ac3e9)

El campo de **Tags** es lo que nosotros ponemos cuando seleccionamos una serie para descargar, con solo poner uno de **anime** por ejemplo ya serviria.

## Agregar series

Ahora vamos a agregar una serie para comprobar si lo hemos configurado todo correctamente.

Nos tenemos que ir a **Series -> Add New** y buscamos una serie en mi caso lo probaré con esta. ![Add SAO](https://github.com/user-attachments/assets/86fd0145-0f99-4d75-996f-971c4518cc6c)

Al hacer click en la serie se nos abrirá un menú.

Si lo hemos configurado anteriormente, ya nos tendria que salir el **Root Folder** que hemos añadido seguido de una carpeta nueva que será la de la serie a descargar.

#### Configuración Serie
* **Monitor**: Este campo es para trackear los episodios, con poner **All Episodes** ya nos sirve.
* **Quality Profile**: Aquí seleccionaremos el perfil creado anteriormente para la calidad esperada el video (cuiado al poner mucha calidad, que igual no hay y no descarga nada).
* **Language Profile**: Seleccionamos el perfil creado (recomentable poner el ejemplo que he dado antes).
* **Series Type**: Tipo de serie, recomendado poner siempre **Anime**.
* **Season Folder**: Si queremos que se cree una carpeta de Temporada, por si hay varias.
* **Tags**: Aquí tendremos que poner el **Tag** que hemos puesto cuando hemos agregado el **Release Profile**

Ahora tenemos la opcion de que vaya buscando cuando le demos a agregar con la opción que hay abajo de **Start search for missing episodes**, que son los archivos que no tenemos descargados.

Procedemos a darle al botón verde para que vaya buscando los capítulos.  ![SAO agregar](https://github.com/user-attachments/assets/0220b3ea-0889-4b9f-9a1e-096f2acc8f22)

Ahora abajo a la izquierda podemos ver que ha salido un panel que está buscando los capitulos.

![Indexer Search](https://github.com/user-attachments/assets/4e8fba52-2558-4ea8-957f-f0747e62ab0d)

Ahora tendremos que meternos en la serie que hemos añadido y verificar que se estan descargando. 

En este caso podemos ver que se estando descargando los episodios correctamente.

![Descargando anime SAO](https://github.com/user-attachments/assets/a86b86db-c810-4040-a20e-826622b64243)

⚠️⚠️
**También nos podemos encontrar que en series antiguas no nos descarge con mucha velocidad o simplemente que no encuentre ningún archivo.**
⚠️⚠️

Ahora en el mismo panel de la serie, arriba, si seleccionamos **Manage Episodes** podemos ver que se han descargado los episodios y nos muestra su configuración como por ejemplo la ruta relativa en donde están, el tamaño...

## Licencia
Este tutorial está licenciado bajo la [Creative Commons Attribution-ShareAlike 4.0](https://creativecommons.org/licenses/by-sa/4.0/) (CC BY-SA 4.0).  

**Autor:** [Munchi](https://github.com/MunchiA).  

Si usas este trabajo, por favor da crédito adecuado, enlaza a la licencia, e indica si se realizaron cambios. Cualquier obra derivada debe distribuirse bajo la misma licencia.
