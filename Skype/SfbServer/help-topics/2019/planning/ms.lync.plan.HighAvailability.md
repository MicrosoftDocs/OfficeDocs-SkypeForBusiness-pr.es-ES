---
title: Alta disponibilidad (herramienta de planeación)
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
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
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 'El esquema de alta disponibilidad principal para la mayoría de los roles de servidor en Skype Empresarial Server se basa en la redundancia del servidor mediante agrupación. Si se produce un error en un servidor que ejecuta un rol de servidor determinado, los demás servidores del grupo que ejecutan el mismo rol asumen la carga de dicho servidor.'
---

# <a name="high-availability-planning-tool"></a>Alta disponibilidad (herramienta de planeación)
 
El esquema de alta disponibilidad principal para la mayoría de los roles de servidor en Skype Empresarial Server se basa en la redundancia del servidor mediante agrupación. Si se produce un error en un servidor que ejecuta un rol de servidor determinado, los demás servidores del grupo que ejecutan el mismo rol asumen la carga de dicho servidor.
  
Skype Empresarial Server requiere al menos dos servidores front-end para habilitar la alta disponibilidad. La Herramienta de planeación usa los siguientes criterios para determinar si agregará servidores adicionales para admitir la alta disponibilidad:
  
- Si la implementación contiene dos o más servidores front-end, la herramienta de planeación no agrega un servidor adicional.
    
- Si la implementación contiene servidor perimetral, se agrega un servidor adicional. 
    
- Si la implementación contiene chat persistente, la herramienta de planeación agregará un servidor adicional, pero no aumentará el número de grupo. Por ejemplo, si la implementación ya contiene cuatro servidores, la Herramienta de planeación sugerirá agregar un servidor adicional (para un total de cinco servidores), pero mantendrá un único grupo de servidores. 

    > [!NOTE] 
    > El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, [vea Skype Empresarial para Microsoft Teams actualización](/MicrosoftTeams/upgrade-start-here). Si necesita usar el chat persistente, las opciones son migrar usuarios que requieren esta funcionalidad para Teams o seguir usando Skype Empresarial Server 2015. 

    
La Herramienta de planeación también agrega una base de SQL de datos reflejada para todas las bases de datos. Por ejemplo, si hay una base de datos de SQL Server front-end, la Herramienta de planeación agregará la otra base de datos como la base de datos reflejada para esta y la nombrará como la base de datos reflejada SQL front-end.
  
Para obtener más información sobre cómo preparar el entorno para la alta disponibilidad, vea [Plan for high availability and disaster recovery in Skype Empresarial Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
