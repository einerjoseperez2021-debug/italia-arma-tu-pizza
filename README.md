# Arma tu pizza · Italia Sincelejo 🍕

Página web interactiva para que los clientes de **Italia** (comidas rápidas, Plaza Cultural de Majagual, Sincelejo) armen su pizza personal de 27 cm, la vean salir del horno en 3D y envíen el pedido por WhatsApp.

## ¿Qué hace?

- **Armar la pizza:** la base (salsa de tomate de la casa, mozzarella y finas hierbas) va incluida. Luego, el cliente agrega las adiciones que quiera y puede pedir doble porción de cada una.
- **Precio en vivo:** el total cambia con cada ingrediente.
- **Pedido de varias pizzas:** cada pizza horneada entra al pedido. Desde el botón **Mi pedido**, el cliente puede cambiar la cantidad, editar o quitar cualquier pizza.
- **Envío por WhatsApp:** al finalizar, se abre WhatsApp con el pedido ya escrito: cada pizza, sus adiciones, los subtotales, el total, el nombre, la dirección y las notas del cliente.
- **Funciona en celular y en computador:** en celular, la pantalla queda fija, con una bandeja de ingredientes por pestañas.
- **Bienvenida con Niko:** la mascota de Italia recibe al cliente con una pantalla animada y lo acompaña mientras arma su pizza.
- **Modo restaurante (kiosco):** al agregar `#kiosco` al final del enlace, la página muestra una pantalla de bienvenida y se reinicia sola después de 90 segundos sin uso.

## Cómo publicarla con GitHub Pages

1. Crea un repositorio nuevo en GitHub, por ejemplo `italia-arma-tu-pizza`.
2. Sube los archivos de esta carpeta con **Add file → Upload files**.
3. Entra a **Settings → Pages**.
4. En **Source**, elige **Deploy from a branch**, luego la rama `main` y la carpeta `/ (root)`, y guarda.
5. En uno o dos minutos, la página queda publicada en:
   `https://TU-USUARIO.github.io/italia-arma-tu-pizza/`

Para la tablet del restaurante, usa el mismo enlace con `#kiosco` al final:
`https://TU-USUARIO.github.io/italia-arma-tu-pizza/#kiosco`

## Cómo cambiar precios o datos

Todo lo que se ajusta con frecuencia está al inicio del código, en `index.html`, en la sección **CONFIGURACIÓN**:

```js
const WHATSAPP = '573122957109';   // número que recibe los pedidos (con el 57 de Colombia)
const PRECIO_BASE = 11500;         // pizza base: tomate, mozzarella y finas hierbas
const PRECIO_CATEGORIA = { proteina: 2000, vegetal: 1000, fruta: 1500, queso: 2000, premium: 4000, salsa: 1000 };
const GOATCOUNTER_CODIGO = 'italia-sincelejo'; // panel: https://italia-sincelejo.goatcounter.com
const KIOSCO_INACTIVIDAD_SEG = 90; // segundos sin uso antes de reiniciar en modo kiosco
```

Los ingredientes están en la lista `TOPS`, donde a cada uno se le asigna su categoría de precio.

> **Nota:** los precios de las adiciones son **provisionales**. Salen del análisis de la carta actual y se van a ajustar con el estudio de costos por ingrediente (archivo de Excel del proyecto).

## Medir resultados (panel privado)

La página ya trae la conexión con **GoatCounter**, un servicio gratuito de estadísticas que no usa cookies.

1. Crea una cuenta gratis en [goatcounter.com](https://www.goatcounter.com/). Al registrarte, eliges un código; el de Italia es `italia-sincelejo`.
2. En `index.html`, escribe ese código en la configuración: `const GOATCOUNTER_CODIGO = 'italia-sincelejo';`
3. Sube el archivo de nuevo a GitHub.

Tu panel privado queda en `https://italia-sincelejo.goatcounter.com` y muestra:

| Dato | Qué significa |
|---|---|
| Visitas | Personas que abrieron la página |
| `inicio` | Personas que pasaron la bienvenida de Niko |
| `pizza-horneada` | Pizzas que llegaron al horno |
| `adicion/...` | Cuántas veces se eligió cada adición (por ejemplo, `adicion/pepperoni`) |
| `pedido-enviado` | Pedidos que se enviaron por WhatsApp |

Con estos datos se puede calcular la conversión: de cada 100 personas que entran, cuántas envían un pedido.

## Imagen de vista previa

Cuando alguien comparte el enlace por WhatsApp, Facebook o Instagram, aparece una tarjeta con título, descripción e imagen. El título y la descripción ya están listos. La imagen (`og-image.png`) se agrega cuando la página esté publicada, porque necesita la dirección definitiva del sitio.

## Privacidad

La página no tiene servidor ni base de datos. Cada persona arma su pedido en su propio dispositivo, y los datos (nombre, dirección y notas) solo se usan para escribir el mensaje de WhatsApp. En un celular personal, el nombre y la dirección quedan guardados únicamente en ese navegador para el siguiente pedido. En modo kiosco no se guarda nada.

## Créditos

Proyecto de Marketing y Negocios Digitales · TEINCO.
Hecho para **Italia**, Sincelejo · [@italiasincelejo](https://www.instagram.com/italiasincelejo/)
