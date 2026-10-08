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

4. Luego podés usar la navegación según el perfil. La sección “Crear cuenta” ya no aparece en la vista del dueño; la creación de usuarios de prueba sigue disponible desde el login.

## Vistas por perfil

- **Administrador / dueño:** acceso a todos los módulos y datos de ejemplo: ventas, clientes, empleados, producción, mantenimiento y compras a proveedores.
- **Cliente:** accede únicamente a sus presupuestos y pedidos. En esta vista se quitó la opción de crear usuario desde el módulo del cliente; la cuenta se gestiona con el login y la cuenta activa del cliente.
- **Vendedor:** puede gestionar presupuestos, pedidos, remitos, comprobantes de venta, comprobantes de pago y devoluciones.
- **Encargado de producción:** puede gestionar órdenes de producción, recetas y órdenes de mantenimiento.

## Reglas de negocio del prototipo

- **Receta vinculada al producto:** cada receta indica qué producto se fabrica y la receta queda asociada al producto correspondiente.
- **Producción automática:** en la orden de producción, la cantidad de producción ya no se ingresa como dato independiente; se calcula la materia prima requerida automáticamente según el producto y la receta asociada.
- **Clientes:** se deshabilitan y se pueden volver a habilitar; no se eliminan para conservar su historial. El límite de deuda es distinto del saldo pendiente.
- **Pedidos:** cada pedido se registra como una Orden de Pedido con número propio. Desde un presupuesto se puede generar la orden asociada copiando cliente e ítems; hereda el tipo del presupuesto y muestra solo los campos de agenda correspondientes: mostrador usa fecha de entrega, fijo semanal usa fechas de inicio/fin y días, y evento/fiesta usa fecha del evento.
- **Pagos y facturación:** una orden permite preparar su comprobante de venta. Los anticipos se registran como comprobantes de pago asociados a una o más órdenes; cada comprobante admite varias líneas con distintos medios de pago.
- **Fechas:** se muestran en formato `DD/MM/AAAA` en las tablas y detalles; los formularios conservan el formato ISO necesario para los controles de calendario.
- **Persistencia local:** clientes, presupuestos, pedidos, detalles y comprobantes se guardan en `localStorage` del navegador y se mantienen al recargar en ese mismo navegador. No se sincronizan entre dispositivos ni reemplazan una base de datos o un sistema de facturación fiscal.

## Alcance del prototipo

La vista Cliente inicia con la cuenta de ejemplo María González. El selector de perfiles y la cuenta activa son simulaciones locales del frontend, no un sistema real de autenticación ni autorización. Para uso real se necesita persistencia en base de datos, validación del lado del servidor, gestión de sesiones y emisión fiscal integrada.
