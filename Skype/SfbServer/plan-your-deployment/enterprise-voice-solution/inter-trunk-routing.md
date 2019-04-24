---
title: Enrutamiento entre tronco en Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Obtenga información sobre cómo Skype para Business Server Enterprise Voice admite enrutamiento troncal entre granjas.
ms.openlocfilehash: 281e722898655e463c3db281014421ae224c2cec
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207303"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Enrutamiento entre tronco en Skype para Business Server
 
Obtenga información sobre cómo Skype para Business Server Enterprise Voice admite enrutamiento troncal entre granjas.
  
Skype para Business Server proporciona administración de sesiones básica a través de la compatibilidad de enrutamiento entre troncos. Esto permite Skype para Business Server proporcionar funcionalidades de control de llamada a sistemas de telefonía de nivel inferior. El enrutamiento entre troncos puede interconectar una IP-PBX con una puerta de enlace de la red telefónica conmutada (RTC) para que las llamadas realizadas desde un teléfono de una central de conmutación (PBX) se puedan redirigir a la RTC y las llamadas RTC entrantes se puedan redirigir a un teléfono PBX. De forma similar, Skype para Business Server puede interconnect dos o más sistemas de IP-PBX para que las llamadas se pueden colocar y recibió entre teléfonos PBX de los distintos sistemas de IP-PBX. 
  
La siguiente ilustración muestra Skype para Business Server proporcionando interconectividad entre una puerta de enlace RTC y un IP-PBX.
  
![Diagrama de conexión puerta de enlace RTC/IP-PBX en Lync Server](../../media/inter_trunk01.jpg)
  
En la siguiente figura ilustra Skype para Business Server conectando dos sistemas IP-PBX.
  
![Diagrama de interconexión de los sistemas IP-PAX en Lync Server](../../media/inter_trunk02.jpg)
  

