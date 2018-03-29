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
description: 'Resumen: Leer este tema para obtener información acerca de los requisitos de hardware y software para el servidor de Chat persistente en Skype para Business Server 2015.'
ms.openlocfilehash: a56f939360edae0da47198e4a3810f70712b6ab8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información acerca de los requisitos de hardware y software para el servidor de Chat persistente en Skype para Business Server 2015.
  
Servidor de charla persistente puede instalarse con Skype para Business Server 2015 Enterprise Edition o Standard Edition. Requisitos dependen de qué edición de Skype para el año 2015 de Business Server instalado y los requisitos de rendimiento de su negocio. Enterprise Edition puede admitir hasta 80 000 usuarios simultáneos; Standard Edition puede admitir hasta 20 000 usuarios simultáneos. El chat persistente consiste de un componente front-end y de un componente de base de datos de SQL back-end.
  
Antes de implementar el servidor de charla persistente, debe asegurarse de que se cumplen los siguientes requisitos de hardware y software:
  
- Hardware que cumpla los requisitos mínimos para admitir Skype para Business Server 2015, persistente Chat Server, servidores de base de datos y servidores de archivos. Para obtener más información, consulte [requisitos del servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Sistemas operativos y software de base de datos compatibles
    
    Para obtener más información acerca de sistemas operativos y software de base de datos y Windows actualizar requisitos, vea [requisitos del servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Skype de negocios 2015 Front-End Server. El servidor Front-End es la base para el protocolo SIP (Session Initiation) enrutamiento, lo que permite la comunicación entre equipos que ejecutan el servidor de charla persistente y la funcionalidad de Chat persistentes. 
    
- Software Message Queue. Utilizada por el servicio de servidor de charla persistente y cumplimiento de Chat persistentes, si ha implementado.
    
Las secciones siguientes describen los requisitos específicos para el servidor de charla persistente y la base de datos que almacena los datos persistentes de charla.
  
## <a name="front-end-server-requirements"></a>Requisitos del servidor front-end

Requisitos del servidor de extremo frontales dependen de si va a implementar servidor de Chat persistente con Skype para Business Server 2015 Enterprise Edition o Standard Edition.
  
- Si va a implementar servidor de Chat persistente con Skype para 2015 Business Server Enterprise, puede implementar la persistente Chat Server servidor Front-End en uno o más equipos independientes en el grupo de servidores Enterprise Edition. No se puede colocar la persistente Chat servidores frontales en el Skype para servidor Front-End de Business Server 2015. 
    
    Un único persistente Chat Front End Server puede admitir 20.000 usuarios activos. Puede tener un grupo de servidores de charla persistente con hasta 4 activos front-ends, por tanto, admitir un total de 80.000 usuarios simultáneos. 
    
- Si va a implementar servidor de Chat persistente con Skype para 2015 Business Server Standard Edition, puede colocar la charla persistente con el servidor Front-End. Esta implementación de servidor único puede admitir hasta 20 000 usuarios. 
    
## <a name="persistent-chat-server-database-requirements"></a>Requisitos de base de datos de servidor de charla persistentes

Servidor de charla persistente requiere software de base de datos de SQL Server para almacenar el historial del salón de chat y contenido, datos de configuración, datos de configuración de usuario y otros metadatos relevantes. Opcionalmente, utiliza la base de datos de cumplimiento de Chat persistente para almacenar datos de cumplimiento de normas. Las bases de datos de chat persistente se pueden combinar en el mismo SQL Server o, incluso, en la misma instancia de SQL, como las bases de datos back-end. 
  
- Si va a instalar al servidor de charla persistente con Skype para 2015 Business Server Enterprise, para garantizar un rendimiento óptimo, se recomienda que instale el almacén de archivos Chat persistente.
    
- Si va a instalar al servidor de charla persistente con Skype para 2015 Business Server Standard edition, puede implementar el Chat almacén nuevo final servidor persistente en la instancia local de SQL Server Express.
    
- La base de datos persistente Chat (mgc) y la base de datos de cumplimiento de normas (mgccomp) pueden encontrarse en la misma instancia de SQL Server o en diferentes servidores de SQL.
    
Para preparar una plataforma de servidor de base de datos, asegúrese de que cada equipo cumpla los requisitos de hardware y, luego, instale el software que se necesita como requisito previo. La plataforma de servidor para los servidores de base de datos persistente de charla requiere el mismo hardware que el Skype para el servidor de base de datos back-end de Business Server 2015. Para obtener más información, consulte [requisitos del servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
  
Confirma que una de las siguientes aplicaciones de software está instalada en el servidor de bases de datos:
  
- Microsoft SQL Server 2012. Para obtener más información acerca de cómo instalar Microsoft SQL Server 2012, vea [instalar SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).
    
- Microsoft SQL Server 2008 R2. Para obtener más información acerca de cómo instalar Microsoft SQL Server 2008 R2, vea [Instalación de SQL Server (SQL Server 2008 R2)](https://go.microsoft.com/fwlink/p/?LinkId=275702).
    
## <a name="persistent-chat-server-certificate-requirements"></a>Requisitos de certificados de servidor de charla persistentes

Para obtener más información acerca de cómo adquirir certificados, crear la base de datos de SQL Server y crear almacenes de archivos, vea [Implementar Skype para Business Server 2015](../../deploy/deploy.md). 
  
## <a name="for-more-information"></a>Para obtener más información

Para obtener más información sobre los requisitos de hardware y software, mira los siguientes temas:
  
- [Requisitos del servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Requisitos ambientales para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

