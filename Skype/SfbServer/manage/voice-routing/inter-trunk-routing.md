---
title: Enrutamiento entre tronco en Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype para Business Server proporciona administración de sesiones básica a través de la compatibilidad de enrutamiento entre troncos. '
ms.openlocfilehash: 66ee1f0cb9e37587d3c581b895528e27e7fad6c0
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222817"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Enrutamiento entre tronco en Skype para Business Server

Skype para Business Server proporciona administración de sesiones básica a través de la compatibilidad de enrutamiento entre troncos. Esta capacidad permite Skype para Business Server proporcionar funcionalidades de control de llamada a sistemas de telefonía de nivel inferior. El enrutamiento entre troncos puede interconectar una IP-PBX con una puerta de enlace de la red telefónica conmutada (RTC) para que las llamadas realizadas desde un teléfono de una central de conmutación (PBX) se puedan redirigir a la RTC y las llamadas RTC entrantes se puedan redirigir a un teléfono PBX. De forma similar, Skype para Business Server puede interconnect dos o más sistemas de IP-PBX para que las llamadas se pueden colocar y recibió entre teléfonos PBX de los distintos sistemas de IP-PBX. 


La siguiente ilustración muestra Skype para Business Server proporcionando interconectividad entre una puerta de enlace RTC y un IP-PBX.

![Interconectividad entre una puerta de enlace RTC y un IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

En la siguiente figura ilustra Skype para Business Server conectando dos sistemas IP-PBX.

![Skype para Business Server conectando dos sistemas IP-PGX](../../media/two-ip-pbx-systems.jpg)

