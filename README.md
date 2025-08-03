-- create a table 
CREATE TABLE usuario ( 
  nombres VARCHAR NOT NULL, 
  doc_iden INT PRIMARY KEY, 
  apellidos VARCHAR NOT NULL, 
  nombre_us VARCHAR NOT NULL, 
  direccion TEXT NOT NULL, 
  correo TEXT NOT NULL, 
  contraseña TEXT NOT NULL, 
  telefono VARCHAR NOT NULL 
); 
 
CREATE TABLE rol ( 
  cod_rol INT PRIMARY KEY, 
  nombre_rol VARCHAR NOT NULL, 
  descripcion TEXT NOT NULL, 
  permisos TEXT NOT NULL 
); 
 
CREATE TABLE ganado ( 
  cod_res INT PRIMARY KEY, 
  raza VARCHAR NOT NULL, 
  estado_salud VARCHAR NOT NULL, 
  estado_repro VARCHAR NOT NULL, 
  fecha_naci DATE NOT NULL, 
  peso VARCHAR NOT NULL, 
  origen VARCHAR NOT NULL 
); 
 
CREATE TABLE vacunaciones ( 
  cod_vacun INT PRIMARY KEY, 
  fecha DATE NOT NULL, 
  tipo_vacuna VARCHAR NOT NULL, 
  observaciones VARCHAR NOT NULL 
); 
 
CREATE TABLE reproduccion ( 
  cod_evento INT PRIMARY KEY, 
  tipo_evento VARCHAR NOT NULL, 
  fecha_evento DATE NOT NULL, 
  cod_pareja INT NOT NULL, 
  observaciones VARCHAR NOT NULL 
); 
 
CREATE TABLE alimentacion ( 
  cod_alimen INT PRIMARY KEY, 
  tipo_alimen VARCHAR NOT NULL, 
  cantidad VARCHAR NOT NULL, 
  responsable VARCHAR NOT NULL, 
  fecha DATE NOT NULL 
); 
 
CREATE TABLE raciones_sugueridas ( 
  cod_recion INT PRIMARY KEY, 
  peso_actual VARCHAR NOT NULL, 
  edad DATE NOT NULL, 
  cantidad_sugue VARCHAR NOT NULL, 
  veterinario VARCHAR NOT NULL, 
  fecha DATE NOT NULL 
); 
 
CREATE TABLE produccion ( 
  cod_produc INT PRIMARY KEY, 
  tipo_produc VARCHAR NOT NULL, 
  fecha DATE NOT NULL, 
  cantidad VARCHAR NOT NULL 
); 
 
CREATE TABLE inventario ( 
  cod_item INT PRIMARY KEY, 
  tipo VARCHAR NOT NULL, 
  nombre VARCHAR NOT NULL, 
  cantidad INT NOT NULL, 
  ubicacion VARCHAR NOT NULL, 
  estado VARCHAR NOT NULL, 
  motivo VARCHAR NOT NULL, 
  destino VARCHAR NOT NULL, 
  fecha_ingre DATE NOT NULL, 
  fecha_salid DATE NOT NULL, 
  responsable VARCHAR NOT NULL 
); 
 
CREATE TABLE novedades_inventario ( 
  cod_noved INT PRIMARY KEY, 
  tipo_noved VARCHAR NOT NULL, 
  fecha DATE NOT NULL, 
  descripcion VARCHAR NOT NULL, 
  evidencia TEXT NOT NULL, 
registrada_por VARCHAR NOT NULL 
); 

CREATE TABLE facturas ( 
cod_factu INT PRIMARY KEY, 
metodo_pago VARCHAR NOT NULL, 
fecha_emi DATE NOT NULL, 
monto_pagado VARCHAR NOT NULL 
); 

CREATE TABLE ventas ( 
cod_venta INT PRIMARY KEY, 
cliente VARCHAR NOT NULL, 
cantidad VARCHAR NOT NULL, 
precio_uni VARCHAR NOT NULL, 
total VARCHAR NOT NULL, 
fecha_emi DATE NOT NULL 
);

-- Usuario
SELECT 
  doc_iden           AS documento_identidad,
  nombres            AS nombres_personales,
  apellidos          AS apellido_personales,
  nombre_us          AS nombre_de_usuario,
  direccion          AS ubicacion,
  correo             AS correo_electronico,
  contraseña         AS clave,
  telefono           AS telefono_contacto
FROM usuario;

-- Rol
SELECT
  cod_rol            AS id_rol,
  nombre_rol         AS denominacion_rol,
  descripcion        AS detalle_rol,
  permisos           AS privilegios
FROM rol;

-- Ganado
SELECT
  cod_res            AS id_res,
  raza               AS tipo_raza,
  estado_salud       AS condicion_salud,
  estado_repro       AS condicion_reproductiva,
  fecha_naci         AS fecha_nacimiento,
  peso               AS masa,
  origen             AS procedencia
FROM ganado;

-- Vacunaciones
SELECT
  cod_vacun          AS id_vacunacion,
  fecha              AS fecha_aplicacion,
  tipo_vacuna        AS vacuna,
  observaciones      AS comentarios
FROM vacunaciones;

-- Reproducción
SELECT
  cod_evento         AS id_evento,
  tipo_evento        AS categoria_evento,
  fecha_evento       AS fecha,
  cod_pareja         AS pareja_id,
  observaciones      AS comentarios
FROM reproduccion;

-- Alimentación
SELECT
  cod_alimen         AS id_alimentacion,
  tipo_alimen        AS categoria_alimento,
  cantidad           AS volumen,
  responsable        AS encargado,
  fecha              AS fecha_entrega
FROM alimentacion;

-- Raciones sugeridas
SELECT
  cod_recion         AS id_racion,
  peso_actual        AS peso_presente,
  edad               AS nacimiento,
  cantidad_sugue     AS cantidad_recomendada,
  veterinario        AS medico_veterinario,
  fecha              AS fecha_recomendacion
FROM raciones_sugueridas;

-- Producción
SELECT
  cod_produc         AS id_produccion,
  tipo_produc        AS categoria_producto,
  fecha              AS fecha_registro,
  cantidad           AS volumen_generado
FROM produccion;

-- Inventario
SELECT
  cod_item           AS id_item,
  tipo               AS categoria_item,
  nombre             AS denominacion_item,
  cantidad           AS stock,
  ubicacion          AS localizacion,
  estado             AS condicion,
  motivo             AS razon,
  destino            AS destino_final,
  fecha_ingre        AS fecha_entrada,
  fecha_salid        AS fecha_salida,
  responsable        AS responsable_registro
FROM inventario;

-- Novedades de inventario
SELECT
  cod_noved          AS id_novedad,
  tipo_noved         AS categoria_novedad,
  fecha              AS fecha_registro,
  descripcion        AS detalle_novedad,
  evidencia          AS pruebas,
  registrada_por     AS usuario_registro
FROM novedades_inventario;

-- Facturas
SELECT
  cod_factu          AS id_factura,
  metodo_pago        AS forma_pago,
  fecha_emi          AS fecha_emision,
  monto_pagado       AS valor_pagado
FROM facturas;

-- Ventas
SELECT
  cod_venta          AS id_venta,
  cliente            AS nombre_cliente,
  cantidad           AS cantidad_vendida,
  precio_uni         AS precio_unitario,
  total              AS valor_total,
  fecha_emi          AS fecha_emision
FROM ventas;
