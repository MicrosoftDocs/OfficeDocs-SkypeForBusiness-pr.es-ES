---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: El esquema de alta disponibilidad principal para la mayoría de los roles de servidor de Skype empresarial Server 2015 se basa en la redundancia de los servidores a través de la agrupación. Si falla un servidor que está ejecutando un determinado rol de servidor, los demás servidores del grupo que estén ejecutando el mismo rol asumirán su carga.
ms.openlocfilehash: 1d82174e8dc1314deaf81708c70054a4d602085b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821442"
---
# <a name="high-availability-planning-tool"></a>High Availability (Planning Tool)
 
El esquema de alta disponibilidad principal para la mayoría de los roles de servidor de Skype empresarial Server 2015 se basa en la redundancia de los servidores a través de la agrupación. Si falla un servidor que está ejecutando un determinado rol de servidor, los demás servidores del grupo que estén ejecutando el mismo rol asumirán su carga.
  
Skype empresarial Server 2015 requiere al menos dos servidores front-end para poder ofrecer una alta disponibilidad. La herramienta de planeación usa los siguientes criterios para determinar si agregará servidores adicionales para admitir una alta disponibilidad:
  
- Si la implementación contiene dos o más servidores front-end, la herramienta de planeación no agrega un servidor adicional.
    
- Si la implementación contiene un servidor perimetral, se agrega un servidor adicional. 
    
- Si la implementación contiene una conversación persistente, la herramienta de planificación agregará un servidor adicional, pero no aumentará el número de la agrupación. Por ejemplo, si la implementación ya contiene cuatro servidores, la herramienta de planeación sugerirá que se agregue un servidor adicional (para un total de cinco servidores), pero que mantendrá un único grupo. 
    
La herramienta de planeación también agrega una base de datos SQL de reflejo para todas las bases de datos. Por ejemplo, si hay una base de datos de SQL Server front end, la herramienta de planeación agregará la otra base de datos como la base de datos reflejada para esta y la asignaremos el nombre "base de datos SQL de reflejo front-end.
  
Para obtener más información sobre cómo preparar el entorno para una alta disponibilidad, consulte [Plan for Disaster Availability and Disaster Recovery in Skype empresarial Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  

