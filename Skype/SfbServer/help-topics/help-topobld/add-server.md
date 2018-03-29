---
title: Agregar servidor
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 'Para agregar un nuevo servidor a un grupo existente de servidores, donde el grupo es uno de los siguientes:'
ms.openlocfilehash: 609fbb28900ac67e0a4e1e2a400f1eebb29b2ff2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-server"></a>Agregar servidor
 
Para agregar un nuevo servidor a un grupo existente de servidores, donde el grupo es uno de los siguientes:
  
- Servidor Front-End de Enterprise Edition
    
- Servidor director
    
- Servidor de mediación
    
- Servidor de conferencias de audio/vídeo
    
- Servidor de aplicaciones de confianza
    
Cada uno de los nuevos servidores de piscina tiene requisitos diferentes. En las secciones siguientes, busque el tipo de servidor que se va a agregar a la agrupación y facilitar la información solicitada tal como se define para cada tipo de servidor. Proporcionar la información solicitada para definir el nuevo servidor de grupo.
  
 **Servidor Front-End de Enterprise Edition**
  
- Nombre de dominio completo (FQDN) del nuevo servidor tal y como se define en el sistema de nombres de dominio (DNS).
    
- Seleccione **usar todas las direcciones IP**, lo que significa que se puede utilizar cualquier dirección IP definida en el equipo. Alternativamente, puede seleccionar el **uso del servicio de límite a las direcciones IP seleccionadas** y escriba una dirección específica en el nuevo servidor. La dirección IP introducida es la única dirección IP que responderá a los servicios alojados.
    
- Definir una **dirección IP de RTC** cuando un servidor de mediación se encuentra en el servidor Front-End.
    
- Seleccione **Habilitar IPv6** para habilitar IPv6 para este servidor.
    
 **Servidor director**
  
- El FQDN del servidor nuevo que está definido en DNS.
    
- Seleccione **utilizar todas las direcciones IP**, lo que significa que se puede utilizar cualquier dirección IP definida en el equipo. Como alternativa, seleccione **limitar el uso de servicio a las direcciones IP seleccionadas** y escriba una dirección IP específica en el nuevo servidor. La dirección IP introducida es la única dirección IP que responderá a los servicios alojados.
    
 **Servidor de mediación**
  
- El FQDN del servidor nuevo que está definido en DNS.
    
- Seleccione **usar todas las direcciones IP**, lo que significa que se puede utilizar cualquier dirección IP definida en el equipo. Como alternativa, seleccione **uso de servicio de límite a las direcciones IP seleccionadas** y entrar una dirección IP específica en el nuevo servidor la dirección IP principal y un entrar una dirección IP para la dirección IP pública telefónica conmutada (RTC) de la red. Las direcciones IP introducidas son la única dirección IP que responderá a los servicios designados.
    
    > [!NOTE]
    > Para el servidor de mediación, la dirección IP especificada para la dirección IP principal y la dirección IP de PSTN es el mismo de forma predeterminada. Las direcciones IP se pueden definir por separado si utiliza las interfaces de red dedicada o separe las direcciones IP en la misma interfaz de red. Si tiene interfaces de red de dos, uno para la conexión de red local y otro para la conexión RTC, debe asignar direcciones IP diferentes. 
  
 **Servidor de conferencias de audio/vídeo**
  
- El FQDN del servidor nuevo que está definido en DNS.
    
- Seleccione **usar todas las direcciones IP**, lo que significa que se puede utilizar cualquier dirección IP definida en el equipo. Alternativamente, puede seleccionar el **uso del servicio de límite a las direcciones IP seleccionadas** y escriba una dirección específica en el nuevo servidor. La dirección IP introducida es la única dirección IP que responderá a los servicios alojados.
    
 **Servidor de aplicaciones de confianza**
  
- El FQDN del servidor nuevo que está definido en DNS.
    

