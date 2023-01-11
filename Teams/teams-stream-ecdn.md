---
title: Escalar la entrega de vídeo en Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: asteele
search.appverid: MET150
f1.keywords:
- NOCSH
description: En este artículo se describen las redes de entrega de vídeo a escala y de entrega de contenido empresarial (eCDN) para los eventos de streaming de Microsoft Teams.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 9475ac8a99a7858221c062ccedb0bd1327f37e4c
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767976"
---
# <a name="scale-video-delivery-and-monitor-network-traffic-by-using-ecdns-with-microsoft-teams"></a>Escalar la entrega de vídeo y supervisar el tráfico de red mediante eCDNs con Microsoft Teams

La reproducción de vídeos de Microsoft Teams y los eventos en directo de "aplicación o dispositivo externo" (anteriormente conocidos como producciones de "codificador externo") usan streaming de velocidad de bits adaptable (ABR) entregado como secuencia de unidifusión. Esto significa que cada visor está recibiendo su propia transmisión de vídeo de Internet. En el caso de eventos en directo o vídeos enviados a grandes partes de su organización, podría haber una cantidad significativa de ancho de banda de red e Internet consumido por los visores.

Es posible que las organizaciones quieran comprender y reducir este tráfico de red para eventos en directo y vídeos populares. Si es así, se puede habilitar Teams para integrarse con asociados de confianza de Microsoft que ofrecen soluciones de red de entrega de contenido empresarial (eCDN) que incluyen tecnologías de entrega de administración automática, supervisión en tiempo real y análisis de red detallados. Estas plataformas eCDN permiten a las organizaciones supervisar, escalar y optimizar la distribución de transmisiones de vídeo (y, a veces, otros tipos de contenido) en su red empresarial.

## <a name="acquire-and-set-up-your-ecdn-solution-outside-of-teams"></a>Adquirir y configurar su solución de eCDN fuera de Teams

Obtenga ayuda de expertos con la supervisión y la distribución de vídeo a escala al asociarse con asociados de confianza de eCDN de Microsoft.

Para poder usar una solución de eCDN con Teams, debe comprarla y configurarla fuera y aparte de Teams. Para garantizar que la solución satisfaga sus necesidades, algunos partners proporcionan pruebas gratuitas de sus tecnologías de distribución de contenido y análisis de red.

Varias soluciones de eCDN están preins integradas y se pueden habilitar para su uso con Teams. Consulta la información de los proveedores a continuación.

### <a name="hive-streaming"></a>Streaming de subárbol

La **plataforma de experiencia de vídeo de streaming de Hive** consta de tres productos principales:

- **Optimización de vídeo de Hive** se basa en un algoritmo patentado de configuración cero solo para software. La optimización maximiza automáticamente la calidad y el alcance del vídeo en directo y bajo demanda (VOD) para toda la organización.
- **Hive Video Analytics** ayuda a los clientes a comprender las tendencias en eventos en directo y el rendimiento de vídeo bajo demanda para mejorar la participación del espectador a lo largo del tiempo. A medida que mejora la participación, también lo hace la adopción de vídeo en toda la empresa.
- **Hive Video Operations** ofrece potentes capacidades con el objetivo de asegurar de forma proactiva el éxito del vídeo en streaming antes y durante los eventos de vídeo en directo. Las herramientas operativas permiten a sus equipos de streaming de vídeo y UC encontrar y corregir problemas antes de que se produzcan.

Todos ellos trabajan para crear experiencias de vídeo de alcance completo, desde la planificación hasta la ejecución y el análisis. Maximizar la experiencia de comunicación de vídeo en streaming es crucial para la participación y la alineación de los empleados en la misión de su empresa. Para obtener más información, echa un vistazo a [este vínculo](https://www.hivestreaming.com/partners/microsoft).

### <a name="kollective"></a>Kollective

**Kollective Technology** es una plataforma de distribución de contenido basada en la nube que utiliza emparejamiento inteligente para ofrecer vídeo empresarial en directo y bajo demanda, proporcionando una calidad de vídeo del 100 % y una participación del 100 % con solo el 1 % del ancho de banda. La integración de Kollective con Teams Live Events permite a los empleados dispersos globalmente consumir vídeo fácilmente, mejorar la comunicación de los empleados, impulsar la participación general y aumentar la formación y las oportunidades de retención.

**Kollective IQ** es una plataforma de análisis sofisticada y fácil de usar para Microsoft Stream. Con los informes, visualizaciones y paneles personalizables, es fácil cuantificar y digerir tanto la experiencia del usuario como la participación en redes empresariales globales complejas. Los administradores de comunicación y de red pueden ver los eventos en tiempo real y la actividad de la red, por lo que se pueden solucionar los cuellos de botella rápidamente, lo que garantiza un rendimiento máximo de la red.

Para obtener más información sobre estas opciones, consulte [este vínculo](https://kollective.com/microsoft-live-events/).

### <a name="microsoft-ecdn"></a>Microsoft eCDN

**Microsoft eCDN** resuelve el problema de congestión de la red que se produce durante grandes eventos virtuales corporativos, como reuniones de todo tipo. Microsoft eCDN forma una red de malla a través de la LAN que reduce la carga en un 95 % y elimina los problemas de red. Microsoft eCDN es el primer eCDN en usar WebRTC como base, lo que significa que no se necesita instalación de software o hardware. Los clientes de Fortune 500 mitigan problemas de redes y confían en Peer5 para sus mayores eventos corporativos.

- La configuración de red de configuración cero para microsoft eCDN garantiza que los trabajadores remotos y/o el tráfico de vídeo pesado no obstetrará su red ni le obligará a invertir en una infraestructura costosa. Incluye la detección automática de sitios, la detección automática de VPN y el cruce automático nat/firewall. Obtenga más información en [este vínculo](/ecdn/how-to/enable-microsoft-ecdn-for-your-tenant).
- Las pruebas silenciosas con Microsoft eCDN permiten a los administradores de TI simular grandes eventos en directo en su red corporativa, lo que permite pruebas exhaustivas y no disruptivas y la solución de problemas antes de un evento real. Obtenga más información en [este vínculo](/ecdn/how-to/perform-silent-test).
- Los análisis líderes del sector de Microsoft eCDN proporcionan análisis granulares y permiten a los administradores encontrar rápidamente la causa raíz de cualquier problema de streaming. El kit de herramientas incluye métricas de entrega y experiencia del usuario, obtenciones avanzadas de detalles, análisis por usuario y una API back-end. Obtenga más información en [este vínculo](/ecdn/technical-documentation/analytics).

### <a name="ramp"></a>Ramp

**El eCDN de rampa** reduce el consumo de ancho de banda de red en un 90 % o más cuando se realizan streaming de eventos en directo y vídeo bajo demanda (VOD). Use Ramp para mezclar y hacer coincidir cualquier combinación de tecnologías de eCDN:multidifusión, almacenamiento en caché y redes punto a punto. Gracias a la administración centralizada, la supervisión y el análisis exhaustivo, obtiene visibilidad y control sobre el rendimiento de la red para crear la experiencia del visor de la más alta calidad.

- **Ramp Multicast+** es la forma más eficiente de transmitir vídeo en vivo. Usando el protocolo multicast, usted consume solamente el ancho de banda requerido para un visor, si usted tiene 100, 10,000, o 100,000 visores. Obtenga más información en [este vínculo](https://www.rampecdn.com/altitudecdn/multicast/).
- **Ramp OmniCache™** es un software de almacenamiento en caché específico de vídeo que usa cachés locales para servir vídeo en directo y VOD a audiencias cercanas, lo que reduce drásticamente el número de transmisiones de vídeo que viajan a través de sus conexiones a Internet y vínculos WAN. Obtenga más información en [este vínculo](https://www.rampecdn.com/altitudecdn/video-cache/).
- **Ramp Peer-to-Peer (P2P)** le permite optimizar el ancho de banda incluso en ubicaciones con infraestructura limitada. P2P crea una red de punto de dispositivos cliente que ven el mismo contenido para redistribuir las transmisiones de vídeo de un dispositivo de visualización a otro. Obtenga más información en [este vínculo](https://www.rampecdn.com/altitudecdn/p2p/).

### <a name="riverbed"></a>Riverbed

**Riverbed**, el estándar del sector en optimización de red, ha ampliado sus soluciones de aceleración a Teams. Los clientes de Microsoft 365 pueden acelerar con confianza el tráfico de Microsoft 365, incluido Teams, junto con una gran cantidad de otros servicios SaaS empresariales líderes para aumentar la productividad de la fuerza de trabajo desde cualquier lugar. La aceleración de Teams se puede habilitar a través de una configuración sin esfuerzo que viene con toda la garantía de que Riverbed ofrece soporte técnico de primera clase e inversión continua. Obtenga más información en [este vínculo](https://www.riverbed.com/office365).

> [!NOTE]
> La solución de eCDN elegida está sujeta a los términos de servicio y a la directiva de privacidad del proveedor de eCDN asociado seleccionado, que regirán el uso de la solución del proveedor de eCDN. El uso de la solución del proveedor de eCDN no estará sujeto a los términos de licencias por volumen de Microsoft ni a los Términos de servicios en línea. Si no acepta los términos del proveedor de terceros, no habilite la solución eCDN en Microsoft Teams.

## <a name="configure-stream-encoder-type-events-for-your-ecdn-solution"></a>Configurar eventos de tipo de codificador de Stream para la solución de eCDN

Después de comprar y configurar la solución eCDN, puede habilitarla para su uso con Microsoft Stream, incluidos los eventos en directo del codificador de Stream creados a través de Microsoft Teams o Yammer.

1. Abra el Centro de administración de Teams como administrador global de Microsoft 365 o administrador de Teams y vaya a la página [de configuración de eventos en directo](https://admin.teams.microsoft.com/broadcasts/settings) .
1. Cambie el **proveedor de distribución de vídeo** a **Activado**.
1. Elija un **proveedor de eCDN/SDN** en la lista desplegable **Proveedor de distribución de vídeo** .
1. Rellene los demás campos según le indique su proveedor de soluciones (no todos los campos los usan todos).
1. Seleccione **Guardar**.
1. Para comprobar si la configuración es correcta, selecciona **Comprobar configuración**.
    - Busque cualquier vídeo de su organización con el que validar.
    - Si su proveedor de eCDN está configurado correctamente, **verá un mensaje** correcto en la herramienta de configuración de comprobación.
    - Si no está configurado correctamente, verá un mensaje **de Error** . Copie el mensaje del evento para compartirlo con su proveedor para solucionar problemas.

Después de configurar Teams para una solución de eCDN, cualquier vídeo o evento en directo que se reproduzca en Teams se aprovechará automáticamente de esa solución.

## <a name="configure-teams-production-type-events-through-teams-and-yammer-for-your-ecdn-solution"></a>Configurar eventos de tipo de producción de Teams a través de Teams y Yammer para su solución de eCDN

Si tiene previsto crear eventos en directo de Teams a través de Teams o Yammer, deberá [configurar su proveedor de eCDN para que también se integre con Microsoft Teams](teams-live-events/what-are-teams-live-events.md#enterprise-content-delivery-network-ecdn) .

### <a name="get-to-video-analytics-reports-for-your-ecdn-solution"></a>Obtener informes de análisis de vídeo para su solución de eCDN

Como se mencionó anteriormente, algunas soluciones de eCDN también proporcionan informes de análisis que proporcionan información más detallada sobre las sesiones de reproducción, los visores y la calidad del servicio. Si su proveedor le proporcionó una plantilla de URL de informe de análisis para configurarla al configurar el proveedor en el Centro de administración de Teams, los propietarios de vídeos o eventos pueden acceder fácilmente al informe de análisis de un vídeo o evento específico.

Los propietarios de vídeos verán una pestaña Análisis directamente debajo del vídeo. En esta pestaña, habrá un vínculo para que los propietarios accedan al informe de análisis de este vídeo específico en el sistema del proveedor de eCDN.

Si es administrador de Teams, también puede elevar su acceso para ver la pestaña Análisis y acceder al vínculo del informe de análisis de eCDN, incluso si no es el propietario del evento o vídeo en directo.

1. Como administrador de Teams, vaya a la página del reproductor de vídeo.
1. Seleccione **Configuración**.
1. Seleccione **Ver en modo de administración**.
1. Seleccione la pestaña **Análisis** .

## <a name="troubleshooting-issues"></a>Solución de problemas

Asegúrese de que la solución de eCDN está configurada correctamente en su red y de que ha configurado correctamente Teams para habilitar el proveedor según sus instrucciones y cadenas de configuración específicas. Si sigues teniendo problemas, es posible que alguna de las siguientes informaciones te ayude.

### <a name="verify-setup-tool"></a>Comprobar la herramienta de configuración

Si tiene problemas con la solución de eCDN, siempre puede volver y ejecutar la herramienta de **configuración Comprobar** . Los mensajes de eventos del proveedor de eCDN que se muestran para el vídeo de prueba pueden proporcionarle a usted y a su proveedor de eCDN más información sobre lo que no funciona.

- Vaya a **Configuración** >  **Administración Proveedor** >  de **configuración** >  eCDN **Comprobar configuración**

### <a name="disable-ecdn-for-a-specific-session-via-url-query-string"></a>Deshabilitar eCDN para una sesión específica a través de la cadena de consulta de dirección URL

Para determinar si un problema que está viendo es con la solución eCDN o con Teams, puede deshabilitar fácilmente la solución de eCDN para una sesión de reproducción específica a través de una cadena de consulta.

- Si la dirección URL de reproducción ya tiene un signo de interrogación, **?**, a continuación, agregue **&disableSDN=true**.
- Si la dirección URL de reproducción no tiene un signo de interrogación, **?**, en ella agregue **?disableSDN=true**.

### <a name="view-ecdn-info-in-browser-console"></a>Ver información de eCDN en la consola del explorador

Si su proveedor de soluciones eCDN lo admite, es posible que imprima información de depuración durante la inicialización de la reproducción a través de su solución. Esta información adicional puede ser útil para determinar lo que va mal. Puede habilitar mensajes de depuración de consola adicionales a través de la cadena de consulta.

- Si la dirección URL de reproducción ya tiene un signo de interrogación, **?**, en ella, agregue **&isSDNDebug=true**.
- Si la dirección URL de reproducción no tiene un signo de interrogación **? en** ella, agregue **?isSDNDebug=true**.

Seleccione **F12** en el teclado cuando el explorador esté activo y cambie a la pestaña **Consola** para ver toda la información impresa durante la carga de la página con la cadena de consulta isSDNDebug=true establecida en la dirección URL de reproducción.
