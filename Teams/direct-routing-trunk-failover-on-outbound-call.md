---
title: Conmutación por error de tronco en llamadas salientes
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Lea este tema para obtener información sobre cómo controlar las conmutación por error en las llamadas salientes desde Teams al controlador de borde de sesión (SBC).
ms.openlocfilehash: c88394cba0a98316ac272901a6ab2972e9eaf3c8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836182"
---
# <a name="trunk-failover-on-outbound-calls"></a>Conmutación por error de tronco en llamadas salientes

En este tema se describe cómo evitar conmutación por error en las llamadas salientes desde Teams al controlador de borde de sesión (SBC).

## <a name="failover-on-network-errors"></a>Conmutación por error en errores de red

Si, por algún motivo, no se puede conectar un tronco, se probará la conexión con el mismo tronco desde otro centro de datos de Microsoft. Es posible que un tronco no esté conectado, por ejemplo, si se rechaza una conexión, si se sobresalte el tiempo de espera de TLS o si hay otros problemas de nivel de red.
Por ejemplo, una conexión puede fallar si un administrador limita el acceso a la SBC solo desde direcciones IP conocidas, pero se olvida de poner las direcciones IP de todos los centros de datos de enrutamiento directo de Microsoft en la lista de control de acceso (ACL) de la SBC. 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>Conmutación por error de códigos SIP específicos recibidos del controlador de borde de sesión (SBC)

Si el enrutamiento directo recibe códigos de error 4xx o 6xx SIP en respuesta a una invitación saliente, la llamada se considerará completada de forma predeterminada. Saliente significa una llamada desde un cliente de Teams a la red telefónica conmutada (RTC) con el siguiente flujo de tráfico: Cliente de Teams -> Enrutamiento directo -> SBC -> Telefonía móvil.

La lista de códigos SIP se encuentra en RFC del Protocolo de inicio de [sesión (SIP).](https://tools.ietf.org/html/rfc3261)

Suponga una situación en la que un SBC respondió en una invitación entrante con el código "Tiempo de espera de la solicitud 408: El servidor no pudo producir una respuesta en un período de tiempo adecuado, por ejemplo, si no podía determinar la ubicación del usuario a tiempo. El cliente PUEDE repetir la solicitud sin modificarla en cualquier momento posterior".

Es posible que esta SBC en particular tenga dificultades para conectarse al destinatario de la llamada, quizás debido a un error de configuración de la red u otro error. Sin embargo, hay otro SBC en la ruta que podría llegar al destinatario.

En el siguiente diagrama, cuando un usuario realiza una llamada a un número de teléfono, hay dos sbcs en la ruta que puede llegar a entregar esta llamada. Al principio, SBC1.contoso.com seleccionado para la llamada, SBC1.contoso.com no puede alcanzar una red PTSN debido a un problema de red.
De forma predeterminada, la llamada se completará en este momento. 
 
![Diagrama que muestra que SBC no puede llegar a RTC debido a un problema de red](media/direct-routing-failover-response-codes1.png)

Sin embargo, hay otro SBC más en la ruta que podría entregar la llamada.
Si configura el parámetro, se `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"` probará el segundo SBC SBC2.contoso.com en el siguiente diagrama:

![Diagrama que muestra el enrutamiento a un segundo SBC](media/direct-routing-failover-response-codes2.png)

Establecer el parámetro -FailoverResponseCodes y especificar los códigos le ayuda a ajustar el enrutamiento y evitar posibles problemas cuando un SBC no puede realizar una llamada debido a problemas de red u otros.

Valores predeterminados: 408, 503, 504

