---
title: Alta disponibilidad (herramienta de planeación)
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/8/2016
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: El esquema principal de alta disponibilidad para la mayoría de funciones de servidor en Skype para Business Server 2015 se basa en la redundancia de servidor a través de la agrupación. Si falla un servidor que está ejecutando un determinado rol de servidor, los demás servidores del grupo que estén ejecutando el mismo rol asumirán su carga.
ms.openlocfilehash: 8441db5ee4a84c573ed6a1642473b827382e4654
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="high-availability-planning-tool"></a>Alta disponibilidad (herramienta de planeación)
 
El esquema principal de alta disponibilidad para la mayoría de funciones de servidor en Skype para Business Server 2015 se basa en la redundancia de servidor a través de la agrupación. Si falla un servidor que está ejecutando un determinado rol de servidor, los demás servidores del grupo que estén ejecutando el mismo rol asumirán su carga.
  
Skype para Business Server 2015 requiere al menos dos servidores frontales para permitir una alta disponibilidad. La herramienta de planeación utiliza los siguientes criterios para determinar si agrega servidores adicionales con el fin de conseguir una elevada disponibilidad:
  
- Si la implementación contiene dos o más servidores frontales, la herramienta de planeación no agrega un servidor adicional.
    
- Si la implementación contiene el servidor perimetral, se agrega un servidor adicional. 
    
- Si la implementación contiene Chat persistente, la herramienta de planificación agregar un servidor adicional, pero no aumentar el número de grupo. Por ejemplo, si la implementación ya contiene cuatro servidores, la herramienta de planeación sugiere agregar un servidor adicional (para un total de cinco servidores) pero mantendrá un grupo único. 
    
La herramienta de planeación también agrega una base de datos SQL de espejo para todas las bases de datos. Por ejemplo, si hay una base de datos de SQL Server de extremo frontal, la herramienta de planeación agregará otra base como la base de datos reflejada para éste y asígnele el nombre como el "Front End SQL base de datos reflejada.
  
Para obtener más información acerca de cómo preparar el entorno para alta disponibilidad, vea [Planear la alta disponibilidad y recuperación ante desastres en Skype para Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  

