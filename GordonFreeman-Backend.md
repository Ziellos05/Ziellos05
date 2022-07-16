## ** Gordon Freeman Backend queries per route **

1. Dishes

  - GET: Devuelve todos los platos, si es la ruta /:dishId devuelve ese plato específico

  - POST: Publica un plato nuevo, necesita autenticación y administrador

  - PUT: En la ruta /:dishId edita ese plato, necesita autenticación y administrador

  - DELETE: Elimina todos los platos, si es en la ruta /:dishId elimina ese plato específico, necesita autenticación y administrador

2. Favorites

  - GET: Devuelve todos los platos favoritos del user, necesita autenticación

  - POST: Agrega varios favoritos o un solo si es en la ruta /:dishId, necesita autenticación

  - DELETE: Elimina todos los favoritos del user, en la ruta /:dishId elimina solo ese favorito, necesita autenticación

3. Comments

  - GET: Devuelve todos los comentarios, en la ruta /:dishId devuelve los comentarios para el plato en cuestión 

  - POST: Agrega un comentario para un plato específico

  - PUT: En la ruta /:commentId, edita ese comentario

  - DELETE: Elimina todos los comentarios del usuario, si es en la ruta /:commentId, elimina el comentario específico

3. Promotions

  - GET: Devuelve todas las promociones

  - POST: Publica una promoción nueva, necesita autenticación y administrador

  - PUT: Edita una promoción, necesita autenticación y administrador

  - DELETE: Elimina una promoción, necesita autenticación y administrador

4. Leaders

  - GET: Retorna todos los líderes, en la ruta /:leaderId retorna el lider específico

  - POST: Publica un nuevo lider, necesita autenticación y administrador

  - PUT: En la ruta /:leaderId edita el lider en cuestión, necesita autenticación y administrador

5. Users

  - GET: Retorna a todos los usuarios si es admin, en la ruta /logout, cierra la sesión, en la ruta /checkJWTtoken revisa el token enviado con la inf del user

  - POST: En la ruta /signup agrega un nuevo user, en la ruta /login inicia sesión del usuario y envía un token JWT
