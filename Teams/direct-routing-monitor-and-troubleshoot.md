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
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: En este artículo se describe cómo supervisar y solucionar problemas de la configuración de enrutamiento directo.
ms.openlocfilehash: c1cb84cd8ee764c58441ad9d5d33f18b77336a40
ms.sourcegitcommit: 3197f3ffca2b2315be9fd0c702ccc8c87383c893
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2019
ms.locfileid: "35062382"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a>Supervisar y solucionar problemas de enrutamiento directo

En este artículo se describe cómo supervisar y solucionar problemas de la configuración de enrutamiento directo. 

La capacidad de realizar y recibir llamadas mediante enrutamiento directo incluye los siguientes componentes: 

- Controladores de borde de sesión (SBCs) 
- Componentes de enrutamiento directo en la nube de Microsoft 
- Troncos de telecomunicación 

Si tiene dificultades para solucionar problemas, abra un caso de soporte técnico con su proveedor de SBC o Microsoft. 

Microsoft está trabajando en proporcionar más herramientas para la solución de problemas y la supervisión. Consulta la documentación periódicamente para obtener las actualizaciones. 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>Supervisión de la disponibilidad de los controladores de borde de sesión mediante mensajes de opciones de protocolo de inicio de sesión (SIP)

El enrutamiento directo usa las opciones SIP enviadas por los controladores de borde de la sesión para supervisar el estado de SBC. El administrador de inquilinos no necesita acciones para habilitar la supervisión de las opciones del SIP. La información recopilada se toma en consideración cuando se toman decisiones de enrutamiento. 

Por ejemplo, si, para un usuario específico, hay varios SBCs disponibles para enrutar una llamada, enrutamiento directo tiene en cuenta la información de opciones SIP recibida de cada SBC para determinar el enrutamiento. 

En el siguiente diagrama se muestra un ejemplo de la configuración: 

![Ejemplo de configuración de opciones de SIP](media/sip-options-config-example.png)

Cuando un usuario hace una llamada a Number + 1 425 \<, los siete dígitos>, el enrutamiento directo evalúa la ruta. Hay dos SBCs en la ruta: sbc1.contoso.com y sbc2.contoso.com. Tanto SBCs tienen la misma prioridad en la ruta. Antes de elegir un SBC, el mecanismo de enrutamiento evalúa el estado de SBCs según el momento en que la SBC envió las opciones de SIP la última vez. 

Un SBC se considera saludable si las estadísticas en el momento de enviar la llamada muestran que SBC envía opciones de forma regular.  

El enrutamiento directo calcula intervalos regulares al tomar dos veces el promedio cuando el SBC envía opciones antes de hacer la llamada y agregar cinco minutos. 

Por ejemplo, supongamos lo siguiente: 

- Una SBC está configurada para enviar opciones cada minuto. 
- La SBC fue emparejada a 11,00 A.M.  
- El SBC envía las opciones en 11,01 A.M., 11,02 A.M., etc.  
- En 11,15, un usuario realiza una llamada y el mecanismo de enrutamiento selecciona esta SBC. 

Se aplica la siguiente lógica: dos veces el intervalo medio cuando el SBC envía opciones (un minuto más un minuto = dos minutos) más cinco minutos = siete minutos. Este es el valor del intervalo normal para la SBC.
 
Si el SBC de nuestro ejemplo envió opciones en cualquier período comprendido entre 11,08 AM y 11,15 AM (el momento en que se realizó la llamada), se considerará saludable. De lo contrario, se degradará la SBC de la ruta. 

La degradación significa que la SBC no se intentará en primer lugar. Por ejemplo, tenemos sbc1.contoso.com y sbc2.contoso.com con la misma prioridad.  

Si sbc1.contoso.com no envía las opciones de SIP a un intervalo regular según se describe anteriormente, se degradará. A continuación, sbc2.contoso.com intenta la llamada. Si sbc2. contoso. con no puede entregar la llamada, se intentará de nuevo el sbc1.contoso.com (degradado) antes de que se genere un error. 

Si dos (o más) SBCs en una ruta contratada en buen estado y es igual, se aplicará el orden de distrubute de Fisher a yates en las llamadas entre los SBCs.

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>Supervisar los registros del panel de análisis de calidad de llamadas y de SBC 
 
En algunos casos, especialmente durante el emparejamiento inicial, es posible que haya problemas relacionados con la configuración indebido de la configuración de SBCs o del servicio de enrutamiento directo. 

Puede usar las siguientes herramientas para supervisar la configuración:  
 
- Panel de calidad de llamadas 
- Registros de SBC 

El servicio de enrutamiento directo tiene códigos de error muy descriptivos que se han notificado a análisis de llamadas o a los registros de SBC. 

El panel de calidad de llamadas proporciona información sobre la calidad de las llamadas y la fiabilidad. Para obtener más información sobre cómo solucionar problemas con el análisis de llamadas, consulte [activar y usar el panel de calidad de llamadas para Microsoft Teams y Skype empresarial online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) y [usar el análisis de llamadas para solucionar problemas de baja calidad de las llamadas](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality). 

En caso de que se produzcan errores en las llamadas, el análisis de llamadas proporciona códigos SIP estándar para ayudarle a solucionar problemas. 

![Código SIP de ejemplo para error de llamada](media/failed-response-code.png)

Sin embargo, el análisis de llamadas solo puede ayudar cuando las llamadas llegan a los componentes internos del enrutamiento directo y producen errores. En caso de problemas con el emparejamiento de SBC o problemas en los que se rechazó el "invitar" SIP (por ejemplo, el nombre del FQDN de tronco está configurado incorrectamente), el análisis de llamadas no le servirá. En este caso, consulta los registros de SBC. El enrutamiento directo envía una descripción detallada de los problemas al SBCs; estos problemas se pueden leer desde los registros de SBC. 
