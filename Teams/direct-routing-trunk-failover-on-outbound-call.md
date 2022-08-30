---
title: Conmutación por error de tronco en llamadas salientes
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Lea este tema para obtener información sobre cómo controlar las conmutaciones por error de tronco en las llamadas salientes de Teams al controlador de borde de sesión (SBC).
ms.openlocfilehash: 0fa0d452a2611874be570f4e80a746bb07da0163
ms.sourcegitcommit: d7a86b3a72005764c18acb60eedf5163523ffae3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2022
ms.locfileid: "67457140"
---
# <a name="trunk-failover-on-outbound-calls"></a>Conmutación por error de tronco en llamadas salientes

En este tema se describe cómo evitar conmutaciones por error de tronco en llamadas salientes: desde Teams al controlador de borde de sesión (SBC).

## <a name="failover-on-network-errors"></a>Conmutación por error en errores de red

Si un tronco no se puede conectar por cualquier motivo, la conexión con el mismo tronco se intentará desde un centro de datos de Microsoft diferente. El centro de datos podría estar situado en una región geográfica diferente, fuera de la región actual. Es posible que un tronco no esté conectado si se rechaza una conexión, si hay un tiempo de espera de TLS o si hay otros problemas de nivel de red.

Por ejemplo, una conexión podría producir un error si un administrador limita el acceso al SBC solo desde direcciones IP conocidas, pero olvida colocar las direcciones IP de todos los centros de datos de Enrutamiento directo de Microsoft en la lista de Access Control (ACL) de la SBC. 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>Conmutación por error de códigos SIP específicos recibidos del controlador de borde de sesión (SBC)

Si Direct Routing recibe códigos de error SIP 4xx o 6xx en respuesta a una invitación saliente, la llamada se considera completada de forma predeterminada. Saliente significa una llamada desde un cliente de Teams a la red telefónica conmutada (RTC) con el siguiente flujo de tráfico: Cliente de Teams -> enrutamiento directo -> red telefónica SBC -> telefonía.

La lista de códigos SIP puede encontrarse en [RFC del Protocolo de inicio de sesión (SIP).](https://tools.ietf.org/html/rfc3261)

Suponga una situación en la que un SBC respondió en una invitación entrante con el código "408 Request Timeout: El servidor no pudo producir una respuesta dentro de un período de tiempo adecuado, por ejemplo, si no pudo determinar la ubicación del usuario a tiempo. El cliente puede repetir la solicitud sin modificaciones en cualquier momento posterior."

Este SBC en particular podría tener dificultades para conectarse al destinatario de la llamada, quizás debido a un error de configuración de red u otro error. Sin embargo, hay un SBC más en la ruta que podría llegar al destinatario de la llamada.

En el siguiente diagrama, cuando un usuario realiza una llamada a un número de teléfono, hay dos SBCs en la ruta que pueden potencialmente entregar esta llamada. Inicialmente, se selecciona SBC1.contoso.com para la llamada, pero SBC1.contoso.com no puede llegar a una red PTSN debido a un problema de red.
De forma predeterminada, la llamada se completará en este momento. 
 
![Diagrama que muestra que SBC no puede llegar a RTC debido a un problema de red.](media/direct-routing-failover-response-codes1.png)

Hay una SBC más en la ruta que puede potencialmente entregar la llamada.
Si configura el parámetro `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, se intentará el segundo SBC (SBC2.contoso.com en el siguiente diagrama):

![Diagrama que muestra el enrutamiento a la segunda SBC.](media/direct-routing-failover-response-codes2.png)

Establecer el parámetro -FailoverResponseCodes y especificar los códigos le ayuda a ajustar el enrutamiento y evitar posibles problemas cuando un SBC no puede realizar una llamada debido a la red u otros problemas.

Valores predeterminados: 408, 503, 504

