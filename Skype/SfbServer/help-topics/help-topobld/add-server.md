---
title: Agregar servidor
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 'Para agregar un nuevo servidor a un grupo de servidores existente, donde el grupo de servidores es uno de los siguientes:'
ms.openlocfilehash: 6aaa8c29e6eb8ae7742b28aff82a25bd596a2cdb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887175"
---
# <a name="add-server"></a>Agregar servidor
 
Para agregar un nuevo servidor a un grupo de servidores existente, donde el grupo de servidores es uno de los siguientes:
  
- Servidor Front-End Enterprise Edition
    
- Servidor de director
    
- Servidor de mediación
    
- Servidor de conferencia de audio y vídeo
    
- Servidor de aplicaciones de confianza
    
Cada uno de los nuevos servidores de grupo de servidores tiene requisitos diferentes. En las secciones siguientes, busque el tipo de servidor que va a agregar al grupo de servidores existente y facilitar la información solicitada tal y como se define para cada tipo de servidor. Proporcionar la información solicitada para definir el nuevo servidor de grupo de servidores.
  
 **Servidor Front-End Enterprise Edition**
  
- Nombre de dominio completo (FQDN) del nuevo servidor tal y como se define en el sistema de nombres de dominio (DNS).
    
- Seleccione **usar todas las direcciones IP**, lo que significa que se puede usar cualquier dirección IP que se haya definido en el equipo. Como alternativa, puede seleccionar **limitar el uso del servicio a las direcciones IP seleccionadas** y escriba una dirección específica en el nuevo servidor. La dirección IP que ha escrito es la única dirección IP que se va a responder para los servicios hospedados.
    
- Defina una **dirección IP de RTC** cuando un servidor de mediación está combinado en el servidor Front-End.
    
- Seleccione **Habilitar IPv6** para habilitar IPv6 para este servidor.
    
  **Servidor de director**
  
- El FQDN del nuevo servidor tal como se define en DNS.
    
- Seleccione **usar todas las direcciones IP**, lo que significa que se utilizará cualquier dirección IP que se haya definido en el equipo. Como alternativa, seleccione **limitar el uso del servicio a las direcciones IP seleccionadas** y escriba una dirección IP específica en el nuevo servidor. La dirección IP que ha escrito es la única dirección IP que se va a responder para los servicios hospedados.
    
  **Servidor de mediación**
  
- El FQDN del nuevo servidor tal como se define en DNS.
    
- Seleccione **usar todas las direcciones IP**, lo que significa que se puede usar cualquier dirección IP que se haya definido en el equipo. Como alternativa, seleccione **limitar el uso del servicio a las direcciones IP seleccionadas** y escriba una dirección IP específica en el nuevo servidor como la dirección IP principal y un entrar una dirección IP para la dirección IP telefónica conmutada (RTC). Las direcciones IP que ha escrito son la única dirección IP que se va a responder para los servicios designados.
    
    > [!NOTE]
    > Para el servidor de mediación, la dirección IP especificada para la dirección IP principal y la dirección IP de PSTN es el mismo de forma predeterminada. Las direcciones IP se pueden definir por separado si está usando interfaces de red dedicada o separe las direcciones IP en la misma interfaz de red. Si dispone de interfaces de red de dos, uno para la conexión de red local y otro para la conexión de RTC, debe asignar direcciones IP diferentes. 
  
  **Servidor de conferencia de audio y vídeo**
  
- El FQDN del nuevo servidor tal como se define en DNS.
    
- Seleccione **usar todas las direcciones IP**, lo que significa que se puede usar cualquier dirección IP que se haya definido en el equipo. Como alternativa, puede seleccionar **limitar el uso del servicio a las direcciones IP seleccionadas** y escriba una dirección específica en el nuevo servidor. La dirección IP que ha escrito es la única dirección IP que se va a responder para los servicios hospedados.
    
  **Servidor de aplicaciones de confianza**
  
- El FQDN del nuevo servidor tal como se define en DNS.
    

