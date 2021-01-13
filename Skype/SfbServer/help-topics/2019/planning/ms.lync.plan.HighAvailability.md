---
title: Alta disponibilidad (Herramienta de planeación)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
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
ROBOTS: NOINDEX, NOFOLLOW
description: El esquema principal de alta disponibilidad para la mayoría de los roles de servidor en Skype Empresarial Server se basa en la redundancia de servidores a través de la agrupación. Si se produce un error en un servidor que ejecuta un rol de servidor determinado, los demás servidores del grupo que ejecutan el mismo rol asumen la carga de dicho servidor.
ms.openlocfilehash: 5c9895e325770f5c826b5c55213fcc1b569aa701
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819800"
---
# <a name="high-availability-planning-tool"></a>Alta disponibilidad (Herramienta de planeación)
 
El esquema principal de alta disponibilidad para la mayoría de los roles de servidor en Skype Empresarial Server se basa en la redundancia de servidores a través de la agrupación. Si se produce un error en un servidor que ejecuta un rol de servidor determinado, los demás servidores del grupo que ejecutan el mismo rol asumen la carga de dicho servidor.
  
Skype Empresarial Server requiere al menos dos servidores front-end para habilitar la alta disponibilidad. La Herramienta de planeación usa los siguientes criterios para determinar si agregará servidores adicionales para admitir la alta disponibilidad:
  
- Si la implementación contiene dos o más servidores front-end, la Herramienta de planeación no agrega un servidor adicional.
    
- Si la implementación contiene un servidor perimetral, se agrega un servidor adicional. 
    
- Si la implementación contiene chat persistente, la herramienta de planeación agregará un servidor adicional, pero no aumentará el número de grupo. Por ejemplo, si la implementación ya contiene cuatro servidores, la Herramienta de planeación sugerirá agregar un servidor adicional (para un total de cinco servidores), pero mantendrá un único grupo. 

    > [!NOTE] 
    > El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no es compatible con Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Actualización de Skype Empresarial a Microsoft Teams.](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here) Si necesita usar el chat persistente, puede migrar usuarios que requieran esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015. 

    
La Herramienta de planeación también agrega una base de datos SQL reflejo para todas las bases de datos. Por ejemplo, si hay una base de datos de SQL Server front-end, la Herramienta de planeación agregará la otra base de datos como la base de datos reflejada para esta y la nombrará como la base de datos reflejada SQL front-end.
  
Para obtener más información sobre cómo preparar su entorno para la alta disponibilidad, consulte [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  

