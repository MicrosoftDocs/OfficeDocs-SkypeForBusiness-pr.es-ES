---
title: Solución de problemas de streaming en directo en Microsoft Teams
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
description: En este artículo se explican las opciones de solución de problemas de los eventos de streaming de Microsoft Teams.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: d88b8c0f356bcf59319f073c0e75c65a25361cf2
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767995"
---
# <a name="troubleshooting-live-events-in-microsoft-teams"></a>Solución de problemas de eventos en directo en Microsoft Teams

> [!IMPORTANT]
> **China**: Los usuarios que se encuentren en China no podrán configurar ni asistir a eventos en directo de Teams o Yammer, ni ver vídeos a petición, ya que, actualmente, la red CDN de Azure en la que dependen estas aplicaciones podría no ser accesible en China.
>
> Como administrador, es posible que tengas que configurar una VPN para conectar tu red corporativa para que estas aplicaciones funcionen sin problemas. Una vez completado, los usuarios de su organización pueden programar y asistir a eventos en directo.

## <a name="before-a-live-event"></a>Antes de un evento en directo

### <a name="make-sure-all-events-are-reachable-in-your-network"></a>Asegurarse de que todos los eventos sean accesibles en la red

#### <a name="general-teams-endpoints"></a>Puntos de conexión generales de Teams

Teams requiere conectividad a Internet. Todos los puntos de conexión [enumerados en Office 365 puntos de conexión para Teams deben ser accesibles](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) para los usuarios de Teams dentro de la red de su organización.

#### <a name="teams-encoder-live-events---rmtp-ingest-endpoints"></a>Eventos en directo del codificador de Teams: puntos de conexión de sugerencias de RMTP

Para obtener una fuente de vídeo para un evento en directo del codificador de Teams enviado a Teams desde su codificador, necesitará que el nombre de dominio y los puertos se abran en el firewall de su red:

- Dominios: *.rtmpingest.mcr.teams.microsoft.com
- Puertos: 1935/1936 (para RTMP/RTMPS)

### <a name="make-sure-you-have-enough-upload-bandwidth"></a>Asegurarse de que tiene suficiente ancho de banda de carga

Al producir o hacer streaming de un evento en vivo a través de RTMP, es posible que el ancho de banda de carga de Internet en el sitio que empuja la transmisión en directo no sea suficiente. El bajo ancho de banda de carga puede provocar la caída de fotogramas o problemas en el propio vídeo en directo, lo que puede provocar problemas de reproducción para los espectadores.

Asegúrese de que la velocidad de carga para el equipo y la red que empuja la transmisión en directo sea mayor que la velocidad de bits que estableció para la transmisión en directo. Si estás generando una transmisión de 5 Mbps desde el codificador, pero la velocidad de bits de carga es cercana o inferior a esa, podrías tener problemas para no poder cargar la transmisión lo suficientemente rápido.

Si tienes problemas con el ancho de banda de carga, estas son algunas cosas que puedes probar:

1. Utilice una conexión Ethernet de cable duro para cualquier máquina desde la que esté empujando el flujo para evitar caídas en el WiFi.
1. Reduzca la velocidad de bits de codificación de su fuente en vivo a un valor muy por debajo de la velocidad de carga máxima.

### <a name="preparing-your-network-for-many-concurrent-viewers"></a>Preparar la red para muchos visores simultáneos

Durante los eventos en directo, muchas personas se unirán para ver el evento en directo. Esto podría sobrecargar tu red y el ancho de banda de descarga de Internet. Necesita evaluar la infraestructura de red actual y asegurarse de que los usuarios de su red corporativa tendrán el ancho de banda necesario para ver un evento en directo. Para ayudar a reducir el tráfico de Internet necesario para eventos en directo hay dos opciones:

1. Configure servidores proxy de caché existentes en la red para almacenar en caché vídeos de Teams.
1. Use una solución de entrega de vídeo eCDN de terceros para optimizar el tráfico de vídeo.

### <a name="i-cant-create-a-live-event"></a>No puedo crear un evento en directo

Hay permisos en Microsoft Teams y Yammer que un usuario necesita para poder crear un evento en directo en función del servicio que use para el evento en directo.

1. Compruebe que el administrador de Teams le ha habilitado para crear eventos en directo.
1. Póngase en contacto con su administrador para comunicarle que tiene una licencia de Teams válida que permite la creación de eventos en directo.

### <a name="make-sure-viewers-have-permission-to-watch-the-event"></a>Asegurarse de que los espectadores tienen permiso para ver el evento

Los eventos en directo de Microsoft Teams tienen algunos roles diferentes para los permisos en el propio evento (organizador, productor, moderador y asistente).

Consulte [Roles de grupo de eventos de Microsoft Teams](https://support.office.com/article/microsoft-teams-live-events-overview-d077fec2-a058-483e-9ab5-1494afda578a#bkmk_roles) para obtener más información.

## <a name="producing-a-live-event"></a>Producir un evento en directo

### <a name="i-dont-know-how-to-set-up-my-encoder"></a>No sé cómo configurar mi codificador

La forma más sencilla de empezar es seguir las instrucciones que se describen en el artículo [Usar un codificador para streaming en directo en Microsoft Teams](teams-encoder-setup.md) .

### <a name="my-encoder-isnt-connecting-to-the-server-ingest-url"></a>Mi codificador no se está conectando a la dirección URL de entrada del servidor

- Comprueba que la dirección URL RTMP se introduce correctamente como resultado del codificador.
- Comprueba que la clave RTMP se introduce correctamente como resultado del codificador.
- Comprueba el estado de la conexión a Internet para asegurarte de que el codificador esté correctamente conectado y en línea.
- Es posible que tengas una configuración de seguridad de red o relacionada con el firewall que esté bloqueando la salida de la conexión.
- Es posible que el codificador no sea compatible con Teams. Consulte la lista de codificadores probados en [Usar un codificador para el streaming en directo en Microsoft Teams](teams-encoder-setup.md).

### <a name="i-cant-get-rtmps-to-work"></a>No puedo hacer que los RTMPs funcionen

- Es posible que algunos codificadores admitan una implementación diferente que no es compatible con Teams. Consulte la lista de codificadores probados que funcionan con Teams en [Usar un codificador para el streaming en directo en Microsoft Teams](teams-encoder-setup.md).
- No todos los codificadores o versiones admiten RTMPs. Consulta con el fabricante o el creador de software para ver qué es lo que admiten.

### <a name="i-tried-to-start-setup-and-its-taking-a-long-time"></a>Intenté iniciar la configuración y está tardando mucho tiempo

En general, la configuración puede tardar unos minutos antes de que puedas empezar a insertar el codificador. Si el servicio está ocupado, es posible que esto tarde más en ponerse en marcha, por lo que se recomienda que disponga de suficiente tiempo para iniciar la configuración antes del evento en directo programado.

### <a name="i-tried-to-start-setup-but-there-are-too-many-events-happening"></a>Intenté iniciar la configuración, pero hay demasiados eventos sucediendo

Si recibe un mensaje al iniciar un evento en el que se indica que se ha alcanzado el número máximo de eventos, póngase en contacto con un administrador de Teams, que tiene la capacidad de detener otros eventos para liberar espacio para un evento de prioridad más alta.

### <a name="i-cant-see-producer-view"></a>No puedo ver la vista de productor

1. La vista previa del productor puede tardar unos segundos en aparecer después de haber iniciado el streaming desde el codificador.
1. Asegúrese de que el codificador está conectado a Teams.
1. A veces, puede ser de ayuda actualizar la página en Teams. Es posible que se le pregunte si desea salir de la página; esto no afectará al evento en directo.
1. Algunas redes pueden bloquear el acceso al contenido. Asegúrese de que la configuración de seguridad y firewall de su red permite que el protocolo RTMP y los [dominios necesarios](/microsoft-365/enterprise/urls-and-ip-address-ranges) estén en la lista de permitidos. Puede ayudar a intentar ver si funciona en un entorno de red diferente, independiente de una red corporativa, UNA VPN o una red bloqueada.

### <a name="my-feed-looks-bad-has-poor-quality-or-is-glitchy"></a>Mi fuente se ve mal, tiene mala calidad o no funciona

1. Compruebe el ancho de banda de carga desde el equipo desde el que está insertando la transmisión en directo. El bajo ancho de banda puede provocar caídas de fotogramas, mala calidad o una transmisión de vídeo con aspecto insocuo. Necesita un ancho de banda de carga superior a la velocidad de bits en la que está transmitiendo.
1. Asegúrese de que está usando la configuración recomendada del codificador para Teams. Consulte [Configurar manualmente codificadores para el streaming de eventos en directo en Microsoft Teams](teams-encoder-configuration.md) para obtener más información.
1. Comprueba que el audio o vídeo que se incluye en el codificador no tiene ningún problema. Las fuentes de audio o vídeo de origen enrutadas al codificador podrían tener problemas en sí, lo que daría como resultado una mala experiencia enviada a los visores.
1. Comprueba la carga de LA CPU en el codificador. Es posible que estés agotando la CPU con el contenido de origen o con la velocidad de bits que intentas insertar. Si la carga de CPU es demasiado alta, intente reducir la complejidad de las superposiciones o contenido de fuentes en directo o reduzca la velocidad de transmisión por secuencias.
1. Asegúrate de que el codificador esté actualizado. Si se trata de un codificador de hardware, asegúrate de disponer de las últimas actualizaciones de firmware. Si se trata de un codificador de software, asegúrate de que estás ejecutando la versión más reciente.
1. Intenta restablecer o reiniciar el codificador. Ten en cuenta que, si haces esto durante una transmisión en directo, los visores verán un error durante la reproducción mientras se reinicia el codificador. Después de reiniciar el streaming en directo desde el codificador, los visores tendrán que volver a cargar la página para obtener la transmisión en directo de nuevo.

### <a name="i-ended-my-live-event-from-my-encoder-but-viewers-are-seeing-an-error"></a>He finalizado mi evento en directo desde mi codificador, pero los espectadores ven un error

Selecciona **Detener evento** antes de desconectar el codificador. Si ya has desconectado el codificador, puedes seleccionar **Detener evento**, pero es posible que los visores vean un error.

### <a name="my-viewers-are-seeing-issues"></a>Mis visores están viendo problemas

- Si un único visor está informando de un problema, asegúrese de que el visor tiene suficiente ancho de banda y está en una buena conexión a Internet para ver el evento.
- Si hay varias personas dentro de la misma red que tienen problemas, es posible que esté experimentando problemas relacionados con la congestión de la red. Revise [La distribución de vídeo a escala y supervise el tráfico de red mediante eCDNs con Microsoft Teams](teams-stream-ecdn.md) para ver si puede identificar una solución a su problema.
- Muchas veces, cuando varios visores están viendo un problema, se relaciona realmente con la fuente del codificador.
  - Comprueba que el codificador esté correctamente configurado según las especificaciones descritas en la configuración del codificador y configurado correctamente.
  - Asegúrese de que tiene suficiente ancho de banda de carga para hacer streaming. Puede intentar reducir el ancho de banda desde la salida del codificador.
  - A veces, el restablecimiento del codificador ayuda, pero ten en cuenta que debes mantener la misma configuración cuando vuelvas a conectarte. Es posible que los miembros de la audiencia vean un error o problemas en el evento en directo.

### <a name="i-or-my-viewers-cant-hear-the-video"></a>Yo, o mis lectores, no oigo el vídeo

1. Comprueba que el codificador está enviando audio.
1. Comprueba que el dispositivo de audio esté enchufado.
1. Si está en Windows, asegúrese de que el dispositivo de audio correcto está seleccionado y activado.
1. Si se produjo una interrupción del codificador, es posible que algunos exploradores o dispositivos no puedan recuperar y reproducir el audio correctamente.

> [!NOTE]
> Si ha implementado Microsoft eCDN como su proveedor de distribución de vídeo para eventos en directo, consulte [Solución de problemas de rendimiento de eCDN](/ecdn/troubleshooting/troubleshoot-ecdn-performance-issues) para obtener más información sobre cómo solucionar los problemas de rendimiento de eCDN que pueda estar experimentando.
