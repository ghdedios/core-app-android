# Core App para Android

App de demo para mostrar un agente de Agentforce desde el celular, por texto y por voz, encima del sitio web del
cliente. Cargás la URL del cliente y los datos de tu org, y la app abre el sitio con el widget de Agentforce arriba.
Cada uno usa su propio agente. La voz sale por el parlante.

Hecha por Solution Engineering LATAM para demos. No es un producto oficial de Salesforce y no tiene soporte.

**Descargar:** [última versión](../../releases/latest) → `CoreApp-<versión>.apk`. Necesita Android 10 o más nuevo.

## Antes de empezar: usá el Chrome personal

Si tu teléfono tiene un **perfil de trabajo** (Workspace ONE / Intelligent Hub), ahí no se pueden instalar apps
bajadas de internet. Abrí este link con el **Chrome personal**, el que **no** tiene el maletín en el ícono. Así el APK
queda en las descargas del perfil personal, que sí lo deja instalar. No hace falta iniciar sesión en nada.

- ¿Ya tenés una Core App instalada desde Android Studio o compilada en otra Mac? Desinstalala primero: está firmada con
  otra clave y Android no deja instalar esta encima ("App no instalada").
- No lo hagas en medio de una llamada: Android bloquea el permiso de fuentes desconocidas mientras hay una.

## Instalar

1. En el Chrome personal, abrí la [última versión](../../releases/latest) y tocá `CoreApp-<versión>.apk` en
   **Assets**. Si Chrome avisa "Es posible que el archivo sea dañino": **Descargar de todos modos**.
2. **Samsung:** si tenés **Auto Blocker** activado (Ajustes → Seguridad y privacidad → Auto Blocker), desactivalo.
   Mientras está activo, sólo deja instalar desde Play Store y Galaxy Store.
3. Abrí el APK desde la notificación de la descarga o desde las descargas de Chrome. Si pregunta con qué abrirlo:
   **Instalador de paquetes → Solo una vez**.
4. La primera vez dice que el teléfono no tiene permitido instalar aplicaciones desconocidas de esta fuente:
   **Configuración → Otorgar permiso**. Lo normal es que el instalador siga solo; si no, volvé y **abrí el APK otra
   vez**. En Android 16 puede aparecer un aviso ("Tu teléfono y tus datos están más expuestos…"): **Continuar**.
5. "¿Deseas instalar esta app?" → **Instalar** (si ya la tenías: "¿Deseas actualizar esta app?" → **Actualizar**).
6. La primera vez, **Google Play Protect** muestra "Se recomienda analizar la app" porque no la conoce. Sirve
   cualquiera de las dos: **Analizar app**, o **Más detalles → Instalar sin analizar**. "Instalar sin analizar" es la
   línea que queda **debajo** del link "Cómo funciona Play Protect": si tocás el link, se cancela la instalación.
7. "Se instaló la app." → **Abrir**. Pide el **micrófono** (Mientras la app está en uso). La primera vez que pases a
   voz pide las **notificaciones** (Permitir): sin eso la voz no arranca.
8. Si querés, volvé a activar Auto Blocker y sacale a Chrome el permiso de instalar apps desconocidas.

La primera conversación después de instalar o de cambiar de org tarda hasta un minuto en arrancar. Desde la 1.5 la app
conecta apenas abrís la demo, así que esa espera pasa mientras mostrás el sitio.

## Qué necesita tu org

Un agente de servicio activo y un Embedded Service deployment para mobile (canal de Messaging for In-App, con Voice
habilitado y el guest user activo). En la app se cargan cuatro datos: Organization ID, Service API URL (la del SCRT,
`https://<tu-dominio>.my.salesforce-scrt.com`), el Developer Name del Embedded Service y el My Domain.

## Si algo no anda

- Antes de la demo, en la configuración tocá **Probar conexión**: te dice si la org responde, si el deployment existe
  y es Mobile, y si el canal tiene voz. Cada campo avisa si el dato tiene algo raro.
- Si el agente no entra o algo falla, volvé a la configuración y tocá **Enviar diagnóstico** (abajo de todo, al lado
  de la versión). Mandanos ese archivo por Slack o WhatsApp: lleva la versión, el teléfono, los datos cargados y el log
  de la app.

## Actualizar

Bajá el APK nuevo e instalalo encima del anterior, con los mismos pasos. **No desinstales**: perderías "Mis
ambientes". Si una versión nueva dice "App no instalada", avisanos.

## Comprobar el archivo

Cada release trae el SHA-256 del APK. En la Mac: `shasum -a 256 CoreApp-<versión>.apk`.
