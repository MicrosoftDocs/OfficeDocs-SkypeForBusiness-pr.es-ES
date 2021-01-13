---
title: Agregar servidor
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 'Para agregar un nuevo servidor a un grupo de servidores ya creado que puede ser uno de los siguientes:'
ms.openlocfilehash: e40cf71b0ab52e66a3a28e0362de4f9106ddd831
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818630"
---
# <a name="add-server"></a>Agregar servidor
 
Para agregar un nuevo servidor a un grupo de servidores ya creado que puede ser uno de los siguientes:
  
- Servidor front-end de Enterprise Edition
    
- Servidor director
    
- Servidor de mediación
    
- Servidor de conferencia A/V
    
- Servidor de aplicaciones de confianza
    
Cada uno de los nuevos servidores del grupo de servidores tiene sus propios requisitos. En las secciones siguientes, busque el tipo de servidor que va a agregar al grupo de servidores ya creado y proporcione la información pertinente para cada tipo de servidor. La información solicitada se proporciona para definir el nuevo servidor del grupo de servidores.
  
 **Servidor front-end de Enterprise Edition**
  
- Nombre de dominio completo del nuevo servidor como se haya especificado en el Sistema de nombres de dominio (DNS).
    
- Seleccione **Usar todas las direcciones IP configuradas**; de este modo, se puede usar cualquier dirección IP que se haya definido en el equipo. Si lo prefiere, seleccione **Limitar el uso del servicio a las direcciones IP seleccionadas** e indique una determinada dirección en el nuevo servidor. La dirección IP que se especifica es la única dirección IP que se encargará de los servicios hospedados.
    
- Defina una **dirección IP RTC** cuando un servidor de mediación se coloca en el servidor front-end.
    
- Seleccione **Habilitar IPv6** para habilitar IPv6 para este servidor.
    
  **Servidor de director**
  
- El nombre de dominio completo del nuevo servidor es el mismo que en DNS.
    
- Seleccione **Usar todas las direcciones IP configuradas**, lo que significa que se puede utilizar cualquier dirección IP definida en el equipo. De forma alternativa, puede seleccionar **Limitar el uso de servicio a las direcciones IP seleccionadas** y escribir una dirección específica en el nuevo servidor. La dirección IP especificada es la única dirección IP que responderá para los servicios hospedados.
    
  **Servidor de mediación**
  
- El nombre de dominio completo del nuevo servidor es el mismo que en DNS.
    
- Seleccione **Usar todas las direcciones IP configuradas**; de este modo, se puede usar cualquier dirección IP que se haya definido en el equipo. Si lo desea, seleccione **Limitar el uso del servicio a las direcciones IP seleccionadas** y especifique una dirección IP en el nuevo servidor como dirección IP principal; asimismo, indique una dirección IP para la dirección IP de la RTC. Las direcciones IP que se especifican son las únicas direcciones IP que se encargarán de los servicios hospedados.
    
    > [!NOTE]
    > En el caso del servidor de mediación, la dirección IP especificada como IP principal y la dirección IP de RTC coinciden por defecto. Las direcciones IP se pueden definir por separado si utiliza interfaces de red dedicada o direcciones IP separadas en la misma interfaz de red. Si tiene dos interfaces de red diferentes, una para la conexión de red local y otra para la conexión de RTC, debe asignar direcciones IP diferentes. 
  
  **Servidor de conferencia audio/vídeo**
  
- El nombre de dominio completo del nuevo servidor es el mismo que en DNS.
    
- Seleccione **Usar todas las direcciones IP configuradas**, lo que significa que se puede utilizar cualquier dirección IP definida en el equipo. De forma alternativa, puede seleccionar **Limitar el uso de servicio a las direcciones IP seleccionadas** y escribir una dirección específica en el nuevo servidor. La dirección IP especificada es la única dirección IP que responderá para los servicios hospedados.
    
  **Servidor de aplicación de confianza**
  
- El FQDN del nuevo servidor tal como se define en el DNS.
    

