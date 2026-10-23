# Pedido Burger — Demo de pedidos y comanda

Prototipo frontend de pedidos para un local gastronómico. Construido con **HTML, CSS, Bootstrap y JavaScript**, sin backend ni servidor de datos.

> **Alcance:** demostración local y educativa. No es un POS, sistema de facturación ni plataforma apta para recibir pedidos de clientes en producción.

## Pantallas

| Archivo | Función |
| --- | --- |
| `index.html` | Inicio: tipo de pedido y nombre del cliente |
| `totem.html` | Menú, carrito y confirmación de pedidos |
| `Comanda.html` | Vista de cocina con estados y acciones |
| `status.html` | Consulta del estado de pedidos por nombre |

## Cómo ejecutarlo

Se recomienda servir los archivos desde un servidor HTTP local y abrir todas las pantallas **en el mismo navegador y origen**.

Ejemplo con Python 3:

```bash
python -m http.server 8000
```

Abrir `http://localhost:8000/index.html`. Para observar los mensajes abrir además `Comanda.html` y `status.html` en pestañas del mismo navegador.

## Funcionamiento y límites

- La interfaz guarda cierta información temporal en `sessionStorage` y puede utilizar `localStorage` según la pantalla.
- Las pantallas usan `BroadcastChannel` y `postMessage` para intercambiar eventos. **BroadcastChannel funciona entre contextos compatibles del mismo origen y entorno de almacenamiento, no es sincronización de red entre equipos.**
- La comanda conserva pedidos en memoria mientras la pestaña está abierta. Recargarla puede perder el estado.
- No hay backend, autenticación, autorización, stock, facturación, pagos reales ni base de datos compartida.
- Los datos y precios del menú son demostrativos.
- La carga de nombres y productos en vistas de comanda se escapa como texto HTML para mitigar la inyección de marcado desde los campos dinámicos.

## Requisitos para llevarlo a producción

Serían necesarios, al menos, una API/backend, persistencia de pedidos, identificación de órdenes, sesiones, roles de cocina/caja, validación del servidor, sincronización real entre clientes, controles de seguridad, pruebas y observabilidad.

## Qué demuestra

Flujos de interfaz de pedidos, carrito, gestión de estados tipo Kanban, comunicación entre pestañas y trabajo con DOM sin framework. Este proyecto es un **ejemplo frontend** distinto de mis desarrollos comerciales en .NET.

**Autor:** Enzo Torricella · [Portfolio](https://etorri.com.ar/) · [GitHub](https://github.com/enzotorricella)
