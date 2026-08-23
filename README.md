# kalinda.app

Sitio público de **Kalinda**, la app de conteo de calorías. HTML y CSS estáticos, sin dependencias ni proceso de compilación: se sirve con GitHub Pages en el dominio `kalinda.app`.

El código de la app vive aparte, en el repositorio privado `kalinda-app`.

## Páginas

| Español | English | Para qué sirve |
|---|---|---|
| `/` | `/en/` | Página de inicio. Es la *Application home page* que exige la pantalla de consentimiento de Google, y la *Marketing URL* de App Store Connect. |
| `/privacidad.html` | `/en/privacy.html` | Política de privacidad. Obligatoria en Google Play, App Store y en la configuración de OAuth de Google. |
| `/terminos.html` | `/en/terms.html` | Términos de uso. |
| `/eliminar-datos.html` | `/en/delete-data.html` | Instrucciones de borrado de cuenta. Es la URL que pide Google Play en *Data safety*. |
| `/soporte.html` | `/en/support.html` | Ayuda. Es la *Support URL* de App Store Connect. |

Cada página enlaza a su equivalente en el otro idioma desde la cabecera.

## Estructura

```
index.html, privacidad.html, ...   páginas en español
en/                                las mismas en inglés
styles.css                         estilos compartidos
assets/                            icono, favicon y capturas
CNAME                              dominio personalizado de GitHub Pages
```

`styles.css` reproduce los tokens de color de la app (`src/theme/colors.ts` en `kalinda-app`) y usa la misma tipografía, Outfit. Tiene modo oscuro automático según las preferencias del sistema. Si cambian los colores de la app, hay que reflejarlo aquí a mano: los dos proyectos no comparten código.

## Publicar cambios

Editar el HTML y hacer push a `master`. GitHub Pages reconstruye el sitio solo, en menos de un minuto. No hay nada que compilar ni que instalar.

## DNS

El dominio está en Porkbun. `kalinda.app` apunta a los servidores de GitHub Pages con cuatro registros `A` y `www` con un `CNAME` a `yordanglez.github.io`. El archivo `CNAME` de este repositorio es el que le dice a GitHub qué dominio servir: si se borra, el sitio vuelve a `yordanglez.github.io/kalinda-web`.

## Pendiente

- El botón principal de la portada apunta a `mailto:hola@kalinda.app` porque la app todavía está en pruebas cerradas. Cuando salga a producción en Google Play y en App Store, sustituirlo por los enlaces reales a las fichas de las tiendas (está en `index.html` y en `en/index.html`, dos líneas).
- Las capturas son las de la versión 1.1.0. Conviene renovarlas cuando cambie el diseño.
