---
title: Agregar opciones de IP de servidor perimetral
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
ROBOTS: NOINDEX, NOFOLLOW
description: 'Skype para Business Server le permite configurar las direcciones IPv4 e IPv6 para cada interfaz para el servidor perimetral y el grupo de servidores perimetrales. Para ello, realice lo siguiente:'
ms.openlocfilehash: b4b7a80ac8f1cc9f310542a9c87c5a2c568e870b
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21069303"
---
# <a name="add-edge-server-ip-options"></a>Agregar opciones de IP de servidor perimetral
 
Skype para Business Server le permite configurar las direcciones IPv4 e IPv6 para cada interfaz para el servidor perimetral y el grupo de servidores perimetrales. Para ello, realice lo siguiente:
  
- **Habilitar IPv4 en interfaz interna**: Active la casilla de verificación si desea aplicar una dirección IPv4 para el servidor perimetral o la interfaz interna del grupo de servidores perimetrales
    
- **Habilitar IPv6 en la interfaz interna**: Active la casilla de verificación si desea aplicar una dirección IPv6 para el servidor perimetral o la interfaz interna del grupo de servidores perimetrales
    
- **Habilitar IPv4 en interfaz externa**: Active la casilla de verificación si desea aplicar una dirección IPv4 para el servidor perimetral o la interfaz externa de grupo de servidores perimetrales
    
- **Habilitar IPv6 en la interfaz externa**: Active la casilla de verificación si desea aplicar una dirección IPv6 para el servidor perimetral o la interfaz externa de grupo de servidores perimetrales
    
También puede configurar el servidor perimetral o grupo de servidores perimetrales para usar una dirección de traducción de direcciones de red para las direcciones IP externas. Para ello, mediante la selección de la casilla de verificación **NAT traduce la dirección IP externa de este grupo de servidores perimetrales**.
  
Compatibilidad con NAT. Traducción de direcciones de red (NAT) no se admite cuando se usa hardware equilibrio de carga, por lo que no seleccione la opción de NAT si va a implementar un grupo de servidores perimetrales con equilibrio de carga de hardware.
  

