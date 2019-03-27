---
title: Informe de detalles de llamadas en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38862e35-3fec-41b9-a035-0b301942d446
description: 'Resumen: Información sobre el informe de detalles de llamadas usadas en Skype para Business Server.'
ms.openlocfilehash: a0b0836099e1181a25b95bf7adbbe603ef7d5e5f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887655"
---
# <a name="call-detail-report-in-skype-for-business-server"></a>Informe de detalles de llamadas en Skype para Business Server
 
**Resumen:** Obtenga información sobre el informe de detalles de llamadas usadas en Skype para Business Server.
  
El informe de detalles de llamadas proporciona una visión detallada de una llamada individual; el informe incluye casi todas la calidad de la experiencia métricas y las estadísticas recopiladas por Skype para Business Server, se divide en las secciones de informes, como:
  
- Información de llamada 
    
- Métricas de dispositivo y señal del autor de la llamada
    
- Métricas de dispositivo y señal del destinatario de la llamada
    
- Evento de cliente de autor de la llamada
    
- Evento de cliente de destinatario de la llamada
    
- Secuencia de audio (del autor al destinatario de la llamada)
    
- Secuencia de vídeo (del autor al destinatario de la llamada)
    
- Secuencia de audio (del destinatario al autor de la llamada)
    
- Secuencia de vídeo (del destinatario al autor de la llamada)
    
Tenga en cuenta que las categorías y las métricas que se muestran en los informes depende de dos cosas: el tipo de sesión y el tipo de extremo utilizado en la sesión. Por ejemplo, no se mostrarán métricas de secuencias de vídeos en llamadas solo de audio, ya que la llamada no tiene ninguna secuencia de vídeo. Del mismo modo, puede que tenga un informe en el que solo se muestren estadísticas del autor de la llamada y no del destinatario. Ello se debe a que el destinatario de la llamada no estaba utilizando ningún dispositivo compatible con SIP. Los extremos son responsables de informar de las estadísticas al final de la llamada; pero, un teléfono móvil (que no usa SIP ni estadísticas SIP) no puede informar de este tipo de información. Por ello, si llama a alguien que responde con un teléfono móvil, obtendrá un informe de dicho teléfono móvil cuando finalice la llamada.
  
El Informe de detalles de llamadas resulta de gran utilidad para determinar exactamente por qué se han registrado problemas de calidad multimedia en una llamada determinada.
  
## <a name="accessing-the-call-detail-report"></a>Acceso al Informe de detalles de llamadas

Es posible tener acceso al Informe de detalles de llamadas desde cualquiera de los informes siguientes:
  
- [Ubicación informe en Skype para Business Server (ubicación-report.md) (haciendo clic en el volumen de llamadas o la métrica porcentaje de llamadas deficientes)
    
- El [Media Quality Summary Report en Skype para Business Server (summary.md) (haciendo clic en el volumen de llamadas o la métrica porcentaje de llamadas deficientes)
    
- El [Informe de comparación de calidad de medios en Skype para Business Server](comparison.md) (haciendo clic en el [Informe de lista de llamadas en Skype para Business Server](call-list-report-0.md) y, a continuación, haga clic en la métrica detalles).
    
- El [Informe de rendimiento del servidor en Skype para Business Server](server-performance.md) (haciendo clic en el volumen de llamadas o la métrica porcentaje de llamadas deficientes)
    
- El [Informe de lista de llamadas en Skype para Business Server](call-list-report-0.md) (haciendo clic en la métrica detalles)
    
Desde el informe de detalles de llamadas, puede acceder al [Informe de dispositivos en Skype para Business Server](device-report.md) haciendo clic en cualquiera de las métricas siguientes:
  
- Dispositivo de captura
    
- Dispositivo de presentación
    
También se puede tener acceso al Informe de tendencias de calidad de medios de servidor haciendo clic en la métrica del servidor perimetral A/V.
  
## <a name="making-the-best-use-of-the-call-detail-report"></a>Cómo sacar el máximo partido al Informe de detalles de llamadas

El Informe de detalles de llamadas incluye más de 250 métricas distintas e incluye elementos como, por ejemplo, el Desfase de marca de tiempo de micrófono, el Tiempo de SNR bajo y el Tiempo de extremo próximo a eco. Si no recuerda qué miden todas estas métricas, coloque el mouse sobre la etiqueta de la métrica para que se muestre información de descripción.
  
Si tiene problemas para encontrar una métrica, escriba una parte del nombre de la métrica en el cuadro de búsqueda y haga clic en **Buscar**. Por ejemplo, si no encuentra la métrica Tiempo de SNR bajo, escriba SNR en el cuadro de búsqueda y, a continuación, haga clic en **Buscar**.
  
Tenga en cuenta que el informe solo sigue la información de una llamada. La llamada propiamente dicha no queda registrada.
  
## <a name="filters"></a>Filtros

Ninguno. No se puede filtrar el informe de detalles de llamadas.
  
## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información que recoge el informe de detalles de llamadas sobre cada llamada.
  
**Métricas del informe de detalles de llamadas**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**PAI de autor de la llamada** <br/> |No  <br/> |P-Asserted-Identity del usuario que inició la llamada. P-Asserted-Identity se utiliza para transmitir la identidad demostrada de un usuario en una red de confianza.  <br/> |
|**URI de autor de la llamada** <br/> |No  <br/> |Dirección SIP del usuario que inició la llamada.  <br/> |
|**Extremo de autor de la llamada** <br/> |No  <br/> |Dispositivo usado para realizar la llamada.  <br/> |
|**Agente de usuario de autor de la llamada** <br/> |No  <br/> |Software usado en el dispositivo que realizó la llamada.  <br/> |
|**Inicio de la llamada** <br/> |No  <br/> |Fecha y hora en las que se realizó inicialmente la llamada.  <br/> |
|**Llamada sin pasar por el servidor de mediación** <br/> |No  <br/> |Indica si la llamada se conectó a una puerta de enlace de voz RTC o a un IP PBX cualificado sin pasar por el servidor de mediación.  <br/> |
|**Sistema operativo del autor de la llamada** <br/> |No  <br/> |Sistema operativo del equipo del autor de la llamada.  <br/> |
|**CPU de autor de la llamada** <br/> |No  <br/> |CPU instalada en el equipo del usuario que inició la llamada.  <br/> |
|**Número de núcleo de CPU de autor de la llamada** <br/> |No  <br/> |Número de procesador del equipo usado por la persona que inició la llamada.  <br/> |
|**Velocidad de CPU de autor de la llamada** <br/> |No  <br/> |Velocidad del procesador de la CPU del equipo usado por la persona que inició la llamada.  <br/> |
|**Virtualización de CPU de autor de la llamada** <br/> |No  <br/> |Virtualización (si la hay) usada en el equipo de la persona que inició la llamada.  <br/> |
|**PAI de destinatario de la llamada** <br/> |No  <br/> |P-Asserted-Identity del usuario invitado a unirse a la llamada. P-Asserted-Identity se utiliza para transmitir la identidad demostrada de un usuario en una red de confianza.  <br/> |
|**URI de destinatario de la llamada** <br/> |No  <br/> |Dirección SIP del usuario que recibió la llamada.  <br/> |
|**Extremo de destinatario de la llamada** <br/> |No  <br/> |Dispositivo usado para recibir la llamada.  <br/> |
|**Agente de usuario de destinatario de la llamada** <br/> |No  <br/> |Software usado en el dispositivo que recibió la llamada.  <br/> |
|**Duración** <br/> |No  <br/> |Duración de la llamada.  <br/> |
|**Marcador de advertencia de desvío de medios** <br/> |No  <br/> |Advertencia emitida cuando se ignora el servidor de mediación.  <br/> |
|**Sistema operativo del destinatario de la llamada** <br/> |No  <br/> |Sistema operativo del equipo del usuario que recibió la llamada.  <br/> |
|**CPU de destinatario de la llamada** <br/> |No  <br/> |CPU instalada en el equipo del usuario que recibió la llamada.  <br/> |
|**Número de núcleo de destinatario de la llamada** <br/> |No  <br/> |Número de procesador del equipo usado por la persona que recibió la llamada.  <br/> |
|**Velocidad de CPU de destinatario de la llamada** <br/> |No  <br/> |Velocidad del procesador de la CPU del equipo usado por la persona que recibió la llamada.  <br/> |
|**Virtualización de CPU de destinatario de la llamada** <br/> |No  <br/> |Virtualización (si la hay) usada en el equipo de la persona que recibió la llamada.  <br/> |
   

