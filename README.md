# Sistema de gestión de fábrica de pastas

Prototipo de dashboard en un único archivo HTML, con vistas y navegación según el perfil seleccionado.

## Cómo ver las vistas

1. Abrí `index.html` en un navegador. No hace falta instalar dependencias ni iniciar un servidor.
2. Usá el selector **Vista de perfil**, arriba a la derecha, para cambiar entre **Administrador / dueño**, **Cliente**, **Vendedor**, **Encargado de producción** y **Administración**.
3. Elegí una sección en el menú lateral para abrir sus pantallas. El dashboard también ofrece accesos directos a los módulos del perfil activo.
4. El perfil elegido se guarda en el navegador. Al volver a abrir el archivo en ese mismo navegador, se mantiene la última vista seleccionada.

## Vistas por perfil

- **Administrador / dueño:** acceso a todos los módulos y datos de ejemplo: ventas, clientes, empleados, producción, mantenimiento y compras a proveedores.
- **Cliente:** puede crear una cuenta y acceder únicamente a los presupuestos y pedidos asociados al documento de su cuenta activa. Las opciones para vincular un pedido también se limitan a esa cuenta y a sus propios presupuestos.
- **Vendedor:** puede gestionar presupuestos, pedidos, remitos, comprobantes de venta, comprobantes de pago y devoluciones.
- **Encargado de producción:** puede gestionar órdenes de producción, recetas y órdenes de mantenimiento.
- **Administración:** puede gestionar materias primas, productos, recetas, máquinas, mantenimiento, repuestos, proveedores, clientes, presupuestos de proveedores, órdenes de compra, remitos y comprobantes de proveedores, órdenes de pago y comprobantes de venta y pago.

## Alcance del prototipo

La vista Cliente inicia con la cuenta de ejemplo María González. Si se crea otra cuenta, pasa a ser la cuenta activa durante esa sesión y sus pedidos y presupuestos se asocian a su documento. El selector de perfiles y el filtro de cuenta son solo una simulación local: no reemplazan inicio de sesión ni autorización. Los registros creados desde los formularios viven en la memoria de la página y se pierden al recargar. Para usarlo con clientes reales se necesita persistencia en una API/base de datos, autenticación y validación de permisos en el servidor.
