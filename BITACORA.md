# Bitácora · Semana 4 · GraphQL
Estudiante: David Tapia
URL GraphQL: https://TU-SERVICIO-GRAPHQL.onrender.com/graphql
Repositorio: https://github.com/TU-USUARIO/nestjs-productos-graphql

1. REST vs GraphQL: "todos los productos, solo nombres, más el detalle de uno"
   necesita 2 llamadas REST (el listado devuelve objetos completos y el detalle
   es otro endpoint). En GraphQL es 1 petición con solo los campos pedidos.
2. Cambio del paso 6: antes el resolver usaba el arreglo `catalogo` en memoria;
   ahora usa HttpService contra mi propia API de productos desplegada en Render
   (la que construí en la práctica de persistencia con PostgreSQL). La query no
   cambió, solo el origen de los datos.
3. Diferencias respecto a la guía: el `app.module.ts` debe conservar `ObserveModule`
   porque `main.ts` usa `ObserveInstrument`; la interfaz de pruebas en `/graphql`
   es GraphiQL (no Apollo Sandbox), configurada con `graphiql: true` e
   `introspection: true` para que también funcione en producción.

### Declaración de uso de IA
- Herramienta(s): Claude (Anthropic)
- Nivel de uso: 2–3
- Qué se le pidió: revisar la guía y detectar sus errores, corregir el
  `app.module.ts`, diagnosticar los errores de compilación y de arranque, y
  explicar cómo subir el proyecto a GitHub y desplegarlo en Render.
- Qué se modificó/verificó manualmente: ejecuté cada paso en mi máquina; revisé
  los errores de compilación (`ObserveInstrument` y conflicto de plugins de
  Apollo) y apliqué las correcciones; confirmé que la app arranca
  (`Nest application successfully started`); probé las queries `productos`,
  `productoPorId`, la de solo `nombre` y `productosBaratos` (50 y 100) en
  GraphiQL; conecté el resolver a mi API real; hice commit y push a GitHub;
  [BORRA ESTA LÍNEA SI NO LO HICISTE: desplegué el servicio en Render y repetí
  las queries sobre la URL pública].