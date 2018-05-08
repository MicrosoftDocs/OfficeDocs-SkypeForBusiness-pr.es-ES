---
title: Enrutamiento entre troncos en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Obtenga información sobre cómo Skype para Business Server Enterprise Voice admite enrutamiento troncal entre granjas.
ms.openlocfilehash: 97a47e44eb86fc35ff13e3a139a3f811f98fe71d
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="inter-trunk-routing-in-skype-for-business-server-2015"></a>Enrutamiento entre troncos en Skype Empresarial Server 2015
 
Obtenga información sobre cómo Skype para Business Server Enterprise Voice admite enrutamiento troncal entre granjas.
  
Skype para Business Server proporciona administración de sesiones básica a través de la compatibilidad de enrutamiento entre troncos. Esto permite Skype para Business Server proporcionar funcionalidades de control de llamada a sistemas de telefonía de nivel inferior. El enrutamiento entre troncos puede interconectar una IP-PBX con una puerta de enlace de la red telefónica conmutada (RTC) para que las llamadas realizadas desde un teléfono de una central de conmutación (PBX) se puedan redirigir a la RTC y las llamadas RTC entrantes se puedan redirigir a un teléfono PBX. De forma similar, Skype para Business Server puede interconnect dos o más sistemas de IP-PBX para que las llamadas se pueden colocar y recibió entre teléfonos PBX de los distintos sistemas de IP-PBX. 
  
La siguiente ilustración muestra Skype para Business Server proporcionando interconectividad entre una puerta de enlace RTC y un IP-PBX.
  
![Diagrama de conexión puerta de enlace RTC/IP-PBX en Lync Server](../../media/inter_trunk01.jpg)
  
En la siguiente figura ilustra Skype para Business Server conectando dos sistemas IP-PBX.
  
![Diagrama de interconexión de los sistemas IP-PAX en Lync Server](../../media/inter_trunk02.jpg)
  

