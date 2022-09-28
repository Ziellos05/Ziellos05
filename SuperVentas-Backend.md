## ** Queries per route, this is my first released backend **

1. Users -> api/users
      Cancel changes

- GET: Retorna todos los usuarios, /:email retorna por el correo.

![Screenshot](https://raw.githubusercontent.com/Ziellos05/Ziellos05/main/img/1-getusers.png)

![Screenshot](https://raw.githubusercontent.com/Ziellos05/Ziellos05/main/img/1-useremail.png)

- POST: Agrega un usuario nuevo.

![Screenshot](https://raw.githubusercontent.com/Ziellos05/Ziellos05/main/img/1-users.png)

- PUT: /:email, edita al usuario específico.

![Screenshot](https://raw.githubusercontent.com/Ziellos05/Ziellos05/main/img/1-putemail.png)

- DELETE: /:email elimina al usuario específico.

![Screenshot](https://raw.githubusercontent.com/Ziellos05/Ziellos05/main/img/1-delemail.png)

2. Products -> api/products

- GET: Returna todos los productos en venta, /available retorna en stock, /:nameProduct retorna el producto específico.

- POST: Agrega un producto nuevo.

- PUT: /:id edita un producto específico.

- DELETE: /:id elimina el producto seleccionado.

3. Sales -> api/sales

- GET: Retorna todas las ventas, /:id retorna una venta específica.

- POST: Agrega una nueva venta.

- PUT: /:id edita una venta previa
