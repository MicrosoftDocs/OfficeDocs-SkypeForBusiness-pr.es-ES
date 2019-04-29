---
title: Supervisar y solucionar problemas de enrutamiento directo
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: En este artículo se describe cómo supervisar y solucionar problemas de la configuración de enrutamiento directo.
ms.openlocfilehash: e21d3e020f477fd1518017e0d6fc484e7ea10344
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "33402449"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a>Supervisar y solucionar problemas de enrutamiento directo

En este artículo se describe cómo supervisar y solucionar problemas de la configuración de enrutamiento directo. 

La capacidad de realizar y recibir llamadas mediante el uso de enrutamiento directo implica los siguientes componentes: 

- Controladores de borde de sesión (SBCs) 
- Componentes de enrutamiento directos en el Microsoft Cloud 
- Troncos de telecomunicaciones 

Si tiene dificultades para solución de problemas, abra un caso de soporte con el proveedor SBC o Microsoft. 

Microsoft está trabajando en proporcionar más herramientas de supervisión y solución de problemas. Compruebe la documentación de forma periódica para obtener actualizaciones. 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>Supervisar la disponibilidad de controladores de borde de sesión mediante mensajes de las opciones de protocolo de inicio de sesión (SIP)

Enrutamiento directo usa opciones de SIP enviadas por los controladores de borde de sesión para supervisar el estado SBC. No hay ninguna acción necesaria desde el Administrador de inquilinos para habilitar la supervisión de las opciones de SIP. La información recopilada se toma en cuenta cuando se toman las decisiones de enrutamiento. 

Por ejemplo, si, para un usuario específico, hay varias SBCs disponibles para enrutar una llamada, el enrutamiento directo considera que la información de opciones de SIP recibida desde cada SBC para determinar el enrutamiento. 

En el siguiente diagrama muestra un ejemplo de la configuración: 

![Ejemplo de configuración de opciones de SIP](media/sip-options-config-example.png)

Cuando un usuario realiza una llamada al número +1 425 \<cualquier digits> siete, enrutamiento directo da como resultado la ruta. Hay dos SBCs en la ruta: sbc1.contoso.com y sbc2.contoso.com. Ambos SBCs tienen la misma prioridad en la ruta. Antes de seleccionar un SBC, el mecanismo de enrutamiento, se evalúa como el mantenimiento de la SBCs según cuando la SBC envía las opciones de SIP por última vez. 

Un SBC se considera correcto si las estadísticas en el momento del envío de la llamada se muestran que el SBC envía las opciones en un intervalo regular.  

Enrutamiento directo calcula intervalos regulares siguiendo dos veces el promedio cuando la SBC envía opciones antes de realizar la llamada y adición de cinco minutos. 

Por ejemplo, se supone lo siguiente: 

- Un SBC está configurado enviar las opciones de cada minuto. 
- Se ha emparejado el SBC a las 11:00 de la AM.  
- La SBC envía las opciones de 11.01 AM, 11.02 AM y así sucesivamente.  
- En 11.15, un usuario realiza una llamada y el mecanismo de enrutamiento selecciona este SBC. 

Se aplica la lógica siguiente: dos veces el intervalo promedio cuando la SBC envía opciones (de un minuto más de un minuto = dos minutos) plus cinco minutos = siete minutos. Éste es el valor del intervalo regular para la SBC.
 
Si la SBC en nuestro ejemplo envía las opciones en cualquier período entre 11:08 A.M. y 11:15 A.M. (el tiempo que se realizó la llamada), se considera correcto. En caso contrario, se degradará la SBC desde la ruta. 

Disminución de nivel significa que la SBC no se intentará en primer lugar. Por ejemplo, tenemos sbc1.contoso.com y sbc2.contoso.com con la misma prioridad.  

Si sbc1.contoso.com no envía las opciones de SIP en un intervalo regular como se describió anteriormente, se degrada. A continuación, se intenta sbc2.contoso.com para la llamada. Si sbc2.contoso.con no puede entregar la llamada, el sbc1.contoso.com (cuyo nivel ha disminuido) se volverá a intentar antes de que se genere un error. 

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>Supervise el panel de análisis de calidad de llamadas y los registros SBC 
 
En algunos casos, especialmente durante el emparejamiento inicial, puede haber problemas relacionados con una configuración incorrecta de la SBCs o el servicio de enrutamiento directo. 

Puede usar las siguientes herramientas para supervisar la configuración:  
 
- Panel de calidad de llamadas 
- Registros SBC 

El servicio de enrutamiento directo tiene códigos de error muy descriptivo que se notifiquen al análisis de llamadas o los registros de SBC. 

El panel de calidad de llamadas proporciona información acerca de la calidad de la llamada y la confiabilidad. Para obtener más información acerca de cómo solucionar problemas con el análisis de llamadas, vea [activar y con el panel de calidad de llamadas para los equipos de Microsoft y Skype para profesionales en línea](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) y [Análisis de uso de llamadas para solucionar problemas de calidad de la llamada deficiente](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality). 

En el caso de errores de llamadas, llamada análisis proporciona códigos de SIP estándar para ayudarle a solucionar problemas. 

![Código de error de llamada SIP de ejemplo](media/failed-response-code.png)

Sin embargo, solo puede ayudar llamar análisis cuando las llamadas llegar a los componentes internos de enrutamiento directo y se producirá un error. En caso de problemas con el emparejamiento SBC o donde se rechazó SIP "Invitar" (por ejemplo, el nombre del tronco que FQDN está mal configurado), no le ayudará llamar a análisis. En este caso, consulte los registros de SBC. Enrutamiento directo envía una descripción detallada de los problemas a la SBCs; estos problemas se pueden leer desde los registros de SBC. 
