---
title: Conmutación por error de tronco en llamadas salientes
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Lea este tema para obtener información sobre cómo controlar las conmutaciones por error de tronco en las llamadas salientes desde los equipos para el controlador de borde de sesión (SBC).
ms.openlocfilehash: b2da454097fcb0f0af91aefad987d195e9e0f912
ms.sourcegitcommit: ee3f79ce1b6da0885e1096f9fba894bcff1814da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/25/2019
ms.locfileid: "33298559"
---
# <a name="trunk-failover-on-outbound-calls"></a>Conmutación por error de tronco en llamadas salientes

En este tema se describe cómo evitar tronco conmutaciones por error en las llamadas salientes--desde los equipos para el controlador de borde de sesión (SBC).

## <a name="failover-on-network-errors"></a>Conmutación por error en los errores de red

Si no se puede conectar un tronco por cualquier motivo, se intentará la conexión con el mismo tronco desde un Microsoft Datacenter diferentes. Un tronco que no esté conectado, por ejemplo, si se ha rechazado una conexión si no hay un tiempo de espera TLS, o si hay otros problemas de nivel de red.
Por ejemplo, una conexión puede producirse un error si un administrador limita el acceso a la SBC únicamente desde las direcciones IP conocidas, pero se olvida poner las direcciones IP de todos los centros de datos enrutamiento directo de Microsoft en la lista de Control de acceso (ACL) de la SBC. 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>Conmutación por error de códigos específicos de SIP recibidos desde el controlador de borde de sesión (SBC)

Si el enrutamiento directo recibe los códigos de error 4xx o 6xx SIP en respuesta a una invitación saliente, la llamada se considera completada de forma predeterminada. Saliente significa una llamada desde un cliente de los equipos a la pública teléfono red conmutada (RTC) con el siguiente flujo de tráfico: los equipos cliente-> enrutamiento directo-> SBC-red de telefonía de >.

La lista de códigos de SIP puede encontrarse en el [Protocolo de inicio de sesión (SIP) RFC](https://tools.ietf.org/html/rfc3261).

Se supone una situación donde un SBC respondió una invitación entrante con el código "408 tiempo de espera de solicitud: el servidor no puede crear una respuesta dentro de una cantidad adecuada de tiempo, por ejemplo, si no puede determinar la ubicación del usuario en el tiempo. El cliente puede repetir la solicitud sin modificaciones en cualquier momento."

Es posible que tenga las dificultades de conexión con el destinatario de la llamada--quizás debido a un error de configuración de red o a otro error este SBC determinada. Sin embargo, hay una SBC más en la ruta que es posible que pueda ponerse en contacto con el destinatario de la llamada.

En el diagrama siguiente, cuando un usuario realiza una llamada a un número de teléfono, hay dos SBCs en la ruta que puede suministrar esta llamada. Inicialmente, se selecciona SBC1.contoso.com para la llamada, pero SBC1.contoso.com no puede ponerse en contacto con una red PTSN debido a un problema de red.
De forma predeterminada, la llamada se completará en este momento. 
 
![Muestra SBC no puede alcanzar RTC debido a problemas de red](media/direct-routing-failover-response-codes1.png)

Pero hay una SBC más en la ruta que potencialmente puede ofrecer la llamada.
Si configura el parámetro `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, se intentará la segunda SBC--SBC2.contoso.com en el siguiente diagrama:

![Muestra el enrutamiento al segundo SBC](media/direct-routing-failover-response-codes2.png)

Si se establece el parámetro - FailoverResponseCodes y especificando los códigos de le ayuda a no pasa nada, ajuste el enrutamiento y evitar posibles problemas cuando un SBC no puede realizar una llamada debido a la red u otros problemas.

Valores predeterminados: 408, 503, 504

