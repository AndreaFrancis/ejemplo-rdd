LEEME
=====

Acta realizada en la reunión del 22 de noviembre del 2016.

Resoluciones
------------

1. La librería no maneja acción relacionada a los registros.
2. Se manejara el caso de varios Tokens.
3. Con métodos privados de Java se manejara las sesiones.
4. Todas las funciones se manejan de manera asíncrona, dando la opción síncrona desde el cliente.
5. Crear un jar actualizador de la ui (aplicación de escritorio) y el api rest.
6. Dar la opción que el desarrollador fuerce el uso con un token no soportado.
7. Utilizar algoritmos de encriptación validados por la ATT.
8. Manejar firmadores solo con token.
9. No se tomara el sellado de tiempo para esta primera versión.
10. Manejar desde Java la firma en los distintos formatos (Itext) en esta primera version, con posibilidad de ver luego la firma desde javascript.

Funcionalidades de token.
-------------------------

1. Lista de token conectados (lista de identificadores de tokens).
2. Recuperar información del token (identificador, etiqueta, modelo/marca), soportado o no).
3. * Inicializar el token.
4. * Volver a estado de fabrica.
5. Modificar etiqueta del token.
6. * Modificar PIN (del token o 1 par de claves o 1 keystore) → caso de no conocer PIN (No se puede, proveer PUX, proveer PIN SO).
7. Listar los pares de claves (id, etiqueta).
8. Cambiar etiqueta de 1 par de claves.
9. Genera 1 par de claves. (ver parámetros por omisión: Normas ATT).
10. Obtener la información de un par de claves (algoritmo, clave publica).
11. Borrar un par de claves.
12. Listar Certificados.
13. * Obtener información de un certificado (Estructura de representación de un certificado →Buscar Manipular Certificados X509 → Acceder a un campo y representar en  JSON, XML).
14. * Generar 1 CSR (Buscar como representar y manipularlos perfiles de certificados ATT).
15. Incorporar un Certificado (Verificar correspondencia de la clave publica).
16. Borrar certificado.
17. Abrir sesión de un token (proveer PIN).
18. Cerrar Sesión.
19. Verificar estado de Sesión.

Firmar (JavaScript) api rest
----------------------------

1. Firmar archivo (bye[], id certificado, parámetro con verificación de certificado, parametro
formato de firma, parámetros adicionales si corresponde) → para todas las funciones de firma.
2. Recuperar lista de formatos de firma (PaDes → PDF, Xades, XMLDsig, CoD).

Firmar Java
-----------

1. Firmar Documento → (archivo, id_certificado, formato de firma, verificar certificado).
2. Firmar Documento formato (PaDes → PDF, Xades, XMLDsig, CoD → SENAVEX).
3. Firmar archivo “crudo” (Maneja la Cola) → hash cifrado y/o certificado.

Verificar
^^^^^^^^^

1. Validar cadena de confianza de certificado.
2. Validar certificado ATT/Raiz.
3. Validar fechas del certificado (fecha).
4. Verificar estado de revocación. → prever (OCSP, CRL).
5. Listar Firmas de un documento (Manejar los formatos PaDes → PDF, Xades, XMLDsig, CoD).
6. Obtener información de una firma (certificado, fecha).
7. Validar una firma (verificar hash | verificar fechas → fecha de la firma durante periodo de validez del certificado| verificar certificado → no esta reconocido posterior a la fecha de firma).
