---
title: Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 'Resumen: Lea este tema para obtener más información acerca de los requisitos de hardware y software para el servidor de Chat persistente en Skype para Business Server 2015.'
ms.openlocfilehash: 8db3bda71cb27ec059dcf4c73f8d4754ffcb8b2d
ms.sourcegitcommit: 1530670628e8645b9f8e2fc2786dddd989a9e908
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2018
ms.locfileid: "20246659"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener más información acerca de los requisitos de hardware y software para el servidor de Chat persistente en Skype para Business Server 2015.
  
Servidor de Chat persistente puede instalarse con Skype para Business Server 2015 Enterprise Edition o Standard Edition. Requisitos dependen de qué edición de Skype para Business Server 2015 instaló y los requisitos de rendimiento de su negocio. Enterprise Edition puede admitir hasta 80 000 usuarios simultáneos; Standard Edition puede admitir hasta 20 000 usuarios simultáneos. El chat persistente consiste de un componente front-end y de un componente de base de datos de SQL back-end.
  
Antes de implementar servidores de Chat persistente, debe asegurarse de que se cumplen los siguientes requisitos de hardware y software:
  
- Hardware que cumpla los requisitos mínimos para admitir Skype para Business Server 2015, servidor de Chat persistente, servidores de base de datos y servidores de archivos. Para obtener más información, vea [requisitos de servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Sistemas operativos y software de base de datos compatibles
    
    Para obtener información detallada acerca de los sistemas operativos compatibles y software de base de datos y Windows actualizar requisitos, vea [requisitos de servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Skype para Business Server 2015 Front-End Server. El servidor Front-End es la base para protocolo SIP (Session Initiation) enrutamiento, que posibilita la comunicación entre equipos que ejecutan el servidor de Chat persistente y la funcionalidad de Chat persistente. 
    
- Software Message Queue. Usada por el servicio de servidor de Chat persistente y cumplimiento de Chat persistente, si se ha implementado.
    
Las secciones siguientes describen los requisitos específicos para el servidor de Chat persistente y la base de datos que almacena los datos de Chat persistente.
  
## <a name="front-end-server-requirements"></a>Requisitos del servidor front-end

Requisitos de Front-End Server dependen de si se implementa el servidor de Chat persistente con Skype para Business Server 2015 Enterprise Edition o Standard Edition.
  
- Si va a implementar el servidor de Chat persistente con Skype para Business Server 2015 Enterprise Edition, puede implementar la Persistent Chat Server servidor Front-End en uno o varios equipos independientes en el grupo de servidores Enterprise Edition. No se puede combinar el Persistent Chat servidores Front-End en el Skype para profesionales de 2015 Front-End Server. 
    
    Un único Persistent Chat Server servidor Front-End puede admitir 20.000 usuarios activos. Puede tener un grupo de servidores de Chat persistente con un máximo de 4 active servidores front-end, desde allí, admitir un total de 80.000 usuarios simultáneos. 
    
- Si va a implementar el servidor de Chat persistente con Skype para 2015 Business Server Standard Edition, se puede combinar el Chat persistente con el servidor Front-End. Esta implementación de servidor único puede admitir hasta 20 000 usuarios. 
    
## <a name="persistent-chat-server-database-requirements"></a>Requisitos de base de datos de servidor de Chat persistentes

Persistent Chat Server requiere el software de base de datos de SQL Server para almacenar el historial de salones de chat y contenido, datos de configuración, datos de aprovisionamiento de usuario y otros metadatos relevantes. De forma opcional, se utiliza la base de datos de cumplimiento de Chat persistente para almacenar datos de cumplimiento. Las bases de datos de chat persistente se pueden combinar en el mismo SQL Server o, incluso, en la misma instancia de SQL, como las bases de datos back-end. 
  
- Si va a instalar el servidor de Chat persistente con Skype para Business Server 2015 Enterprise Edition, para garantizar un rendimiento óptimo, se recomienda que instale el almacén de archivos de Chat persistente.
    
- Si va a instalar el servidor de Chat persistente con Skype para Business Server 2015 Standard edition, puede implementar la Persistent Chat almacén de servidor Back-End en la instancia local de SQL Server Express.
    
- La base de datos de Chat persistente (mgc) y la base de datos de cumplimiento (mgccomp) pueden estar ubicadas en la misma instancia de SQL Server o en diferentes servidores de SQL Server.
    
Para preparar una plataforma de servidor de base de datos, asegúrese de que cada equipo cumpla los requisitos de hardware y, luego, instale el software que se necesita como requisito previo. La plataforma de servidor para los servidores de base de datos de Chat persistente requiere el mismo hardware que el Skype para servidor de base de datos back-end de Business Server 2015. Para obtener información detallada, vea [requisitos de servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
  
Confirma que una de las siguientes aplicaciones de software está instalada en el servidor de bases de datos:

- Microsoft SQL Server 2016 y se debe ejecutar con Skype para Business Server actualización acumulativa 7 o versiones posteriores. Es recomendable que ejecuta SQL Server 2016 con el último service pack. Para obtener información detallada acerca de cómo instalar Microsoft SQL Server 2016, vea [instalar SQL Server 2016](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).

- Microsoft SQL Server 2012 (edición de 64 bits) y se recomienda la ejecución con el último service pack. Para obtener información detallada acerca de cómo instalar Microsoft SQL Server 2012, vea [instalar SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).

- Microsoft SQL Server 2008 R2 (64-bit edition) y se recomienda la ejecución con el último service pack. Para obtener información detallada acerca de cómo instalar Microsoft SQL Server 2008 R2, vea [Instalación de SQL Server (SQL Server 2008 R2)](https://go.microsoft.com/fwlink/p/?LinkId=275702). 
    
## <a name="persistent-chat-server-certificate-requirements"></a>Requisitos de certificado de servidor de Chat persistentes

Para obtener información detallada sobre cómo adquirir certificados, crear la base de datos de SQL Server y crear almacenes de archivos, vea [Implementar Skype para Business Server 2015](../../deploy/deploy.md). 
  
## <a name="for-more-information"></a>Para obtener más información

Para obtener más información sobre los requisitos de hardware y software, mira los siguientes temas:
  
- [Requisitos del servidor para Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Requisitos del entorno para Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

