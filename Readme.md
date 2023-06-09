
## PRIMERA PRE-ENTREGA DE UN PROYECTO DE TIENDA:

## SE ESTÁ REQUIRIENDO LO SIGUIENTE:

- Desarrollar el servidor basado en Node.JS y express, que escuche en el puerto 8080 y disponga de dos grupos de rutas: /products y /carts. Dichos endpoints estarán implementados con el router de express, con las siguientes especificaciones: - ((HECHO))

- Para el manejo de productos, el cual tendrá su router en /api/products/ , configurar las siguientes rutas:
  - La ruta raíz GET / deberá listar todos los productos de la base. (Incluyendo la limitación ?limit del desafío anterior)  ((HECHO)).
  - La ruta GET /:pid deberá traer sólo el producto con el id proporcionado ((HECHO)).

- La ruta raíz POST / deberá agregar un nuevo producto con los campos:
  - id: Number/String (A tu elección, el id NO se manda desde body, se autogenera, como lo hemos visto desde los primeros entregables, asegurando que NUNCA se  repetirán los ids en el archivo).
  - title:String, ((HECHO))
  - description:String ((HECHO))
  - code:String ((HECHO))
  - price:Number ((HECHO))
  - status:Boolean ((HECHO))
  - stock:Number ((HECHO))
  - category:String v
  - thumbnails:Array de Strings que contenga las rutas donde están almacenadas las imágenes referentes a dicho producto. ((HECHO))
  - Status es true por defecto.

- Todos los campos son obligatorios, a excepción de thumbnails. 
  ((HECHO)). 

- El POST se puede hacer con Postman o mediante formulario HTML. 
  ((HECHO)).

- El campo thumbnails recibe un string, por los momentos no tiene implementado recibir varias  rutas de archivo para colocarlas en un arreglo.           

- La ruta PUT /:pid deberá tomar un producto y actualizarlo por los campos enviados desde body. NUNCA se debe actualizar o eliminar el id al momento de hacer dicha actualización. - ((HECHO)).

- La ruta DELETE /:pid deberá eliminar el producto con el pid indicado. -((HECHO)).

- Para el carrito, el cual tendrá su router en /api/carts/, configurar dos rutas:

  - La ruta raíz POST / deberá crear un nuevo carrito con la siguiente estructura:
     - Id:Number/String (A tu elección, de igual manera como con los productos, debes asegurar que nunca se dupliquen los ids y que este se autogenere).
     - products: Array vacío que contendrá objetos que representen cada producto - ((HECHO)).

  - La ruta GET /:cid deberá listar los productos que pertenezcan al carrito con el parámetro cid proporcionados. (((HECHO)).)

- La ruta POST  /:cid/product/:pid deberá agregar el producto al arreglo “products” del carrito seleccionado, agregándose como un objeto (((HECHO))) bajo el siguiente formato:

  - product: SÓLO DEBE CONTENER EL ID DEL PRODUCTO (Es crucial que no agregues el producto completo). ((HECHO)).
  - quantity: debe contener el número de ejemplares de dicho producto. ((HECHO)).
  - El producto, de momento, se agregará de uno en uno. ((HECHO)).
  - Además, si un producto ya existente intenta agregarse al producto, incrementar el campo quantity de dicho producto. - ((HECHO)).

- La persistencia de la información se implementará utilizando el file system, donde los archivos “products.json” y “carts.json”, respaldan la información. ((HECHO)).

- No es necesario realizar ninguna implementación visual, todo el flujo se puede realizar por Postman o por el cliente de tu preferencia ((HECHO)) Se realizó con formulario HTML solo se implementó método POST de  producto.

- Link al repositorio de Github con el proyecto completo, sin la carpeta de Node_modules. ((HECHO)).

## Sugerencias

- No olvides app.use(express.json()). ((HECHO)).
- No es necesario implementar multer. ((HECHO)) (Esta instalado Multer para procesar el almacenado de la imagen pero no esta implementado aun).
