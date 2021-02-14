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
description: Obtenga información sobre cómo supervisar y solucionar problemas de configuración de enrutamiento directo, incluidos los controladores de borde de sesión, los componentes de enrutamiento directo y los troncos de telecomunicaciones.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 52ab594b901606ccf7c3b43fc8484d989c248fcd
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "43901915"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a>Supervisar y solucionar problemas de enrutamiento directo

En este artículo se describe cómo supervisar y solucionar problemas de configuración de enrutamiento directo. 

La capacidad para realizar y recibir llamadas mediante enrutamiento directo implica los siguientes componentes: 

- Controlador de borde de sesión (SBCs) 
- Componentes de enrutamiento directo en Microsoft Cloud 
- Telecom trunks 

Si tiene dificultades para solucionar problemas, puede abrir un caso de soporte con su proveedor de SBC o Microsoft. 

Microsoft está trabajando en proporcionar más herramientas para la solución de problemas y la supervisión. Compruebe la documentación periódicamente para ver si hay actualizaciones. 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>Supervisar la disponibilidad de los controladores de borde de sesión mediante los mensajes de opciones del Protocolo de inicio de sesión (SIP)

El enrutamiento directo usa opciones SIP enviadas por los controladores de borde de sesión para supervisar el estado de SBC. No es necesario realizar ninguna acción por parte del administrador de inquilinos para habilitar la supervisión de opciones SIP. La información recopilada se tiene en cuenta al tomar decisiones de enrutamiento. 

Por ejemplo, si hay varios SBC disponibles para enrutar una llamada para un usuario específico, enrutamiento directo tiene en cuenta la información de opciones SIP que se recibe de cada SBC para determinar el enrutamiento. 

El siguiente diagrama muestra un ejemplo de la configuración: 

![Ejemplo de configuración de opciones SIP](media/sip-options-config-example.png)

Cuando un usuario realiza una llamada al número +1 425 cualquiera de los siete dígitos>, enrutamiento directo \< evalúa la ruta. Hay dos sbcs en la ruta: sbc1.contoso.com y sbc2.contoso.com. Ambos SDC tienen la misma prioridad en la ruta. Antes de elegir un SBC, el mecanismo de enrutamiento evalúa el estado de los SBC en función de cuándo la SBC envió las opciones SIP por última vez. 

Un SBC se considera correcto si las estadísticas en el momento de enviar la llamada muestran que la SBC envía opciones cada minuto.  

Cuando se realiza una llamada, se aplica la siguiente lógica:

- La cadena SBC se emparejaba a las 11:00.  
- La SBC envía opciones a las 11:01, a las 11:02 y así sucesivamente.  
- A las 11:15, un usuario realiza una llamada y el mecanismo de enrutamiento selecciona este SBC. 

El enrutamiento directo toma tres veces las opciones de intervalo normal (el intervalo normal es de un minuto). Si las opciones se enviaron durante los últimos tres minutos, la SBC se considera que está en buen estado.

Si la SBC del ejemplo de opciones enviadas en un período entre las 11:12 y las 11:15 (hora en que se realizó la llamada), se considera que está en buen estado. Si no es así, la SBC se degradará de la ruta. 

Democión significa que no se probará la SBC primero. Por ejemplo, tenemos sbc1.contoso.com y sbc2.contoso.com tienen la misma prioridad.  

Si sbc1.contoso.com no envía opciones SIP en un intervalo regular como se describió anteriormente, se degrada. A continuación, sbc2.contoso.com durante la llamada. Si sbc2.contoso.con no puede entregar la llamada, se vuelve a intentar el sbc1.contoso.com (degradado) antes de que se genere un error. 

Si dos (o más) SBC de una ruta se consideran correctos e iguales, Fisher-Yates orden aleatorio se aplica para distribuir las llamadas entre las sbcs.

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>Supervisar los registros SBC y el panel de análisis de calidad de llamadas 
 
En algunos casos, especialmente durante el emparejamiento inicial, puede haber problemas relacionados con la configuración incorrecta de los SBC o el servicio de enrutamiento directo. 

Puede usar las siguientes herramientas para supervisar la configuración:  
 
- Panel de calidad de llamadas 
- Registros SBC 

El servicio de enrutamiento directo tiene códigos de error muy descriptivos que se han notificado a Call Analytics o a los registros SBC. 

El panel de calidad de llamadas proporciona información sobre la calidad y la confiabilidad de las llamadas. Para obtener más información sobre cómo solucionar problemas con Análisis de llamadas, vea Activar y usar el panel de calidad de llamadas para Microsoft Teams y Skype Empresarial [Online,](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) y use El análisis de llamadas para solucionar problemas de calidad de [llamadas deficiente.](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) 

En caso de fallos en la llamada, Análisis de llamadas proporciona códigos SIP estándar para ayudarle a solucionar problemas. 

![Ejemplo de código SIP para un error de llamada](media/failed-response-code.png)

Sin embargo, el análisis de llamadas solo puede ayudarle cuando las llamadas llegan a los componentes internos de Enrutamiento directo y fallan. En caso de problemas con el emparejamiento SBC o problemas en los que se rechazó la "Invitación" SIP (por ejemplo, el nombre del FQDN del tronco está mal configurado), Análisis de llamadas no ayudará. En este caso, consulte los registros SBC. El enrutamiento directo envía una descripción detallada de los problemas a los SBC; estos problemas se pueden leer en los registros de SBC. 
