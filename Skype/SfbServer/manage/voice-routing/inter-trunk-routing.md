---
title: Enrutamiento entre troncales en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype empresarial Server proporciona administración de sesiones básica mediante la compatibilidad con el enrutamiento de intertroncalización. '
ms.openlocfilehash: c3381c6ae6bd86c416e6bd3349cf54d6fb530a08
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816970"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Enrutamiento entre troncales en Skype empresarial Server

Skype empresarial Server proporciona administración de sesiones básica mediante la compatibilidad con el enrutamiento de intertroncalización. Esta capacidad permite que Skype empresarial Server ofrezca funcionalidades funcionales de control de llamadas a sistemas de telefonía indirectos. El enrutamiento entre troncos puede interconectar una IP-PBX con una puerta de enlace de la red telefónica conmutada (RTC) para que las llamadas realizadas desde un teléfono de una central de conmutación (PBX) se puedan redirigir a la RTC y las llamadas RTC entrantes se puedan redirigir a un teléfono PBX. De forma similar, Skype empresarial Server puede interconectar dos o más sistemas IP-PBX para que las llamadas se puedan realizar y recibir entre los teléfonos PBX de los diferentes sistemas IP-PBX. 


En la ilustración siguiente se muestra cómo Skype empresarial Server proporciona interconectividad entre una puerta de enlace PSTN y una IP-PBX.

![Interconectividad entre una puerta de enlace PSTN y una IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

En la siguiente ilustración se muestra cómo Skype empresarial Server conecta dos sistemas IP-PBX.

![Skype empresarial Server que conecta dos sistemas IP-PGX](../../media/two-ip-pbx-systems.jpg)

