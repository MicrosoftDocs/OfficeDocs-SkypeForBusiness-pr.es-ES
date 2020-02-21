---
title: Requisitos de hardware y software para el servidor de chat persistente en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 'Resumen: Lea este tema para obtener información sobre los requisitos de hardware y software para el servidor de chat persistente en Skype empresarial Server 2015.'
ms.openlocfilehash: 39204b675feff78fef56ee02e1c7e381eb36f65f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213236"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Requisitos de hardware y software para el servidor de chat persistente en Skype empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información sobre los requisitos de hardware y software para el servidor de chat persistente en Skype empresarial Server 2015.
  
El servidor de chat persistente se puede instalar con Skype empresarial Server 2015 Enterprise Edition o Standard Edition. Los requisitos dependen de la edición de Skype empresarial Server 2015 que haya instalado y de los requisitos de rendimiento de su empresa. Enterprise Edition puede admitir hasta 80.000 usuarios simultáneos; Standard Edition puede admitir hasta 20.000 usuarios simultáneos. El chat persistente consta de un componente front-end y de un componente de base de datos SQL back-end.
  
Antes de implementar el servidor de chat persistente, debe asegurarse de que se cumplen los siguientes requisitos de hardware y software:
  
- Hardware que cumple los requisitos mínimos para admitir Skype empresarial Server 2015, servidor de chat persistente, servidores de bases de datos y servidores de archivos. Para obtener más información, consulte [Server Requirements for Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Sistema operativo y software de base de datos admitidos.
    
    Para obtener más información sobre los sistemas operativos y el software de bases de datos compatibles, y los requisitos de Windows Update, consulte [Server Requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Servidor front-end de Skype empresarial Server 2015. El servidor front-end es la base del enrutamiento del Protocolo de inicio de sesión (SIP), que hace posible la comunicación entre equipos que ejecutan el servidor de chat persistente y la funcionalidad de chat persistente. 
    
- Software de Message Queue Server. Lo usa el servidor de chat persistente y el servicio de cumplimiento de chat persistente, si se implementan.
    
En las secciones siguientes se describen los requisitos específicos para el servidor de chat persistente y la base de datos que almacena los datos de chat persistente.

> [!NOTE] 
> Chat persistente está disponible en Skype empresarial Server 2015, pero ya no se admite en Skype empresarial Server 2019. La misma funcionalidad está disponible en Microsoft Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams](/microsoftteams/upgrade-start-here). Si necesita usar chat persistente, tiene la opción de migrar los usuarios que necesitan esta funcionalidad a Microsoft Teams o seguir usando Skype empresarial Server 2015. 
  
## <a name="front-end-server-requirements"></a>Requisitos del servidor front-end

Los requisitos de los servidores front-end dependen de si está implementando el servidor de chat persistente con Skype empresarial Server 2015 Enterprise Edition o Standard Edition.
  
- Si va a implementar un servidor de chat persistente con Skype empresarial Server 2015 Enterprise Edition, puede implementar el servidor front-end del servidor de chat persistente en uno o más equipos independientes en el grupo de servidores Enterprise Edition. No puede combinarr los servidores front-end de chat persistente en el servidor front-end de Skype empresarial Server 2015. 
    
    Un solo servidor front-end de servidor de chat persistente puede admitir usuarios activos de 20.000. Puede tener un grupo de servidores de chat persistente con hasta 4 servidores front-end activos, lo que admite un total de 80.000 usuarios simultáneos. 
    
- Si va a implementar un servidor de chat persistente con Skype empresarial Server 2015 Standard Edition, puede combinar chat persistente con el servidor front-end. Esta implementación de servidor único puede admitir hasta 20.000 usuarios. 
    
## <a name="persistent-chat-server-database-requirements"></a>Requisitos de la base de datos del servidor de chat persistente

El servidor de chat persistente requiere el software de base de datos de SQL Server para almacenar el historial y el contenido del salón de chat, los datos de configuración, el aprovisionamiento de usuarios y otros metadatos relevantes. Opcionalmente, usa la base de datos de cumplimiento de chat persistente para almacenar datos de cumplimiento. Las bases de datos de chat persistente se pueden combinar en el mismo SQL Server o incluso en la misma instancia de SQL, como las bases de datos back-end. 
  
- Si va a instalar un servidor de chat persistente con Skype empresarial Server 2015 Enterprise Edition, para garantizar un rendimiento óptimo, se recomienda que instale el almacén de archivos de chat persistente.
    
- Si va a instalar un servidor de chat persistente con Skype empresarial Server 2015 Standard Edition, puede implementar el servidor back-end del almacén de chat persistente en la instancia local de SQL Server Express.
    
- La base de datos de chat persistente (MGC) y la base de datos de cumplimiento (mgccomp) pueden encontrarse en la misma instancia de SQL Server o en diferentes servidores SQL Server.
    
Para preparar una plataforma de servidor de base de datos, asegúrese de que cada equipo cumple los requisitos de hardware y, a continuación, instale el software necesario como requisito previo. La plataforma de servidor para los servidores de base de datos de chat persistente requiere el mismo hardware que el servidor de base de datos back-end de Skype empresarial Server 2015. Para obtener más información, consulte [Server Requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
  
En el servidor de bases de datos, asegúrese de que esté instalada una de las siguientes aplicaciones de software:

- Microsoft SQL Server 2017 con el último Service Pack.

- Microsoft SQL Server 2016 con Service Pack 1 y debe ejecutarse con la actualización acumulativa 7 o versiones posteriores de Skype empresarial Server. Se recomienda ejecutar SQL Server 2016 con el último Service Pack. Para obtener más información sobre cómo instalar Microsoft SQL Server 2016, consulte [instalar SQL server 2016](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).

- Microsoft SQL Server 2014 y debe ejecutarse con la actualización acumulativa 6 o versiones posteriores de Skype empresarial Server. Se recomienda ejecutar SQL Server 2014 con el último Service Pack. Para obtener más información sobre cómo instalar Microsoft SQL Server 2014, consulte [instalar SQL server 2014](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).

- Microsoft SQL Server 2012 (edición de 64 bits) y se recomienda ejecutar con el Service Pack más reciente. Para obtener más información sobre cómo instalar Microsoft SQL Server 2012, consulte [instalar SQL server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).

## <a name="persistent-chat-server-certificate-requirements"></a>Requisitos de certificados del servidor de chat persistente

Para obtener información detallada acerca de la adquisición de certificados, la creación de la base de datos de SQL Server y la creación de almacenes de archivos, consulte [deploy Skype for Business Server 2015](../../deploy/deploy.md). 
  
## <a name="for-more-information"></a>Más información

Para obtener más información acerca de los requisitos de hardware y software, vea los siguientes temas:
  
- [Requisitos de servidor para Skype empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Requisitos del entorno para Skype empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

