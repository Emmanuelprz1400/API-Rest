# API Rest

### Hay dos formas de consumir una API en JavaScript:

- #### Fetch API
- #### Biblioteca Axios 

## Fetch API:
La API Fetch proporciona una interfaz para obtener recursos (incluso a través de la red). Parecerá familiar a quien sea que haya usado `XMLHttpRequest`, pero proporciona un conjunto de características más potentes y flexible.
En pocas palabras, la Fetch API es una alternativa moderna que nos permite interactuar con APIs y obtener los datos a nuestra aplicación, de una forma parecida a lo hacíamos con AJAX pero de una manera mucho más sencilla.

## Pasos a seguir: 
1. Las interfaces genéricas de Headers, Request, and Response proporcionan coherencia, mientras que las promesas permiten un encadenamiento más fácil y async/await sin callbacks.
2. El único parámetro requerido de fetch() es una url. El método por defecto en este caso es GET.
```
Fetch(‘url‘)
````
3. El Segundo parámetro es opcional, en sí recibe parámetros extras acerca del tipo de petición que vamos hacer, si queremos enviar datos, bajo qué tipo va a estar encodeado, si vamos a enviar algún tipo de headers (dependiendo de cómo este configurado el servidor
```
Fetch(‘url ‘, {
    method: (‘GET/POST/PUT/DELETE ‘,        //optional
    headers: {                              //optional
        Content-Type ‘: application/json ‘  //optional
        ...
    },
    body: formData                          //optional
```

## ¿Cómo hacer un GET utlizando API Fetch?
El método **GET** se usa para recuperar datos del servidor. Este es un método de solo lectura, por lo que no tiene riesgo de mutar o corromper los datos.
```
fetch('https://jsonplaceholder.typicode.com/users')
      .then(response => response.json())
      .then(json => console.log(json))
```
## Cómo hacer un POST utlizando API Fetch?
El método **POST** envía datos al servidor y crea un nuevo recurso.
```
fetch('https://jsonplaceholder.typicode.com/todos', {
            method: 'POST',
            body: JSON.stringify({
                name: "Emmanuel",
                surname: "Pérez"
            }),
            headers: {
                "Content-type": "application/json"
            })
      .then(response => response.json())
      .then(json => console.log(json))
```

## ¿Cómo hacer un PUT utilizando la API Fetch?
El método **PUT** se usa con mayor frecuencia para actualizar un recurso existente.
```
fetch('https://jsonplaceholder.typicode.com/todos', {
            method: 'PUT',
            body: JSON.stringify({
                id: 1,             
                name: "Emmanuel",
                surname: "Pérez"
            }),
            headers: {
                "Content-type": "application/json"
            })
      .then(response => response.json())
      .then(json => console.log(json))
```

## ¿Cómo hacer un DELETE utilizando la API Fetch?
El método **DELETE** se usa para eliminar un recurso.
```
fetch('https://jsonplaceholder.typicode.com/users/id', {
    method: ‘DELETE’
});
```

