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
description: Lea este tema para obtener información sobre cómo administrar la conmutación por error del tronco en llamadas salientes de Teams al controlador de borde de sesión (SBC).
ms.openlocfilehash: c88394cba0a98316ac272901a6ab2972e9eaf3c8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836182"
---
# <a name="trunk-failover-on-outbound-calls"></a>Conmutación por error de tronco en llamadas salientes

En este tema se describe cómo evitar la conmutación por error de enlace en llamadas salientes, desde equipos hasta el controlador de borde de sesión (SBC).

## <a name="failover-on-network-errors"></a>Conmutación por error de red

Si, por cualquier motivo, no se puede conectar un tronco, se intentará establecer la conexión con el mismo tronco desde otro centro de recursos de Microsoft. Es posible que un tronco no esté conectado, por ejemplo, si se rechaza una conexión, si hay un tiempo de espera de TLS, o si hay algún otro problema de nivel de red.
Por ejemplo, una conexión podría fallar si un administrador limita el acceso a la SBC solo de direcciones IP conocidas, pero se olvida de colocar las direcciones IP de todos los centros de información de enrutamiento directo de Microsoft en la lista de control de acceso (ACL) de la SBC. 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>Conmutación por error de códigos SIP específicos recibidos del controlador de borde de sesión (SBC)

Si el enrutamiento directo recibe códigos de error de SIP o 6xx, como respuesta a una invitación saliente, la llamada se considera completada de forma predeterminada. Saliente significa una llamada de un cliente de equipo a la red de telefonía pública conmutada (RTC) con el siguiente flujo de tráfico: Teams Client: > enrutamiento directo: > red de telefonía > de SBC-.

La lista de códigos de SIP puede encontrarse en [RFC de protocolo de inicio de sesión (SIP)](https://tools.ietf.org/html/rfc3261).

Asumamos una situación en la que un SBC respondió en una invitación entrante con el código "408 solicitud de tiempo de espera: el servidor no pudo producir una respuesta dentro de un período de tiempo adecuado, por ejemplo, si no puede determinar la ubicación del usuario en el tiempo. El cliente puede repetir la solicitud sin realizar modificaciones en el momento en que lo desee.

Este SBC en particular podría estar teniendo dificultades para conectar con el destinatario; quizás debido a un error de configuración de red o a otro error. Sin embargo, hay un más SBC en la ruta que podría llegar al destinatario.

En el siguiente diagrama, cuando un usuario hace una llamada a un número de teléfono, hay dos SBCs en la ruta que puede entregar esta llamada. Inicialmente, SBC1.contoso.com está seleccionado para la llamada, pero SBC1.contoso.com no puede comunicarse con una red RTC debido a un problema de red.
De forma predeterminada, la llamada se completará en este momento. 
 
![Diagrama que muestra SBC no se puede comunicar con la RTC debido a un problema de red](media/direct-routing-failover-response-codes1.png)

Pero hay otra SBC en la ruta que puede entregar la llamada.
Si configura el parámetro `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, el segundo SBC se intentará--SBC2.contoso.com en el siguiente diagrama:

![Diagrama que muestra el enrutamiento al segundo SBC](media/direct-routing-failover-response-codes2.png)

El establecimiento del parámetro-FailoverResponseCodes y la especificación de códigos le ayuda a ajustar el enrutamiento y evitar posibles problemas cuando una SBC no puede realizar una llamada debido a problemas de red o de otro tipos.

Valores predeterminados: 408, 503, 504

