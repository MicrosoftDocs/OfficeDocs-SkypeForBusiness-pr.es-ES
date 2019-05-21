---
title: Enrutamiento entre troncales en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Obtenga información sobre cómo Skype empresarial Server Enterprise Voice admite el enrutamiento entre troncales.
ms.openlocfilehash: f590463eced61cf2e8b19a27f7cfc2dd648c63c1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276834"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Enrutamiento entre troncales en Skype empresarial Server
 
Obtenga información sobre cómo Skype empresarial Server Enterprise Voice admite el enrutamiento entre troncales.
  
Skype empresarial Server proporciona administración de sesiones básica mediante la compatibilidad con el enrutamiento de intertroncalización. Esto permite que Skype empresarial Server ofrezca funcionalidades de control de llamadas a sistemas de telefonía indirectos. El enrutamiento entre troncos puede interconectar una IP-PBX con una puerta de enlace de la red telefónica conmutada (RTC) para que las llamadas realizadas desde un teléfono de una central de conmutación (PBX) se puedan redirigir a la RTC y las llamadas RTC entrantes se puedan redirigir a un teléfono PBX. De forma similar, Skype empresarial Server puede interconectar dos o más sistemas IP-PBX para que las llamadas se puedan realizar y recibir entre los teléfonos PBX de los diferentes sistemas IP-PBX. 
  
En la ilustración siguiente se muestra cómo Skype empresarial Server proporciona interconectividad entre una puerta de enlace PSTN y una IP-PBX.
  
![Diagrama de conexión puerta de enlace RTC/IP-PBX en Lync Server](../../media/inter_trunk01.jpg)
  
En la siguiente ilustración se muestra cómo Skype empresarial Server conecta dos sistemas IP-PBX.
  
![Diagrama de interconexión de los sistemas IP-PAX en Lync Server](../../media/inter_trunk02.jpg)
  

