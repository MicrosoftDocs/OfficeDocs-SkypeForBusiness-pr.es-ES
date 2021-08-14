---
title: 'Skype Empresarial Server: enrutamiento entre troncos'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype Empresarial Server proporciona administración básica de sesiones mediante la compatibilidad con el enrutamiento entre intrusos. '
ms.openlocfilehash: 694fc707711ae804bade0935e0fb9f34e89dbb93
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234375"
---
# <a name="skype-for-business-server-inter-trunk-routing"></a>Skype Empresarial Server: enrutamiento entre troncos

Skype Empresarial Server proporciona administración básica de sesiones mediante la compatibilidad con el enrutamiento entre intrusos. Esta funcionalidad permite a Skype Empresarial Server funciones de control de llamadas a los sistemas de telefonía descendente. El enrutamiento entre troncos puede interconectar sistemas IP-PBX con una puerta de enlace de red de telefonía conmutada (RTC) pública para que las llamadas realizadas desde un teléfono de central de conmutación PBX se puedan enrutan a la RTC y las llamadas RTC entrantes se puedan enrutar a un teléfono PBX. Del mismo modo, Skype Empresarial Server interconectar dos o más sistemas IP-PBX para que las llamadas se puedan colocar y recibir entre teléfonos PBX desde los diferentes sistemas IP-PBX. 


En la figura siguiente se Skype Empresarial Server proporciona interconectividad entre una puerta de enlace RTC y una IP-PBX.

![Interconectividad entre una puerta de enlace RTC y una IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

En la siguiente ilustración se Skype Empresarial Server conexión de dos sistemas IP-PBX.

![Skype Empresarial Server conectar dos sistemas IP-PGX](../../media/two-ip-pbx-systems.jpg)

