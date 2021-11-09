---
title: Agregar opciones IP de servidor perimetral
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'Microsoft Lync Server 2013 permite configurar direcciones IPv4 e IPv6 para cada interfaz para el servidor perimetral y el grupo de servidores perimetrales. Para ello, siga este procedimiento:'
ms.openlocfilehash: 7cac0c12014e1b4b83ca186fe20adfa67469d8a2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852184"
---
# <a name="add-edge-server-ip-options"></a>Agregar opciones IP de servidor perimetral
 
Microsoft Lync Server 2013 permite configurar direcciones IPv4 e IPv6 para cada interfaz para el servidor perimetral y el grupo de servidores perimetrales. Para ello, siga este procedimiento:
  
- **Habilitar IPv4 en la interfaz interna:** active la casilla si desea aplicar una dirección IPv4 a la interfaz interna del servidor perimetral o del grupo perimetral
    
- **Habilitar IPv6 en la interfaz interna:** active la casilla si desea aplicar una dirección IPv6 a la interfaz interna del servidor perimetral o del grupo perimetral
    
- **Habilitar IPv4 en la interfaz** externa: active la casilla si desea aplicar una dirección IPv4 a la interfaz externa del servidor perimetral o del grupo perimetral
    
- **Habilitar IPv6 en la interfaz** externa: active la casilla si desea aplicar una dirección IPv6 a la interfaz externa del servidor perimetral o del grupo perimetral
    
También puede configurar el servidor perimetral o el grupo de servidores perimetrales para usar una dirección de traducción de direcciones de red para las direcciones IP externas. Para hacerlo, active la casilla **La dirección IP externa del grupo de servidores perimetral se traduce mediante NAT**.
  
Compatibilidad con NAT. La traducción de direcciones de red (NAT) no se admite cuando se usa el equilibrio de carga de hardware, por lo que no seleccione la opción NAT si va a implementar un grupo de servidores perimetrales con equilibrio de carga de hardware.
  

