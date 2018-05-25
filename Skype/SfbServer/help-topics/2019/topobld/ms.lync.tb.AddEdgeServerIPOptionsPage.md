---
title: Agregar opciones de IP de servidor perimetral
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'Microsoft Lync Server 2013 le permite configurar las direcciones IPv4 e IPv6 para cada interfaz para el servidor perimetral y el grupo de servidores perimetrales. Para ello, realice lo siguiente:'
ms.openlocfilehash: a6f4dd60355a4e241c70ec28c72fa86d91c66a9e
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="add-edge-server-ip-options"></a>Agregar opciones de IP de servidor perimetral
 
Microsoft Lync Server 2013 le permite configurar las direcciones IPv4 e IPv6 para cada interfaz para el servidor perimetral y el grupo de servidores perimetrales. Para ello, realice lo siguiente:
  
- **Habilitar IPv4 en interfaz interna**: Active la casilla de verificación si desea aplicar una dirección IPv4 para el servidor perimetral o la interfaz interna del grupo de servidores perimetrales
    
- **Habilitar IPv6 en la interfaz interna**: Active la casilla de verificación si desea aplicar una dirección IPv6 para el servidor perimetral o la interfaz interna del grupo de servidores perimetrales
    
- **Habilitar IPv4 en interfaz externa**: Active la casilla de verificación si desea aplicar una dirección IPv4 para el servidor perimetral o la interfaz externa de grupo de servidores perimetrales
    
- **Habilitar IPv6 en la interfaz externa**: Active la casilla de verificación si desea aplicar una dirección IPv6 para el servidor perimetral o la interfaz externa de grupo de servidores perimetrales
    
También puede configurar el servidor perimetral o grupo de servidores perimetrales para usar una dirección de traducción de direcciones de red para las direcciones IP externas. Para ello, mediante la selección de la casilla de verificación **NAT traduce la dirección IP externa de este grupo de servidores perimetrales**.
  
Compatibilidad con NAT. Traducción de direcciones de red (NAT) no se admite cuando se usa hardware equilibrio de carga, por lo que no seleccione la opción de NAT si va a implementar un grupo de servidores perimetrales con equilibrio de carga de hardware.
  

