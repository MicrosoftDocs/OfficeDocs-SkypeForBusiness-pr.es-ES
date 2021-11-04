---
title: Skype Empresarial Server Herramienta de planeación de alta disponibilidad
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.localizationpriority: medium
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: El esquema de alta disponibilidad principal para la mayoría de los roles de servidor en Skype Empresarial Server 2015 se basa en la redundancia del servidor mediante agrupación. Si se produce un error en un servidor que ejecuta un rol de servidor determinado, los demás servidores del grupo que ejecutan el mismo rol asumen la carga de dicho servidor.
ms.openlocfilehash: 6a39d065349fb392dd54a7ff0d1872acc91e89cd
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774200"
---
# <a name="skype-for-business-server-high-availability-planning-tool"></a>Skype Empresarial Server Herramienta de planeación de alta disponibilidad
 
El esquema de alta disponibilidad principal para la mayoría de los roles de servidor en Skype Empresarial Server 2015 se basa en la redundancia del servidor mediante agrupación. Si se produce un error en un servidor que ejecuta un rol de servidor determinado, los demás servidores del grupo que ejecutan el mismo rol asumen la carga de dicho servidor.
  
Skype Empresarial Server 2015 requiere al menos dos servidores front-end para habilitar la alta disponibilidad. La Herramienta de planeación usa los siguientes criterios para determinar si agregará servidores adicionales para admitir la alta disponibilidad:
  
- Si la implementación contiene dos o más servidores front-end, la herramienta de planeación no agrega un servidor adicional.
    
- Si la implementación contiene servidor perimetral, se agrega otro servidor. 
    
- Si la implementación contiene chat persistente, la herramienta de planeación agregará un servidor adicional, pero no aumentará el número de grupo. Por ejemplo, si la implementación ya contiene cuatro servidores, la Herramienta de planeación sugerirá agregar otro servidor (para un total de cinco servidores), pero mantendrá un único grupo. 
    
La Herramienta de planeación también agrega una base de SQL de datos reflejada para todas las bases de datos. Por ejemplo, si hay una base de datos front-end SQL Server, la Herramienta de planeación agregará la otra base de datos como la base de datos reflejada para esta y la nombrará como la base de datos reflejada SQL front-end.
  
Para obtener más información sobre cómo preparar el entorno para la alta disponibilidad, vea [Plan for high availability and disaster recovery in Skype Empresarial Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  

