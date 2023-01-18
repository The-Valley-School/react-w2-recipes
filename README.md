# WORKSHOP 2: Libro de Recetas Online

En este ejercicio vamos a realizar un pequeño libro de recetas online como el que veis en la captura:

![Untitled](/assets/Untitled.png)

En la parte de la izquierda tendremos un formulario que nos permitirá crear nuevas recetas. Cuando creemos una receta, esta se añadirá en el listado central y se limpiará el formulario.

Si pulsamos en una de las recetas del listado podremos ver su detalle en la parte derecha, donde además podremos modificar los ingredientes, añadiendo o modificando:

![Untitled](/assets/Untitled%201.png)

Para el tema de los datos en este ejercicio vamos a partir de una api en local, recordemos que para ello debemos instalar json-server:

```jsx
npm i json-server
```

Crear una tarea en nuestro package.json para levantar el server:

```jsx
"start-fake-api": "json-server --watch fake-api.json --port 4000"
```

Y os dejamos por aquí los datos a indicar en el fake-api.json:

```json
{
  "recipes": [
    {
      "name": "Paella",
      "numPeople": 4,
      "imageUrl": "https://www.shutterstock.com/image-photo/classic-dish-spain-seafood-paella-600w-1879727512.jpg",
      "id": 1,
      "ingredients": [
        {
          "name": "Pimiento verde",
          "quantity": "2 uds"
        },
        {
          "name": "Pimiento rojo",
          "quantity": "2 uds"
        },
        {
          "name": "Langostino crudo",
          "quantity": "8 uds"
        },
        {
          "name": "Caldo pescado para paella",
          "quantity": "1 litro"
        },
        {
          "name": "Arroz",
          "quantity": "400 grs"
        }
      ]
    },
    {
      "name": "Tarta chocolate y galletas",
      "numPeople": 6,
      "imageUrl": "https://www.shutterstock.com/image-photo/homemade-chocolate-rolls-dessert-600w-368330465.jpg",
      "id": 2,
      "ingredients": [
        {
          "name": "Leche",
          "quantity": "500 ml"
        },
        {
          "name": "Chocolate para postres",
          "quantity": "450 grs"
        },
        {
          "name": "Paquetes de galletas",
          "quantity": "2 uds"
        },
        {
          "name": "Mantequilla",
          "quantity": "50 grs"
        }
      ]
    },
    {
      "name": "Pancake",
      "numPeople": "4",
      "imageUrl": "https://www.shutterstock.com/image-photo/sweet-homemade-stack-pancakes-butter-600w-791630443.jpg",
      "ingredients": [],
      "id": 3
    },
    {
      "name": "Brownie",
      "numPeople": "8",
      "imageUrl": "https://www.shutterstock.com/image-photo/pieces-fresh-chocolate-brownie-on-600w-1893866746.jpg",
      "ingredients": [
        {
          "name": "Mantequilla",
          "quantity": "200 grs"
        },
        {
          "name": "Chocolate",
          "quantity": "400 grs"
        }
      ],
      "id": 4
    },
    {
      "name": "Pollo Asado",
      "numPeople": "4",
      "imageUrl": "https://www.shutterstock.com/image-photo/homemade-chicken-rotisserie-thyme-lemon-600w-1574170006.jpg",
      "ingredients": [
        {
          "name": "Pollo entero crudo",
          "quantity": "1"
        }
      ],
      "id": 5
    }
  ]
}
```

Esta API soporta modificación de los elementos existentes haciendo uso de PUT, así que para añadir ingredientes o eliminarlos debemos hacer uso de este método, la url a la que debemos llamar será [http://localhost:4000/recipes](http://localhost:4000/recipes)/ID donde el ID será el de nuestro elemento a modificar.

Recuerda que en esta semana hemos trabajado con UseRef y deberíamos aplicarlo en todos los sitios que podamos, para así optimizar el pintado de nuestra aplicación, haciendo que solo se ejecute el render de nuestros componentes en los casos que sea necesario.

Debes también crear al menos 3 componentes, uno para cada zona de la app como se muestra en la imagen:

![Untitled](/assets/Untitled%202.png)
