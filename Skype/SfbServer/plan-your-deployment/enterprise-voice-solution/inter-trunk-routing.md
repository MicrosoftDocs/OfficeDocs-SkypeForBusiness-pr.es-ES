---
title: Enrutamiento entre troncos en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Obtenga información sobre cómo Skype Empresarial Server Telefonía IP empresarial el enrutamiento entre troncos.
ms.openlocfilehash: fc03f0df530be12ad1d08148850c11d8f92a2791
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825606"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Enrutamiento entre troncos en Skype Empresarial Server
 
Obtenga información sobre cómo Skype Empresarial Server Telefonía IP empresarial el enrutamiento entre troncos.
  
Skype Empresarial Server proporciona administración de sesiones básicas a través de la compatibilidad con el enrutamiento entretrunkes. Esto permite a Skype Empresarial Server proporcionar funcionalidades de control de llamadas a sistemas de telefonía descendente. El enrutamiento entre troncos puede interconectar sistemas IP-PBX con una puerta de enlace de red de telefonía conmutada (RTC) pública para que las llamadas realizadas desde un teléfono de central de conmutación PBX se puedan enrutan a la RTC y las llamadas RTC entrantes se puedan enrutar a un teléfono PBX. Del mismo modo, Skype Empresarial Server puede interconectar dos o más sistemas IP-PBX para que las llamadas se puedan realizar y recibir entre teléfonos PBX desde los diferentes sistemas IP-PBX. 
  
En la figura siguiente se muestra que Skype Empresarial Server proporciona interconexión entre una puerta de enlace RTC y una IP-PBX.
  
![Lync Server que conecta el diagrama de puerta de enlace RTC/IP-PBX](../../media/inter_trunk01.jpg)
  
En la figura siguiente se muestra cómo Skype Empresarial Server conecta dos sistemas IP-PBX.
  
![Diagrama de sistemas IP-DHCP de interconexión de Lync Server](../../media/inter_trunk02.jpg)
  

