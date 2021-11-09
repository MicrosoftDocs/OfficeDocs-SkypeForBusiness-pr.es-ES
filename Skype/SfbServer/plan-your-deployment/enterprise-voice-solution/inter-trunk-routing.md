---
title: Acerca del enrutamiento entre troncos en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Obtenga información sobre Skype Empresarial Server Telefonía IP empresarial admite el enrutamiento entre troncos.
ms.openlocfilehash: 16a67af73db89f884f797c24123b984d3eb87789
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855417"
---
# <a name="about-inter-trunk-routing-in-skype-for-business-server"></a>Acerca del enrutamiento entre troncos en Skype Empresarial Server
 
Obtenga información sobre Skype Empresarial Server Telefonía IP empresarial admite el enrutamiento entre troncos.
  
Skype Empresarial Server proporciona administración básica de sesiones mediante la compatibilidad con el enrutamiento entre intrusos. Esto permite Skype Empresarial Server funciones de control de llamadas a los sistemas de telefonía descendente. El enrutamiento entre troncos puede interconectar sistemas IP-PBX con una puerta de enlace de red de telefonía conmutada (RTC) pública para que las llamadas realizadas desde un teléfono de central de conmutación PBX se puedan enrutan a la RTC y las llamadas RTC entrantes se puedan enrutar a un teléfono PBX. Del mismo modo, Skype Empresarial Server interconectar dos o más sistemas IP-PBX para que las llamadas se puedan colocar y recibir entre teléfonos PBX desde los diferentes sistemas IP-PBX. 
  
En la figura siguiente se Skype Empresarial Server proporciona interconectividad entre una puerta de enlace RTC y una IP-PBX.
  
![Lync Server que conecta el diagrama de puerta de enlace RTC/IP-PBX.](../../media/inter_trunk01.jpg)
  
En la siguiente ilustración se Skype Empresarial Server conexión de dos sistemas IP-PBX.
  
![Diagrama de sistemas IP-PAX de interconexión de Lync Server.](../../media/inter_trunk02.jpg)
  

