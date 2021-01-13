---
title: Enrutamiento entre troncos en Skype Empresarial Server
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
description: 'Skype Empresarial Server proporciona administración de sesiones básicas a través de la compatibilidad con el enrutamiento entretrunkes. '
ms.openlocfilehash: d509b4f9de489e65ed8443fd1aad92e24363fb55
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814130"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Enrutamiento entre troncos en Skype Empresarial Server

Skype Empresarial Server proporciona administración de sesiones básicas a través de la compatibilidad con el enrutamiento entretrunkes. Esta funcionalidad permite a Skype Empresarial Server proporcionar funcionalidades de control de llamadas a sistemas de telefonía descendente. El enrutamiento entre troncos puede interconectar sistemas IP-PBX con una puerta de enlace de red de telefonía conmutada (RTC) pública para que las llamadas realizadas desde un teléfono de central de conmutación PBX se puedan enrutan a la RTC y las llamadas RTC entrantes se puedan enrutar a un teléfono PBX. Del mismo modo, Skype Empresarial Server puede interconectar dos o más sistemas IP-PBX para que las llamadas se puedan realizar y recibir entre teléfonos PBX desde los diferentes sistemas IP-PBX. 


En la figura siguiente se muestra que Skype Empresarial Server proporciona interconexión entre una puerta de enlace RTC y una IP-PBX.

![Interconectividad entre una puerta de enlace RTC y una IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

En la figura siguiente se muestra cómo Skype Empresarial Server conecta dos sistemas IP-PBX.

![Skype Empresarial Server conectando dos sistemas IP-PGX](../../media/two-ip-pbx-systems.jpg)

