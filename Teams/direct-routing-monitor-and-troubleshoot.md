---
title: Supervisar y solucionar problemas de enrutamiento directo
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo supervisar y solucionar problemas de configuración de enrutamiento directo, incluidos controladores de borde de sesión, componentes de enrutamiento directo y troncos de Telecom.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74a67493fa2f9647e6cd0364bb4c9d6a3c05e48a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121408"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a>Supervisar y solucionar problemas de enrutamiento directo

En este artículo se describe cómo supervisar y solucionar problemas de configuración de enrutamiento directo. 

La capacidad de realizar y recibir llamadas mediante enrutamiento directo implica los siguientes componentes: 

- Controladores de borde de sesión (SBC) 
- Componentes de enrutamiento directo en Microsoft Cloud 
- Troncos de telecomunicaciones 

Si tiene dificultades para solucionar problemas, puede abrir un caso de soporte técnico con su proveedor de SBC o Microsoft. 

Microsoft está trabajando en proporcionar más herramientas para la solución de problemas y la supervisión. Compruebe periódicamente si hay actualizaciones en la documentación. 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>Supervisar la disponibilidad de los controladores de borde de sesión con mensajes de opciones del Protocolo de inicio de sesión (SIP)

Enrutamiento directo usa las opciones SIP enviadas por los controladores de borde de sesión para supervisar el estado de SBC. No se requieren acciones del administrador de inquilinos para habilitar la supervisión de opciones SIP. La información recopilada se tiene en cuenta al tomar decisiones de enrutamiento. 

Por ejemplo, si, para un usuario específico, hay varios SBC disponibles para enrutar una llamada, Enrutamiento directo considera la información de opciones SIP recibida de cada SBC para determinar el enrutamiento. 

En el siguiente diagrama se muestra un ejemplo de la configuración: 

![Ejemplo de configuración de opciones SIP](media/sip-options-config-example.png)

Cuando un usuario realiza una llamada al número +1 425, \<any seven digits> Enrutamiento directo evalúa la ruta. Hay dos SBC en la ruta: sbc1.contoso.com y sbc2.contoso.com. Ambos SBC tienen la misma prioridad en la ruta. Antes de elegir un SBC, el mecanismo de enrutamiento evalúa el estado de los SBC en función de cuándo el SBC envió las opciones SIP la última vez. 

Un SBC se considera correcto si las estadísticas en el momento de enviar la llamada muestran que el SBC envía opciones cada minuto.  

Cuando se realiza una llamada, se aplica la siguiente lógica:

- El SBC se emparejaba a las 11:00 a.m.  
- El SBC envía opciones a las 11:01 a.m., 11:02 a.m., y así sucesivamente.  
- A las 11:15, un usuario realiza una llamada y el mecanismo de enrutamiento selecciona este SBC. 

Enrutamiento directo toma las opciones de intervalo regular tres veces (el intervalo normal es de un minuto). Si las opciones se enviaron durante los últimos tres minutos, el SBC se considera correcto.

Si el SBC del ejemplo envió opciones en cualquier período entre las 11:12 a.m. y las 11:15 a.m. (la hora en que se realizó la llamada), se considera que está en buen estado. Si no es así, el SBC se degradará de la ruta. 

La degradación significa que el SBC no se probará primero. Por ejemplo, hemos sbc1.contoso.com y sbc2.contoso.com con la misma prioridad.  

Si sbc1.contoso.com no envía opciones SIP en un intervalo regular como se ha descrito anteriormente, se degrada. A continuación, sbc2.contoso.com la llamada. Si sbc2.contoso.con no puede realizar la llamada, el sbc1.contoso.com (degradado) se vuelve a intentar antes de que se genere un error. 

Si dos (o más) SBC en una ruta se consideran correctos e iguales, se aplica un orden aleatorio Fisher-Yates distribuir las llamadas entre los SBC.

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>Supervisar el panel de Análisis de calidad de llamadas y los registros de SBC 
 
En algunos casos, especialmente durante el emparejamiento inicial, puede haber problemas relacionados con la configuración incorrecta de los SBC o el servicio de enrutamiento directo. 

Puede usar las siguientes herramientas para supervisar la configuración:  
 
- Panel de calidad de llamadas 
- Registros SBC 

El servicio de enrutamiento directo tiene códigos de error muy descriptivos notificados a Análisis de llamadas o a los registros de SBC. 

El Panel de calidad de llamadas proporciona información sobre la calidad y la confiabilidad de las llamadas. Para obtener más información sobre cómo solucionar problemas con El análisis de llamadas, vea Activar y usar el panel de calidad de llamadas para Microsoft Teams y [Skype Empresarial Online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) y Usar El análisis de llamadas para solucionar problemas de mala calidad de [llamada.](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) 

En caso de errores de llamada, Análisis de llamadas proporciona códigos SIP estándar para ayudarle con la solución de problemas. 

![Código SIP de ejemplo para errores de llamada](media/failed-response-code.png)

Sin embargo, Análisis de llamadas solo puede ayudar cuando las llamadas llegan a los componentes internos de Enrutamiento directo y fallan. En caso de problemas con el emparejamiento SBC o problemas en los que se rechazó la opción "Invitar" sip (por ejemplo, el nombre del FQDN del tronco está mal configurado), Análisis de llamadas no le ayudará. En este caso, consulte los registros de SBC. Enrutamiento directo envía una descripción detallada de los problemas a los SBC; estos problemas se pueden leer en los registros de SBC.