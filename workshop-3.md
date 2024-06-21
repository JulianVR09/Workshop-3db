1. Libros:
| ID_Libro | Titulo                | Autor1                | Autor2                | Autor3                | Genero1        | Genero2       |
|----------|-----------------------|-----------------------|-----------------------|-----------------------|----------------|---------------|
| 1        | Don Quijote           | Miguel de Cervantes   | NULL                  | NULL                  | Novela         | Clásico       |
| 2        | Cien Años de Soledad  | Gabriel García Márquez| NULL                  | NULL                  | Realismo Mágico| Novela        |
| 3        | La Odisea             | Homero                | NULL                  | NULL                  | Épica          | Clásico       |
| 4        | Good Omens            | Neil Gaiman           | Terry Pratchett       | NULL                  | Fantasía       | Comedia       |

1NF

Libros:
| ID_Libro | Titulo                | Autor1                | Genero1        |
|----------|-----------------------|-----------------------|----------------|
| 1        | Don Quijote           | Miguel de Cervantes   | Novela         |
| 2        | Don Quijote           | Miguel de Cervantes   | Clásico        |
| 3        | Cien Años de Soledad  | Gabriel García Márquez| Realismo Mágico|
| 4        | Cien Años de Soledad  | Gabriel García Márquez| Novela         |
| 5        | La Odisea             | Homero                | Épica          |
| 6        | La Odisea             | Homero                | Clásico        |
| 7        | Good Omens            | Neil Gaiman           | Fantasía       |
| 8        | Good Omens            | Terry Pratchett       | Comedia        |

2. Pedidos:
| ID_Pedido | ID_Producto | Cliente          | Dirección             | Producto      | Precio |
|-----------|-------------|------------------|-----------------------|---------------|--------|
| 1         | 101         | Juan Pérez       | Calle 123, Ciudad A   | Camiseta      | 20.00  |
| 1         | 102         | Juan Pérez       | Calle 123, Ciudad A   | Pantalones    | 25.00  |
| 2         | 103         | Ana Gómez        | Avenida 456, Ciudad B | Zapatos       | 50.00  |
| 2         | 101         | Ana Gómez        | Avenida 456, Ciudad B | Camiseta      | 20.00  |

2NF

Clientes
| ID_Cliente | Cliente          | Dirección             |
|------------|------------------|-----------------------|
| 1          | Juan Pérez       | Calle 123, Ciudad A   |
| 2          | Ana Gómez        | Avenida 456, Ciudad B |


Productos:
| ID_Producto | Producto      | Precio |
|-------------|---------------|--------|
| 101         | Camiseta      | 20.00  |
| 102         | Pantalones    | 25.00  |
| 103         | Zapatos       | 50.00  |

Pedidos:
| ID_Pedido | ID_Producto | ID_Cliente       |
|-----------|-------------|------------------|
| 1         | 101         | 1                |
| 2         | 102         | 1                |
| 3         | 103         | 2                |
| 4         | 101         | 2                |

3. Consultas:
| ID_Consulta | ID_Paciente | Paciente         | Doctor       | Especialidad |
|-------------|-------------|------------------|--------------|--------------|
| 1           | 100         | Juan Pérez       | Dr. Smith    | Cardiología  |
| 2           | 101         | Ana Gómez        | Dr. Johnson  | Neurología   |
| 3           | 100         | Juan Pérez       | Dr. Smith    | Cardiología  |
| 4           | 102         | Maria López      | Dr. Lee      | Pediatría    |

3NF:

Pacientes:
| ID_Paciente | Paciente         |
|-------------|------------------|
| 100         | Juan Pérez       |
| 101         | Ana Gómez        |
| 102         | Maria López      |

Doctores:
| ID_Doctor   | Doctor       | Especialidad |
|-------------|--------------|--------------|
| 1           | Dr. Smith    | Cardiología  |
| 2           | Dr. Johnson  | Neurología   |
| 3           | Dr. Lee      | Pediatría    |

Consultas:
| ID_Consulta | ID_Paciente | ID_Doctor  |
|-------------|-------------|------------|
| 1           | 100         | 1          |
| 2           | 101         | 2          |
| 3           | 100         | 1          |
| 4           | 102         | 3          |

4. Proyectos:
| ID_Proyecto | Nombre_Proyecto    | ID_Profesor | Nombre_Profesor |
|-------------|--------------------|-------------|------------------|
| 1           | IA Avanzada        | 101         | Dr. Smith        |
| 2           | Robótica           | 102         | Dr. Johnson      |
| 3           | IA Aplicada        | 101         | Dr. Smith        |
| 4           | Redes de Computo   | 103         | Dr. Lee          |

BCNF

Proyectos:
| ID_Proyecto | Nombre_Proyecto    |
|-------------|--------------------|
| 1           | IA Avanzada        |
| 2           | Robótica           |
| 3           | IA Aplicada        |
| 4           | Redes de Computo   |

Profesores:
| ID_Profesor | Nombre_Profesor  |
|-------------|------------------|
| 101         | Dr. Smith        |
| 102         | Dr. Johnson      |
| 103         | Dr. Lee          |

IDs:
| ID_Proyecto | ID_Profesor |
|-------------|-------------|
| 1           | 101         |
| 2           | 102         |
| 3           | 101         |
| 4           | 103         |

5. Empleado_Habilidades:
| ID_Empleado | Nombre_Empleado | Habilidad                |
|-------------|-----------------|--------------------------|
| 1           | Juan Pérez      | Programación             |
| 1           | Juan Pérez      | Diseño de Bases de Datos |
| 2           | Ana Gómez       | Programación             |
| 2           | Ana Gómez       | Análisis de Datos        |

4NF:
Empleados:
| ID_Empleado | Nombre_Empleado |
|-------------|-----------------|
| 1           | Juan Pérez      |
| 2           | Ana Gómez       |

Habilidades:
| ID_Empleado | Habilidad                |
|-------------|--------------------------|
| 1           | Programación             |
| 1           | Diseño de Bases de Datos |
| 2           | Programación             |
| 2           | Análisis de Datos        |

5.1. Contratos:
| ID_Proyecto | ID_Empleado | ID_Proveedor |
|-------------|-------------|--------------|
| 1           | 1           | 1001         |
| 1           | 2           | 1002         |
| 2           | 1           | 1001         |

Proyectos:
| ID_Proyecto | Nombre_Proyecto  |
|-------------|------------------|
| 1           | Proyecto A       |
| 2           | Proyecto B       |

Proyecto_Empleado:
| ID_Proyecto | ID_Empleado |
|-------------|-------------|
| 1           | 1           |
| 1           | 2           |
| 2           | 1           |

Proyecto_Proveedor:
| ID_Proyecto | ID_Proveedor |
|-------------|--------------|
| 1           | 1001         |
| 2           | 1001         |
| 1           | 1002         |

6. Ventas:
| ID_Venta | Cliente        | Producto     | Precio | Fecha       |
|----------|----------------|--------------|--------|-------------|
| 1        | Juan Pérez     | Camiseta     | 20.00  | 2023-01-01  |
| 2        | Ana Gómez      | Pantalones   | 25.00  | 2023-01-02  |
| 3        | Juan Pérez     | Camiseta     | 20.00  | 2023-01-03  |


Vida real:

Clientes:
| ID_Cliente | Cliente        |
|------------|----------------|
| 1          | Juan Pérez     |
| 2          | Ana Gómez      |

Productos:
| ID_Producto | Producto     | Precio |
|-------------|--------------|--------|
| 1           | Camiseta     | 20.00  |
| 2           | Pantalones   | 25.00  |

Ventas:
| ID_Venta | ID_Cliente     | ID_Producto  | Fecha       |
|----------|----------------|--------------|-------------|
| 1        | 1              | 1            | 2023-01-01  |
| 2        | 2              | 2            | 2023-01-02  |
| 3        | 1              | 1            | 2023-01-03  |


7. Inventarios:
| ID_Inventario | Producto         | Cantidad_Ubicaciones           |
|---------------|------------------|--------------------------------|
| 1             | Tornillos        | A1:100, B2:200                 |
| 2             | Clavos           | A3:150, B4:100                 |

Atomicidad vida real:

Inventarios:
| ID_Inventario | Producto         |
|---------------|------------------|
| 1             | Tornillos        |
| 2             | Clavos           |

Detalles de inventarios:
| ID_Inventario | Ubicación        | Cantidad           |
|---------------|------------------|--------------------|
| 1             | A1               | 100                |
| 1             | B2               | 200                |
| 2             | A3               | 150                |
| 2             | B4               | 100                |