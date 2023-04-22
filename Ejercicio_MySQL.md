Practica Modelo Relacional.

La siguiente practica evalua su conocimiento de consultas con Modelo Relacional.
Como enviar sus respuesta.

    Debe crear este archivo en su fork con el mismo nombre.
    Debe copiar el contenido.
    Debe comenzar a resolver las consultas.
    Debe guardar el progreso en cada paso, puede cambiar la respuesta las veces que quiera, pero debe guardar el progreso cada vez. (Muy importante).

Guardar progreso.

Para guardar su progreso cada vez que termine un ejercicio, o cambie una consulta. Ejecuta lo siguiente en un nuevo terminal:

git add .
git commit -m "Enviando progreso"
git push

Ejercicios:

    Listar la cantidad de tiendas por ciudad.

Salida:

+---------+------------+-------------+
| city_id | city       | store_count |
+---------+------------+-------------+
|     300 | Lethbridge |           1 |
|     576 | Woodridge  |           1 |
+---------+------------+-------------+

Respuesta:

-- Su respuesta aqui:

SELECT c.city_id, c.city, COUNT(s.store_id) AS store_count FROM city c
JOIN address a ON c.city_id = a.city_id
JOIN store s ON a.address_id = s.address_id
GROUP BY c.city_id;

    Listar la cantidad de películas que se hicieron por lenguaje.

Salida:

+-------------+----------+------------+
| language_id | language | film_count |
+-------------+----------+------------+
|           1 | English  |       1000 |
|           2 | Italian  |          0 |
|           3 | Japanese |          0 |
|           4 | Mandarin |          0 |
|           5 | French   |          0 |
|           6 | German   |          0 |
+-------------+----------+------------+

Respuesta:

-- Su respuesta aqui:

SELECT l.language_id, l.name as language, COUNT(f.film_id) AS film_count FROM language l
LEFT JOIN film f ON l.language_id = f.language_id
GROUP BY l.language_id, l.name;

    Seleccionar todos los actores que participaron mas de 35 peliculas.

Salida:

+----------+------------+-----------+------------+
| actor_id | first_name | last_name | film_count |
+----------+------------+-----------+------------+
|       23 | SANDRA     | KILMER    |         37 |
|       81 | SCARLETT   | DAMON     |         36 |
|      102 | WALTER     | TORN      |         41 |
|      107 | GINA       | DEGENERES |         42 |
|      181 | MATTHEW    | CARREY    |         39 |
|      198 | MARY       | KEITEL    |         40 |
+----------+------------+-----------+------------+
6 rows in set (0.01 sec)

Respuesta:

-- Su respuesta aqui:

SELECT ...

    Mostrar el listado de los 10 de actores que mas peliculas realizó en la categoria Comedy.

Salida:

+----------+------------+-----------+-------------------+
| actor_id | first_name | last_name | comedy_film_count |
+----------+------------+-----------+-------------------+
|      196 | BELA       | WALKEN    |                 6 |
|      143 | RIVER      | DEAN      |                 5 |
|      149 | RUSSELL    | TEMPLE    |                 5 |
|       82 | WOODY      | JOLIE     |                 4 |
|      127 | KEVIN      | GARLAND   |                 4 |
|       58 | CHRISTIAN  | AKROYD    |                 4 |
|       24 | CAMERON    | STREEP    |                 4 |
|      129 | DARYL      | CRAWFORD  |                 4 |
|       83 | BEN        | WILLIS    |                 4 |
|       37 | VAL        | BOLGER    |                 4 |
+----------+------------+-----------+-------------------+

Respuesta:

-- Su respuesta aqui:

SELECT ...

    Obtener la lista de actores que NO han participado en ninguna película de categoría "Comedy":

Salida:

+----------+------------+-------------+
| actor_id | first_name | last_name   |
+----------+------------+-------------+
|        3 | ED         | CHASE       |
|        6 | BETTE      | NICHOLSON   |
|        7 | GRACE      | MOSTEL      |
|        8 | MATTHEW    | JOHANSSON   |
|        9 | JOE        | SWANK       |
... Se corta por longitud
|      189 | CUBA       | BIRCH       |
|      190 | AUDREY     | BAILEY      |
|      195 | JAYNE      | SILVERSTONE |
|      200 | THORA      | TEMPLE      |
+----------+------------+-------------+

53 filas total

Respuesta:

-- Su respuesta aqui:

SELECT ...
