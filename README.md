# base_datos_c3_q2
Quiz corte 3 - Base de datos


```sql
-- Obtener de manera ordenada la lista de vistas y modulos a los que tiene acceso un rol en estado activo. 
SELECT 
    r.name AS rol,
    m.name AS nombre,
    m.path AS paquete
    v.name AS vista,
    v.path AS ruta
FROM
    role r 
    INNER JOIN role_module rm ON r.id = rm.role_id
    INNER JOIN module m ON rm.module_id = m.id
    INNER JOIN module_view mv ON m.id = mv.module_id
    INNER JOIN view v ON mv.view_id = v.id 
WHERE r.state = true
ORDER BY r.name
```
![Sin](img/sin.png)
![Con](img/con-data.png)