---
title: Alta disponibilidad (herramienta de planeación)
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: El esquema principal de alta disponibilidad para la mayoría de roles de servidor de Skype para Business Server se basa en la redundancia de servidores a través de la agrupación. Si falla un servidor que está ejecutando un determinado rol de servidor, los demás servidores del grupo que estén ejecutando el mismo rol asumirán su carga.
ms.openlocfilehash: 9948fbc4f1daff73afa020b83357a26c185d7785
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/20/2018
ms.locfileid: "19977267"
---
# <a name="high-availability-planning-tool"></a>Alta disponibilidad (herramienta de planeación)
 
El esquema principal de alta disponibilidad para la mayoría de roles de servidor de Skype para Business Server se basa en la redundancia de servidores a través de la agrupación. Si falla un servidor que está ejecutando un determinado rol de servidor, los demás servidores del grupo que estén ejecutando el mismo rol asumirán su carga.
  
Skype para Business Server requiere al menos dos servidores Front-End con el fin de habilitar la alta disponibilidad. La herramienta de planeación utiliza los siguientes criterios para determinar si agregará servidores adicionales con el fin de ofrecer una alta disponibilidad:
  
- Si la implementación contiene dos o más servidores Front-End, la herramienta de planeación no se agrega un servidor adicional.
    
- Si la implementación contiene el servidor perimetral, se agrega un servidor adicional. 
    
- Si la implementación contiene Chat persistente, la herramienta de planeación de agregar un servidor adicional, pero no aumentar el número de grupo de servidores. Por ejemplo, si la implementación ya contiene cuatro servidores, la herramienta de planeación sugiere agregar un servidor adicional (para un total de cinco servidores) pero mantendrá un único grupo de servidores. 
    
La herramienta de planeación también agrega una base de datos de reflejo SQL para todas las bases de datos. Por ejemplo, si hay una base de datos de SQL Server de Front-End, la herramienta de planeación agregará la otra base de datos como la base de datos reflejada para este uno y asígnele el nombre como el "Front-End SQL base de datos reflejada.
  
Para obtener más información acerca de cómo preparar el entorno para alta disponibilidad, consulte [Plan de alta disponibilidad y recuperación ante desastres en Skype para Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  

