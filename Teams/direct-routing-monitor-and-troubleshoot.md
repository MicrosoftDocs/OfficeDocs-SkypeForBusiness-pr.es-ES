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
description: Aprenda a supervisar y solucionar problemas de configuración de enrutamiento directo, incluidos los controladores de borde de sesión, los componentes de enrutamiento directo y los troncos de telecomunicaciones.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 52ab594b901606ccf7c3b43fc8484d989c248fcd
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "43901915"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a>Supervisar y solucionar problemas de enrutamiento directo

En este artículo se describe cómo supervisar y solucionar problemas de la configuración de enrutamiento directo. 

La capacidad de realizar y recibir llamadas mediante enrutamiento directo incluye los siguientes componentes: 

- Controladores de borde de sesión (SBCs) 
- Componentes de enrutamiento directo en la nube de Microsoft 
- Troncos de telecomunicación 

Si tiene dificultades para solucionar problemas, puede abrir un caso de soporte técnico con su proveedor de SBC o Microsoft. 

Microsoft está trabajando en proporcionar más herramientas para la solución de problemas y la supervisión. Consulta la documentación periódicamente para obtener las actualizaciones. 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>Supervisión de la disponibilidad de los controladores de borde de sesión mediante mensajes de opciones de protocolo de inicio de sesión (SIP)

El enrutamiento directo usa las opciones SIP enviadas por los controladores de borde de la sesión para supervisar el estado de SBC. El administrador de inquilinos no necesita acciones para habilitar la supervisión de las opciones del SIP. La información recopilada se toma en consideración cuando se toman decisiones de enrutamiento. 

Por ejemplo, si, para un usuario específico, hay varios SBCs disponibles para enrutar una llamada, enrutamiento directo tiene en cuenta la información de opciones SIP recibida de cada SBC para determinar el enrutamiento. 

En el siguiente diagrama se muestra un ejemplo de la configuración: 

![Ejemplo de configuración de opciones de SIP](media/sip-options-config-example.png)

Cuando un usuario hace una llamada a Number + 1 425 \<, los siete dígitos>, el enrutamiento directo evalúa la ruta. Hay dos SBCs en la ruta: sbc1.contoso.com y sbc2.contoso.com. Tanto SBCs tienen la misma prioridad en la ruta. Antes de elegir un SBC, el mecanismo de enrutamiento evalúa el estado de SBCs según el momento en que la SBC envió las opciones de SIP la última vez. 

Un SBC se considera saludable si las estadísticas en el momento de enviar la llamada muestran que el SBC envía opciones cada minuto.  

Cuando se realiza una llamada, se aplica la siguiente lógica:

- La SBC fue emparejada a 11:00 A.M.  
- El SBC envía las opciones en 11:01 A.M., 11:02 A.M., etc.  
- En 11:15, un usuario realiza una llamada y el mecanismo de enrutamiento selecciona esta SBC. 

El enrutamiento directo tiene las opciones de intervalo normal tres veces (el intervalo normal es de un minuto). Si las opciones se enviaron durante los tres últimos minutos, la SBC se considerará saludable.

Si la SBC del ejemplo envió opciones en cualquier período comprendido entre 11:12 AM y 11:15 AM (el momento en que se realizó la llamada), se considerará saludable. De lo contrario, se degradará la SBC de la ruta. 

La degradación significa que la SBC no se intentará en primer lugar. Por ejemplo, tenemos sbc1.contoso.com y sbc2.contoso.com con la misma prioridad.  

Si sbc1.contoso.com no envía las opciones de SIP a intervalos regulares como se ha descrito anteriormente, se degradan. A continuación, sbc2.contoso.com intenta la llamada. Si sbc2. contoso. con no puede entregar la llamada, se intentará de nuevo el sbc1.contoso.com (degradado) antes de que se genere un error. 

Si dos (o más) SBCs en una ruta se consideran en buen estado y son iguales, se aplica el orden de reproducción de Fisher-yates para distribuir las llamadas entre el SBCs.

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>Supervisar los registros del panel de análisis de calidad de llamadas y de SBC 
 
En algunos casos, especialmente durante el emparejamiento inicial, es posible que haya problemas relacionados con la configuración indebido de la configuración de SBCs o del servicio de enrutamiento directo. 

Puede usar las siguientes herramientas para supervisar la configuración:  
 
- Panel de calidad de llamadas 
- Registros de SBC 

El servicio de enrutamiento directo tiene códigos de error muy descriptivos que se han notificado a análisis de llamadas o a los registros de SBC. 

El panel de calidad de llamadas proporciona información sobre la calidad de las llamadas y la fiabilidad. Para obtener más información sobre cómo solucionar problemas con el análisis de llamadas, consulte [activar y usar el panel de calidad de llamadas para Microsoft Teams y Skype empresarial online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) y [usar el análisis de llamadas para solucionar problemas de baja calidad de las llamadas](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality). 

En caso de que se produzcan errores en las llamadas, el análisis de llamadas proporciona códigos SIP estándar para ayudarle a solucionar problemas. 

![Código SIP de ejemplo para error de llamada](media/failed-response-code.png)

Sin embargo, el análisis de llamadas solo puede ayudar cuando las llamadas llegan a los componentes internos del enrutamiento directo y producen errores. En caso de problemas con el emparejamiento de SBC o problemas en los que se rechazó el "invitar" SIP (por ejemplo, el nombre del FQDN de tronco está configurado incorrectamente), el análisis de llamadas no le servirá. En este caso, consulte los registros de SBC. El enrutamiento directo envía una descripción detallada de los problemas al SBCs; estos problemas se pueden leer desde los registros de SBC. 
