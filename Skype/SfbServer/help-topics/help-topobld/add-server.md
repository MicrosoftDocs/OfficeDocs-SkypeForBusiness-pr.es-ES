---
title: Agregar servidor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 'Para agregar un nuevo servidor a un grupo de servidores existente, donde el grupo es uno de los siguientes:'
ms.openlocfilehash: c19aad7f55c6ebc22ee64c715700d8cc7116bccb
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698045"
---
# <a name="add-server"></a>Agregar servidor
 
Para agregar un nuevo servidor a un grupo de servidores existente, donde el grupo es uno de los siguientes:
  
- Servidor front-end Enterprise Edition
    
- Servidor Director
    
- Servidor de mediación
    
- Servidor de conferencias de audio y vídeo
    
- Servidor de aplicaciones de confianza
    
Cada uno de los nuevos servidores de grupo tiene requisitos diferentes. En las secciones siguientes, busque el tipo de servidor que está agregando al grupo existente y proporcione la información solicitada, ya que se define para cada tipo de servidor. Proporcione la información solicitada para definir el nuevo servidor de grupo.
  
 **Servidor front-end Enterprise Edition**
  
- Nombre de dominio completo (FQDN) del nuevo servidor como se define en el sistema de nombres de dominio (DNS).
    
- Seleccione **usar todas las direcciones IP configuradas**, lo que significa que se puede usar cualquier dirección IP definida en el equipo. También puede seleccionar **limitar el uso del servicio a las direcciones IP seleccionadas** e introducir una dirección específica en el nuevo servidor. La dirección IP introducida es la única dirección IP que responderá a los servicios hospedados.
    
- Defina una **dirección IP de RTC** cuando se colocará un servidor de mediación en el servidor front-end.
    
- Seleccione **Habilitar IPv6** para habilitar IPv6 en este servidor.
    
  **Servidor Director**
  
- El FQDN del nuevo servidor como se define en DNS.
    
- Seleccione **usar todas las direcciones IP configuradas**, lo que significa que se usará cualquier dirección IP definida en el equipo. También puede seleccionar limitar el **uso del servicio a las direcciones IP seleccionadas** e introducir una dirección IP específica en el nuevo servidor. La dirección IP introducida es la única dirección IP que responderá a los servicios hospedados.
    
  **Servidor de mediación**
  
- El FQDN del nuevo servidor como se define en DNS.
    
- Seleccione **usar todas las direcciones IP configuradas**, lo que significa que se puede usar cualquier dirección IP definida en el equipo. También puede seleccionar limitar el **uso del servicio a las direcciones IP seleccionadas** e introducir una dirección IP específica en el nuevo servidor como dirección IP principal y una dirección IP para la dirección IP de la red de telefonía pública conmutada (RTC). Las direcciones IP especificadas son la única dirección IP que responderá a los servicios designados.
    
    > [!NOTE]
    > Para el servidor de mediación, la dirección IP especificada para la dirección IP principal y la dirección IP de RTC es la misma de forma predeterminada. Las direcciones IP se pueden definir por separado si está usando interfaces de red dedicadas o direcciones IP independientes en la misma interfaz de red. Si tiene dos interfaces de red, una para la conexión de red local y otra para la conexión RTC, debe asignar direcciones IP diferentes. 
  
  **Servidor de conferencias de audio y vídeo**
  
- El FQDN del nuevo servidor como se define en DNS.
    
- Seleccione **usar todas las direcciones IP configuradas**, lo que significa que se puede usar cualquier dirección IP definida en el equipo. También puede seleccionar **limitar el uso del servicio a las direcciones IP seleccionadas** e introducir una dirección específica en el nuevo servidor. La dirección IP introducida es la única dirección IP que responderá a los servicios hospedados.
    
  **Servidor de aplicaciones de confianza**
  
- El FQDN del nuevo servidor como se define en DNS.
    

