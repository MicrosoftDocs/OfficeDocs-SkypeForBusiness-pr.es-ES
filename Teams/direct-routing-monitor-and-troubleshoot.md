---
title: Supervisar enrutamiento directo
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo supervisar y solucionar problemas de configuración de enrutamiento directo, incluidos los controladores de borde de sesión, los componentes de enrutamiento directo y los troncos de telecomunicaciones.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 47a86e8dd98cdb86cd698b187b21453daa003b07
ms.sourcegitcommit: 9de6b0b03f433e71fe239d292387eed33c11b531
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2022
ms.locfileid: "67657250"
---
# <a name="monitor-direct-routing"></a>Supervisar enrutamiento directo

En este artículo se describe cómo supervisar y solucionar problemas de configuración de enrutamiento directo. 

La capacidad de realizar y recibir llamadas mediante el enrutamiento directo implica los siguientes componentes: 

- Controladores de borde de sesión (SBCs) 
- Componentes de enrutamiento directo en la nube de Microsoft 
- Troncos de telecomunicaciones 

Si tienes dificultades para solucionar problemas, puedes abrir un caso de soporte técnico con tu proveedor de SBC o Microsoft. 

Microsoft está trabajando para proporcionar más herramientas de solución de problemas y supervisión. Consulta periódicamente la documentación para ver si hay actualizaciones. 

## <a name="troubleshoot-direct-routing"></a>Solucionar problemas de enrutamiento directo

Para solucionar problemas de enrutamiento directo, consulte [Diagnosticar problemas con enrutamiento directo](/MicrosoftTeams/troubleshoot/phone-system/direct-routing/diagnose-direct-routing-issues).

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>Supervisar la disponibilidad de los controladores de borde de sesión mediante mensajes de opciones de Protocolo de inicio de sesión (SIP)

El enrutamiento directo usa opciones SIP enviadas por los controladores de borde de sesión para supervisar el estado de SBC. El administrador de inquilinos no requiere ninguna acción para habilitar la supervisión de opciones SIP. La información recopilada se tiene en cuenta al tomar decisiones de enrutamiento. 

Por ejemplo, si, para un usuario específico, hay varios SBCs disponibles para enrutar una llamada, enrutamiento directo considera la información de opciones SIP recibida de cada SBC para determinar el enrutamiento. 

El siguiente diagrama muestra un ejemplo de la configuración: 

![Ejemplo de configuración de opciones SIP.](media/sip-options-config-example.png)

Cuando un usuario realiza una llamada al número +1 425 \<any seven digits>, el Enrutamiento directo evalúa la ruta. Hay dos SBCs en la ruta: sbc1.contoso.com y sbc2.contoso.com. Ambos SCA tienen la misma prioridad en la ruta. Antes de elegir un SBC, el mecanismo de enrutamiento evalúa el estado de los SBCs en función de cuándo el SBC envió las opciones sip por última vez. 

Un SBC se considera correcto si las estadísticas en el momento de enviar la llamada muestran que el SBC envía opciones cada minuto.  

Cuando se realiza una llamada, se aplica la siguiente lógica:

- El SBC fue emparejado a las 11:00 AM.  
- El SBC envía opciones a las 11:01 AM, 11:02 AM y así sucesivamente.  
- A las 11:15, un usuario realiza una llamada y el mecanismo de enrutamiento selecciona este SBC. 

Direct Routing toma las opciones de intervalo regular tres veces (el intervalo normal es un minuto). Si se enviaron opciones durante los últimos tres minutos, el SBC se considera correcto.

Si el SBC del ejemplo envió opciones en cualquier período entre las 11:12 y las 11:15 (la hora en que se realizó la llamada), se considera correcto. Si no es así, el SBC disminuirá de la ruta. 

Demotion significa que el SBC no será probado primero. Por ejemplo, tenemos sbc1.contoso.com y sbc2.contoso.com con la misma prioridad.  

Si sbc1.contoso.com no envía opciones sip en un intervalo regular como se describió anteriormente, se degrada. A continuación, sbc2.contoso.com intenta realizar la llamada. Si sbc2.contoso.con no puede realizar la llamada, la sbc1.contoso.com (degradada) se vuelve a intentar antes de que se genere un error. 

Si dos (o más) SBCs en una ruta se consideran saludables e iguales, se aplica Fisher-Yates orden aleatorio para distribuir las llamadas entre los S SBCs.

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>Supervisar el panel de análisis de calidad de llamadas y los registros de SBC 
 
En algunos casos, especialmente durante el emparejamiento inicial, puede haber problemas relacionados con la configuración incorrecta de los SCS o del servicio de enrutamiento directo. 

Puede usar las siguientes herramientas para supervisar la configuración:  
 
- Panel de calidad de llamadas 
- Registros SBC 

El servicio de enrutamiento directo tiene códigos de error descriptivos notificados a Análisis de llamadas o a los registros de SBC.

El panel de calidad de llamadas proporciona información sobre la calidad y confiabilidad de las llamadas. Para obtener más información sobre cómo solucionar problemas con Análisis de llamadas, consulte [Activar y usar el panel de calidad de llamadas para Microsoft Teams y Skype Empresarial Online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) y [Usar análisis de llamadas para solucionar problemas de mala calidad de llamadas](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality). 

En caso de errores de llamada, Análisis de llamadas proporciona códigos SIP estándar para ayudarle con la solución de problemas. 

![Ejemplo de código SIP para error de llamada.](media/failed-response-code.png)

Sin embargo, análisis de llamadas solo puede ayudar cuando las llamadas llegan a los componentes internos del enrutamiento directo y fallan. En caso de problemas con el emparejamiento SBC o problemas en los que se rechazó la "invitación" sip (por ejemplo, el nombre del FQDN del tronco está mal configurado), Análisis de llamadas no ayudará. En este caso, refiera a los registros SBC. Direct Routing envía una descripción detallada de los problemas a los SBCs; estos problemas se pueden leer desde los registros de SBC.
