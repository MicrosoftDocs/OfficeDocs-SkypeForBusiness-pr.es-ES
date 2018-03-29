---
title: Ampliador de configuración de servidor de Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Para editar las propiedades de este equipo, siga este procedimiento:'
ms.openlocfilehash: 0e5e595382bb92621c1551158edecf736ff0aa6b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="server-settings-expander-for-lync-server-2010"></a>Ampliador de configuración de servidor de Lync Server 2010
 
Para editar las propiedades de este equipo, siga este procedimiento:
  
- Editar el **nombre de dominio (completo FQDN) completo** para este equipo. Esta entrada debe coincidir con el nombre del equipo tal como se define en el sistema de nombres de dominio (DNS) y en nombres alternativos de asunto (SAN) o nombre (SN) del sujeto del certificado asociado con este equipo.
    
- Seleccione uno de los siguientes:
    
    **Utilice todas las direcciones IP**: seleccione esta opción para utilizar todas las direcciones IP en el equipo.
    
    > [!IMPORTANT]
    > Si el equipo tiene varias direcciones IP, debe tener en cuenta que los servicios asociados a este equipo utilizará todas las direcciones IP para todos los servicios. Si un servidor escucha o servicio está esperando la comunicación de un puerto y una dirección IP específica, el servicio no tiene la mejor selección de la dirección IP para escuchar. 
  
    **Uso del servicio de límite a las direcciones IP seleccionadas**: seleccione esta opción si desea definir direcciones IP específicas para la **dirección IP principal** en el que escucha en este equipo para la comunicación de otros equipos y grupos en la implementación. Definir la **dirección IP de RTC** para la dirección IP específica que el equipo y el servicio escuchará comunicaciones y enviar comunicaciones a la puerta de enlace PSTN o PBX-IP definido.
    

