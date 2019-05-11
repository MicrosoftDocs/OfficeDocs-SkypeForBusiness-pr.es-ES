---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: El esquema principal de alta disponibilidad para la mayoría de roles de servidor de Skype para Business Server se basa en la redundancia de servidores a través de la agrupación. Si falla un servidor que está ejecutando un determinado rol de servidor, los demás servidores del grupo que estén ejecutando el mismo rol asumirán su carga.
ms.openlocfilehash: 38887d576a6e15135d9ea35c1dd286ee8c052063
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33889363"
---
# <a name="high-availability-planning-tool"></a>High Availability (Planning Tool)
 
El esquema principal de alta disponibilidad para la mayoría de roles de servidor de Skype para Business Server se basa en la redundancia de servidores a través de la agrupación. Si falla un servidor que está ejecutando un determinado rol de servidor, los demás servidores del grupo que estén ejecutando el mismo rol asumirán su carga.
  
Skype para Business Server requiere al menos dos servidores Front-End con el fin de habilitar la alta disponibilidad. La herramienta de planeación utiliza los siguientes criterios para determinar si agregará servidores adicionales con el fin de ofrecer una alta disponibilidad:
  
- Si la implementación contiene dos o más servidores Front-End, la herramienta de planeación no se agrega un servidor adicional.
    
- Si la implementación contiene el servidor perimetral, se agrega un servidor adicional. 
    
- Si la implementación contiene Chat persistente, la herramienta de planeación de agregar un servidor adicional, pero no aumentar el número de grupo de servidores. Por ejemplo, si la implementación ya contiene cuatro servidores, la herramienta de planeación sugiere agregar un servidor adicional (para un total de cinco servidores) pero mantendrá un único grupo de servidores. 

    > [!NOTE] 
    > Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019. La misma funcionalidad está disponible en los equipos. Para obtener más información, consulte [actualización de Skype para la empresa a los equipos de Microsoft](https://docs.microsoft.com/MicrosoftTeams/journey-skypeforbusiness-teams). Si necesita usar chat en grupo, las opciones son migrar los usuarios que requieren esta funcionalidad a los equipos o continuar usando Skype para Business Server 2015. 

    
La herramienta de planeación también agrega una base de datos de reflejo SQL para todas las bases de datos. Por ejemplo, si hay una base de datos de SQL Server de Front-End, la herramienta de planeación agregará la otra base de datos como la base de datos reflejada para este uno y asígnele el nombre como el "Front-End SQL base de datos reflejada.
  
Para obtener más información acerca de cómo preparar el entorno para alta disponibilidad, consulte [Plan de alta disponibilidad y recuperación ante desastres en Skype para Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  

