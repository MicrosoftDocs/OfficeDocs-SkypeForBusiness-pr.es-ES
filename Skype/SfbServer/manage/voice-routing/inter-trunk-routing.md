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
ms.localizationpriority: medium
description: 'Skype Empresarial Server proporciona administración básica de sesiones mediante la compatibilidad con el enrutamiento entre intrusos. '
ms.openlocfilehash: 0e8ed3ab7b72474614011e4b9f7aaf49ffd5160b
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "58730919"
---
# <a name="skype-for-business-server-inter-trunk-routing"></a>Skype Empresarial Server: enrutamiento entre troncos

Skype Empresarial Server proporciona administración básica de sesiones mediante la compatibilidad con el enrutamiento entre intrusos. Esta funcionalidad permite a Skype Empresarial Server funciones de control de llamadas a los sistemas de telefonía descendente. El enrutamiento entre troncos puede interconectar sistemas IP-PBX con una puerta de enlace de red de telefonía conmutada (RTC) pública para que las llamadas realizadas desde un teléfono de central de conmutación PBX se puedan enrutan a la RTC y las llamadas RTC entrantes se puedan enrutar a un teléfono PBX. Del mismo modo, Skype Empresarial Server interconectar dos o más sistemas IP-PBX para que las llamadas se puedan colocar y recibir entre teléfonos PBX desde los diferentes sistemas IP-PBX. 


En la figura siguiente se Skype Empresarial Server proporciona interconectividad entre una puerta de enlace RTC y una IP-PBX.

![Interconectividad entre una puerta de enlace RTC y una IP-PBX.](../../media/pstn-gateway-ip-pbx.jpg)

En la siguiente ilustración se Skype Empresarial Server conexión de dos sistemas IP-PBX.

![Skype Empresarial Server dos sistemas IP-PGX.](../../media/two-ip-pbx-systems.jpg)

