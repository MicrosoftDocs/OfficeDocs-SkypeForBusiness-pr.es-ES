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
description: Lea este tema para obtener información sobre cómo controlar las conmutación por error del tronco en las llamadas salientes desde Teams al controlador de borde de sesión (SBC).
ms.openlocfilehash: c88394cba0a98316ac272901a6ab2972e9eaf3c8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836182"
---
# <a name="trunk-failover-on-outbound-calls"></a>Conmutación por error de tronco en llamadas salientes

En este tema se describe cómo evitar las conmutación por error del tronco en las llamadas salientes, desde Teams hasta el controlador de borde de sesión (SBC).

## <a name="failover-on-network-errors"></a>Conmutación por error en errores de red

Si un tronco no se puede conectar por cualquier motivo, la conexión al mismo tronco se probará desde un centro de datos de Microsoft diferente. Es posible que un tronco no esté conectado, por ejemplo, si se rechaza una conexión, si hay un tiempo de espera de TLS o si hay otros problemas de nivel de red.
Por ejemplo, una conexión puede fallar si un administrador limita el acceso al SBC solo desde direcciones IP conocidas, pero se olvida de poner las direcciones IP de todos los centros de datos de Enrutamiento directo de Microsoft en la Lista de control de acceso (ACL) del SBC. 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>Conmutación por error de códigos SIP específicos recibidos desde el controlador de borde de sesión (SBC)

Si enrutamiento directo recibe códigos de error SIP 4xx o 6xx en respuesta a una invitación saliente, la llamada se considera completada de forma predeterminada. Saliente significa una llamada de un cliente de Teams a la red telefónica conmutada (RTC) con el siguiente flujo de tráfico: cliente Teams -> enrutamiento directo -> red de telefonía SBC ->.

La lista de códigos SIP se puede encontrar en RFC del Protocolo de inicio de [sesión (SIP).](https://tools.ietf.org/html/rfc3261)

Suponga una situación en la que un SBC respondió en una invitación entrante con el código "408 Tiempo de espera de solicitud: el servidor no pudo producir una respuesta en un período de tiempo adecuado, por ejemplo, si no pudo determinar la ubicación del usuario a tiempo. El cliente puede repetir la solicitud sin modificaciones más adelante".

Este SBC en particular podría tener dificultades para conectarse al destinatario, quizás debido a un error de configuración de red u otro error. Sin embargo, hay un SBC más en la ruta que podría llegar al destinatario.

En el siguiente diagrama, cuando un usuario realiza una llamada a un número de teléfono, hay dos SBC en la ruta que potencialmente pueden entregar esta llamada. Inicialmente, SBC1.contoso.com está seleccionado para la llamada, pero SBC1.contoso.com no puede llegar a una red PTSN debido a un problema de red.
De forma predeterminada, la llamada se completará en este momento. 
 
![Diagrama que muestra que SBC no puede llegar a RTC debido a un problema de red](media/direct-routing-failover-response-codes1.png)

Pero hay un SBC más en la ruta que potencialmente puede entregar la llamada.
Si configura el parámetro , se probará el segundo `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"` SBC SBC2.contoso.com en el siguiente diagrama:

![Diagrama que muestra el enrutamiento al segundo SBC](media/direct-routing-failover-response-codes2.png)

Establecer el parámetro -FailoverResponseCodes y especificar los códigos le ayuda a ajustar el enrutamiento y evitar posibles problemas cuando un SBC no puede realizar una llamada debido a problemas de red u otros.

Valores predeterminados: 408, 503 y 504

