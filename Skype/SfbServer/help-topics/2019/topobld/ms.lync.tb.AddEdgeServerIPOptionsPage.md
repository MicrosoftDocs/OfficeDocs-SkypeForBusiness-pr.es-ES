---
title: Agregar opciones IP de servidor perimetral
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
ROBOTS: NOINDEX, NOFOLLOW
description: 'Skype empresarial Server le permite configurar direcciones IPv4 e IPv6 para cada interfaz para el servidor perimetral y el grupo Edge. Para ello, haga lo siguiente:'
ms.openlocfilehash: 5b63847f3044411dcb8e04e29eea21492597993d
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798207"
---
# <a name="add-edge-server-ip-options"></a>Agregar opciones IP de servidor perimetral
 
Skype empresarial Server le permite configurar direcciones IPv4 e IPv6 para cada interfaz para el servidor perimetral y el grupo Edge. Para ello, haga lo siguiente:
  
- **Habilitar IPv4 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv4 al servidor perimetral o a la interfaz interna de grupo perimetral.
    
- **Habilitar IPv6 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv6 al servidor perimetral o a la interfaz interna de la agrupación perimetral.
    
- **Habilitar IPv4 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv4 al servidor perimetral o a la interfaz externa del grupo perimetral.
    
- **Habilitar IPv6 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv6 al servidor perimetral o a la interfaz externa del grupo perimetral.
    
También puede configurar el servidor perimetral o el grupo Edge para usar una dirección de traducción de direcciones de red para las direcciones IP externas. Para ello, active la casilla **la dirección IP externa de este grupo de límites la traduce nat**.
  
Compatibilidad con NAT. La traducción de direcciones de red (NAT) no es compatible cuando se usa el equilibrio de carga de hardware, por lo tanto, no seleccione la opción NAT si está implementando un grupo de servidores perimetrales con el equilibrio de carga de hardware.
  

