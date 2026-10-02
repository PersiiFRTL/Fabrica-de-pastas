# Sistema de gestión de fábrica de pastas

Prototipo de dashboard en un único archivo HTML, con vistas y navegación según el perfil seleccionado.

## Cómo iniciar sesión

1. Abrí `index.html` en un navegador. No hace falta instalar dependencias ni iniciar un servidor.
2. La primera pantalla es un login con usuarios de prueba y contraseñas fijas.
3. Usá alguno de estos usuarios:

- `dueno` / `dueno123` -> Administrador / dueño
- `cliente` / `cliente123` -> Cliente
- `vendedor` / `vendedor123` -> Vendedor
- `produccion` / `produccion123` -> Encargado de producción

4. Luego podés usar el selector de perfil o la navegación según corresponda.

## Vistas por perfil

- **Administrador / dueño:** acceso a todos los módulos y datos de ejemplo: ventas, clientes, empleados, producción, mantenimiento y compras a proveedores.
- **Cliente:** accede únicamente a sus presupuestos y pedidos. En esta vista se quitó la opción de crear usuario desde el módulo del cliente; la cuenta se gestiona con el login y la cuenta activa del cliente.
- **Vendedor:** puede gestionar presupuestos, pedidos, remitos, comprobantes de venta, comprobantes de pago y devoluciones.
- **Encargado de producción:** puede gestionar órdenes de producción, recetas y órdenes de mantenimiento.

## Reglas de negocio del prototipo

- **Receta vinculada al producto:** cada receta indica qué producto se fabrica y la receta queda asociada al producto correspondiente.
- **Producción automática:** en la orden de producción, la cantidad de producción ya no se ingresa como dato independiente; se calcula la materia prima requerida automáticamente según el producto y la receta asociada.
- **Los datos creados desde los formularios viven en la memoria de la página y se pierden al recargar.**

## Alcance del prototipo

La vista Cliente inicia con la cuenta de ejemplo María González. El selector de perfiles y la cuenta activa son simulaciones locales del frontend, no un sistema real de autenticación ni autorización. Para uso real se necesita persistencia en base de datos, validación del lado del servidor y gestión de sesiones.
