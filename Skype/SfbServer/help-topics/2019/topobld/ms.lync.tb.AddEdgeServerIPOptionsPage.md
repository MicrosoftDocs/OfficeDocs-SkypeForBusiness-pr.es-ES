---
title: Agregar opciones IP de servidor perimetral
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Skype Empresarial Server permite configurar direcciones IPv4 e IPv6 para cada interfaz para el servidor perimetral y el grupo de servidores perimetrales. Para ello, siga este procedimiento:'
ms.openlocfilehash: 60b9931a8fd3fad950f3277a27deb420ddb749dbee9269ca628023ea0806e14c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54294257"
---
# <a name="add-edge-server-ip-options"></a>Agregar opciones IP de servidor perimetral
 
Skype Empresarial Server permite configurar direcciones IPv4 e IPv6 para cada interfaz para el servidor perimetral y el grupo de servidores perimetrales. Para ello, siga este procedimiento:
  
- **Habilitar IPv4 en la interfaz interna:** active la casilla si desea aplicar una dirección IPv4 a la interfaz interna del servidor perimetral o del grupo perimetral
    
- **Habilitar IPv6 en la interfaz interna:** active la casilla si desea aplicar una dirección IPv6 a la interfaz interna del servidor perimetral o del grupo perimetral
    
- **Habilitar IPv4 en la interfaz** externa: active la casilla si desea aplicar una dirección IPv4 a la interfaz externa del servidor perimetral o del grupo perimetral
    
- **Habilitar IPv6 en la interfaz** externa: active la casilla si desea aplicar una dirección IPv6 a la interfaz externa del servidor perimetral o del grupo perimetral
    
También puede configurar el servidor perimetral o el grupo de servidores perimetrales para usar una dirección de traducción de direcciones de red para las direcciones IP externas. Para hacerlo, active la casilla **La dirección IP externa del grupo de servidores perimetral se traduce mediante NAT**.
  
Compatibilidad con NAT. La traducción de direcciones de red (NAT) no se admite cuando se usa el equilibrio de carga de hardware, por lo que no seleccione la opción NAT si va a implementar un grupo de servidores perimetrales con equilibrio de carga de hardware.
  

