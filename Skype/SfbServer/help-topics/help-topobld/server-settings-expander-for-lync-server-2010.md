---
title: Expansor de configuración de servidor para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Para editar las propiedades de este equipo, realice lo siguiente:'
ms.openlocfilehash: 0db8f318f7c4381707869fe06ee7c492c78d63ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929542"
---
# <a name="server-settings-expander-for-lync-server-2010"></a>Expansor de configuración de servidor para Lync Server 2010
 
Para editar las propiedades de este equipo, realice lo siguiente:
  
- Editar el **nombre de dominio (FQDN) completo** de este equipo. Esta entrada debe coincidir con el nombre del equipo tal y como se define en el sistema de nombres de dominio (DNS) y en nombres alternativos del sujeto (SAN) o el nombre de sujeto (SN) del certificado asociado con este equipo.
    
- Seleccione una de las siguientes:
    
    **Utilice todas las direcciones IP configuradas**: seleccione esta opción para usar todas las direcciones IP en el equipo.
    
    > [!IMPORTANT]
    > Si el equipo tiene varias direcciones IP, debe tener en cuenta que los servicios asociados con este equipo usará todas las direcciones IP para todos los servicios. Si un servidor escucha o servicio está esperando la comunicación de un puerto y dirección IP específica, el servicio no puede hacer que la mejor selección de qué dirección IP para escuchar en. 
  
    **Limitar el uso del servicio a las direcciones IP seleccionadas**: seleccione esta opción si desea definir direcciones IP específicas para la **dirección IP principal** que escuchará este equipo para la comunicación entre otros equipos y grupos de servidores en la implementación. Definir la **dirección IP de RTC** para la dirección IP específica que el equipo y el servicio se escuchar para las comunicaciones y enviar comunicaciones a la puerta de enlace RTC o IP-PBX definido.
    

