---
title: Enrutamiento entre tronco en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype para Business Server proporciona administración de sesiones básica a través de la compatibilidad de enrutamiento entre troncos. '
ms.openlocfilehash: a1486d24c0681df44085db754fda380d653c636b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920516"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Enrutamiento entre tronco en Skype para Business Server

Skype para Business Server proporciona administración de sesiones básica a través de la compatibilidad de enrutamiento entre troncos. Esta capacidad permite Skype para Business Server proporcionar funcionalidades de control de llamada a sistemas de telefonía de nivel inferior. El enrutamiento entre troncos puede interconectar una IP-PBX con una puerta de enlace de la red telefónica conmutada (RTC) para que las llamadas realizadas desde un teléfono de una central de conmutación (PBX) se puedan redirigir a la RTC y las llamadas RTC entrantes se puedan redirigir a un teléfono PBX. De forma similar, Skype para Business Server puede interconnect dos o más sistemas de IP-PBX para que las llamadas se pueden colocar y recibió entre teléfonos PBX de los distintos sistemas de IP-PBX. 


La siguiente ilustración muestra Skype para Business Server proporcionando interconectividad entre una puerta de enlace RTC y un IP-PBX.

![Interconectividad entre una puerta de enlace RTC y un IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

En la siguiente figura ilustra Skype para Business Server conectando dos sistemas IP-PBX.

![Skype para Business Server conectando dos sistemas IP-PGX](../../media/two-ip-pbx-systems.jpg)

