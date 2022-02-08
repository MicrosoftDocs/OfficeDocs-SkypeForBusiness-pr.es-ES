---
title: Expansor de configuración de servidor para Lync Server 2010
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Para editar las propiedades de este equipo, realice lo siguiente:'
ms.openlocfilehash: 1323206d9ad8762cc175003210f140a28ce2b634
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390202"
---
# <a name="server-settings-expander-for-lync-server-2010"></a>Expansor de configuración de servidor para Lync Server 2010
 
Para editar las propiedades de este equipo, realice lo siguiente:
  
- Edite el **Nombre de dominio completo (FQDN)** de este equipo. Este nombre debe coincidir con el nombre del equipo definido en el sistema de nombres de dominio (DNS) y en nombres alternativos de sujeto (SAN) o nombres de sujeto (SN) del certificado asociado con el equipo.
    
- Seleccione una de las opciones siguientes:
    
    **Usar todas las direcciones IP configuradas**: seleccione esta opción para usar todas las direcciones IP configuradas en el equipo.
    
    > [!IMPORTANT]
    > Si el equipo tiene varias direcciones IP, debe ser consciente de que los servicios asociados con el equipo utilizarán todas las direcciones IP para todos los servicios. Si un servidor o servicio de escucha está a la espera de comunicación con una dirección IP o puerto específico, es posible que el servicio no elija la mejor dirección IP desde la que realizar la escucha. 
  
    **Limitar el uso del servicio a las direcciones IP seleccionadas**: seleccione esta opción si desea definir direcciones IP específicas para la **Dirección IP principal** a la que escuchará este equipo para comunicaciones desde otros equipos y grupos servidores en la implementación. Defina la **Dirección IP de RTC** para la dirección IP específica a la que escucharán el equipo y el servicio para comunicarse y enviar comunicaciones a la puerta de enlace RTC definida o IP-PBX.
    

