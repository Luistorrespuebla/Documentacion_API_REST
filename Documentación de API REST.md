![Logos Oficiales - Tecnológico Nacional de México](file:///C:/Users/Lenovo/AppData/Local/Temp/msohtmlclip1/01/clip_image002.png)

               **INSTITUTO TECNOLÓGICO MILPA ALTA II**

**Tema: Documentación de la creación de una API REST.**

**Asignatura: Programación web.**

**Profesor: Fernando Said Vásquez Telles.**

**Nombres: Luis Torres Puebla.**

Fecha: 04/12/2023

**Descripciones básicas de las tecnologías implementadas durante el desarrollo:**

**Postman:** es una herramienta de código abierto para crear, documentar y probar solicitudes HTTP. Es una herramienta muy popular entre los desarrolladores web y de API, ya que permite crear solicitudes de forma rápida y sencilla, y luego ver los resultados de esas solicitudes. Tiene una interfaz de usuario intuitiva que facilita la creación de solicitudes HTTP. También tiene una amplia gama de funciones que permiten probar y depurar solicitudes, como la posibilidad de guardar solicitudes, crear colecciones de solicitudes y ejecutar solicitudes en paralelo.

**Express:** es un marco de trabajo web ligero y sencillo de usar para Node.js. Es una de las opciones más populares para crear aplicaciones web y API REST con Node.js. Proporciona una API sencilla y fácil de aprender, que permite crear aplicaciones web y API REST rápidamente y fácilmente. También proporciona una amplia gama de funciones, como la posibilidad de manejar solicitudes HTTP, renderizar vistas y crear middleware.

**MongoDB:** es una base de datos NoSQL de documentos. Los documentos de MongoDB son objetos JSON que pueden contener cualquier tipo de datos, lo que los hace muy flexibles para almacenar diferentes tipos de datos. Es una base de datos escalable y eficiente, lo que la hace adecuada para aplicaciones web y API que necesitan manejar grandes volúmenes de datos.

**MongoDB Atlas:** es un servicio de base de datos MongoDB como servicio (PaaS) que proporciona una forma sencilla de crear, administrar y escalar bases de datos MongoDB. Ofrece una amplia gama de características, como la posibilidad de crear bases de datos en la nube, administrar usuarios y roles, y escalar bases de datos según sea necesario.

**Node.js:** es un entorno de ejecución de JavaScript multiplataforma que permite ejecutar código JavaScript fuera de un navegador web. Node.js es una herramienta muy popular para crear aplicaciones web y API REST. Es rápido, eficiente y escalable, lo que lo hace adecuado para aplicaciones que requieren un alto rendimiento.

**Mongosee:** es una biblioteca de JavaScript que proporciona una capa de abstracción para MongoDB. Mongosee facilita el acceso a los datos de MongoDB desde JavaScript. Proporciona una API sencilla y fácil de usar que permite acceder a los datos de MongoDB de forma similar a como se accede a los datos de una matriz.

**Creación del ambiente de desarrollo:**

Se descargo node.js desde la siguiente URL: [https://nodejs.org/en](https://nodejs.org/en).

Se creo una cuenta, en la siguiente URL, para usar mongoDB atlas en la nube: [https://www.mongodb.com/cloud/atlas/register](https://www.mongodb.com/cloud/atlas/register).

Se descargo la herramienta postman de la siguiente URL: [https://www.postman.com/downloads/](https://www.postman.com/downloads/).

Se creo una carpeta con el nombre del proyecto. La seleccionamos y le dio clic derecho para abrir la misma con la opción terminal. Una vez abierta la terminal, se escribió el siguiente comando: **npm init.** El comando init se utiliza para inicializar el proyecto con node.js. Al ejecutarse el comando se crea un archivo package. json. Posteriormente damos un enter y la terminal solicitara rellenar algunas opciones, estas pueden omitirse con una serie de pulsaciones sobre la tecla enter o en su defecto irse rellenando con forme se vaya avanzando.

![](file:///C:/Users/Lenovo/AppData/Local/Temp/msohtmlclip1/01/clip_image004.png)

Posteriormente se ingresó y ejecuto el comando code ., para abrir la carpeta con el editor de texto (visual studio code). Después se procedió a abrir una nueva terminal en el editor de código y escribió el siguiente comando: **npm i express mongoose** para instalar las dependencias express y mongoose en el proyecto. Es importante recordar que estas dependencias solo están incluidas en el proyecto.

Una vez finalizo la descarga, se ingresó el siguiente comando: **npm i -D nodemon.** El comando **npm i -D nodemon** instalo nodemon como dependencia en el proyecto Node.js.

**Configuración del ambiente de desarrollo:**

Se ingresó al archivo; package.json, para realizar los siguientes cambios:

Se agregaron dos scripts: **start** (inicia tu aplicación en modo de producción, ejecuta el comando node para iniciar tu aplicación con el archivo index.js como punto de entrada) y **dev** (inicia tu aplicación en modo de desarrollo, ejecuta el comando nodemon para iniciar tu aplicación con el archivo index.js como punto de entrada). Se ingreso el siguiente comando para iniciar el modo de desarrollo: **npm run dev.**

**Creación de la base de datos en la nube:**

Se abrio un navegador y se ingreso a la página de mongoDB Atlas, donde se creo un nuevo proyecto y se selecciono un nombre para el mismo, después se pulso en el boton crear base de datos para confimar la creación.

![](file:///C:/Users/Lenovo/AppData/Local/Temp/msohtmlclip1/01/clip_image009.png)

Las acciones mensionadas anteriormente me dirigieron a una nueva ventana, donde se selecciono la opcion free para crear una base de datos gratis y se confimo pulsando en el boton create. Posteriormente se nos direcciono a una nueva ventana donde se nos solicito crear; un usuario y contraseña, finalmente se confirmo pulsando en el boton create.

En la siguiente ventana se asigno la IP Address con el valor; 0.0.0.0/0, para tener acceso desde cualquier lugar, la descripcion es opcional,  se guardaron los cambios al pulsar sobre el boton; finish and close.

![](file:///C:/Users/Lenovo/AppData/Local/Temp/msohtmlclip1/01/clip_image011.png)

|   |
|---|
||
||![Rectángulo: esquinas redondeadas: 0.0.0.0/0](file:///C:/Users/Lenovo/AppData/Local/Temp/msohtmlclip1/01/clip_image012.png)|

 

  

**Creación de la conexión:**

En el editor de codigo, se creo una carpeta llamada database que contendra la conexión a mongoDB, dentro de ella se crearon los siguientes archivos; index.js y config.js. En el archivo config,js se realizaron los siguientes cambios; en la direccion de mongoose.connect se remplazo la palabra password por la contraseña que nosotros creamos y se le añadio; /agendaContactos, para crear una base de datos con ese nombre.

![](file:///C:/Users/Lenovo/AppData/Local/Temp/msohtmlclip1/01/clip_image014.png)

La dirección se tomo de mongoDB Atlas en la sección Overview de connect, al pulsar sobre el mismo se desplego una ventana con el **apartado I don't have MongoDB Compass installed** y de bajo aparecio la ruta que tomamos.



![](file:///C:/Users/Lenovo/AppData/Local/Temp/msohtmlclip1/01/clip_image020.png)

  

**Diseño de la lógica de programación:**

Se creo una carpeta llamada models, dentro de la misma se creó un archivo llamado contacto.js, el cual contiene el siguiente script:

![](file:///C:/Users/Lenovo/AppData/Local/Temp/msohtmlclip1/01/clip_image022.png)

Posteriormente se creó una carpeta llamada controllers, donde se definieron los controladores y las funciones para la manipulación de los datos integrados a la base de datos alojada en mongoDB atlas.

![](file:///C:/Users/Lenovo/AppData/Local/Temp/msohtmlclip1/01/clip_image024.png)

![](file:///C:/Users/Lenovo/AppData/Local/Temp/msohtmlclip1/01/clip_image026.png)Para brindarle un mayor orden al código, se separaron las funciones a la carpeta de controladores y en el archivo index.js se realizaron los siguientes cambios:

**Iniciar servidor:**

Se ingreso en la terminal de Visual Studio el comando; **npm run dev,** el cual inicializa el servidor en modo desarrollo.

Ingresamos a postman y dentro del programa pulsamos en el símbolo de más para crear una nueva colección de datos, posteriormente seleccione el tipo de posteo, el cual fue POST, posteriormente se ingresó la URL (localhost: 3001), en el apartado; body**,** se seleccionó la opción; raw, lo cual nos desplegara un apartado en el cual seleccionaremos el formato; JSON.

Se agrego un contacto en formato JSON, siguiendo la estructura del archivo; contacto.js, ubicado en la carpeta models. Se confirmo el ingreso de datos al pulsar el botón; send.

Se visualizo el contacto guardado cambiando el método: POST por el método: GET, pulsando sobre el botón; send, se ejecuta la instrucción.

![](file:///C:/Users/Lenovo/AppData/Local/Temp/msohtmlclip1/01/clip_image028.png)Para actualizar un contacto se cambió del método; GET al método: PUT, dejando la misma ruta, pero agregando el id del usuario que queremos actualizar, al ejecutar GET este mismo nos proporciona el id.

|   |
|---|
||
||![](file:///C:/Users/Lenovo/AppData/Local/Temp/msohtmlclip1/01/clip_image029.png)|

 

  

![](file:///C:/Users/Lenovo/AppData/Local/Temp/msohtmlclip1/01/clip_image031.png)Para eliminar un contacto cambiamos el método; PUT por DELETE, para eliminar un contacto se solicita id de contacto a eliminar, se agrega el id de contacto y confirmamos con el botón; send.

Para finalizar el servidor en la terminal de Visual Studio, se ingresa el siguiente comando; **crtl + c.**