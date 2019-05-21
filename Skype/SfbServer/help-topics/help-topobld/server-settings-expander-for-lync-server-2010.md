---
title: Expansor de configuración de servidor para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Para editar las propiedades de este equipo, haga lo siguiente:'
ms.openlocfilehash: 28261b3637040acda70218f23101b4337b1f90c3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297613"
---
# <a name="server-settings-expander-for-lync-server-2010"></a>Expansor de configuración de servidor para Lync Server 2010
 
Para editar las propiedades de este equipo, haga lo siguiente:
  
- Edite el **nombre de dominio completo (FQDN)** de este equipo. Esta entrada debe coincidir con el nombre del equipo tal como está definido en el sistema de nombres de dominio (DNS) y en los nombres alternativos de asunto (SAN) o el nombre de sujeto (SN) del certificado asociado con este equipo.
    
- Seleccione una de las opciones siguientes:
    
    **Usar todas las direcciones IP**configuradas: Seleccione esta para usar todas las direcciones IP configuradas en el equipo.
    
    > [!IMPORTANT]
    > Si el equipo tiene varias direcciones IP, debe tener en cuenta que los servicios asociados con este equipo usarán todas las direcciones IP para todos los servicios. Si un servidor o servicio de escucha espera la comunicación de una dirección IP y un puerto específicos, es posible que el servicio no haga la mejor selección de la dirección IP en la que escuchar. 
  
    **Limitar el uso del servicio a las direcciones IP seleccionadas**: Seleccione esta opción si desea definir direcciones IP específicas para la **dirección IP principal** en la que este equipo escuchará la comunicación de otros equipos y grupos en la implementación. Defina la **dirección IP de RTC** para la dirección IP específica en la que el equipo y el servicio escucharán las comunicaciones y enviarán las comunicaciones a la puerta de enlace o IP-PBX definida.
    

