# Compiladores_miniC
Proyecto del curso de compiladores

El proyecta utiliza expresiones regulares agregando cad aexpresion a un diccionario junto con su defincio con esto entonces se la entrada linea por linea de esta manera se compara en orden la entrada junto con la expresiones regulares hasta encontrar un match, al enonctrase se toma la posicion de los ccaracteres encontrdas y se realza un split de la linea para quitar lo caracteres emparejados y se continua con el el resto de la linea, de llegarse la final de todas las demas expresiones reguares una expresion regualr que acepta cualquer caracter empareja el "error" y lo escribe como tal en el archivo de salida, la expresiones regulares utilizadas abarcan varios casos y para aqullos caso que no pueden realizarse linea por linea se relizan validacciones externas.

Para el manejo de errores:

1. para cualquier error de carcacter no reconocido como se mencionoeste se empareja con una regex "catch all" para poder remover el caracter y segur analizando el resto de la linea, entonces los carcateres tomados por esta expresion se reportan como carctere no definidos
2. Para el manejo de comentarios sin completar existe una expresion regular que empareja un incio de ocmentario son final que enciendo una bandera que entonces reconoce todo lo que viene en las siguiente lineas como parte del comentario sin importar si cumplen otras regex hasta que una linea cumpla con la regex "fin de comentario" de llegarse al final del programacon esta bandera aun activa se envia un error "EOF comentario sin cerrar"
3. Para string sin completar existe une regex que reconoce una oracion que no cierrar comillas la cual es enviada como error, de ser el ultimo en el archivo se envia error EOF string sin cerar.
4. Para una carcter que excede el tamaño amximo se mide y se ocrta ademas de mandar un error.