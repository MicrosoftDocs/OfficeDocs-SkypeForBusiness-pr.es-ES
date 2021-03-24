---
title: Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 'Resumen: lea este tema para obtener información sobre los requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015.'
ms.openlocfilehash: d4609d557e5c55b680c4c0761f24cc4f320afcbd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095114"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información sobre los requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015.
  
El servidor de chat persistente se puede instalar con Skype Empresarial Server 2015 Enterprise Edition o Standard Edition. Los requisitos dependen de la edición de Skype Empresarial Server 2015 que haya instalado y de los requisitos de rendimiento de su empresa. Enterprise Edition puede admitir hasta 80 000 usuarios simultáneos; Standard Edition puede admitir hasta 20 000 usuarios simultáneos. El chat persistente consta de un componente front-end, así como de un componente de base de datos SQL back-end.
  
Antes de implementar el servidor de chat persistente, debe asegurarse de que se cumplen los siguientes requisitos de hardware y software:
  
- Hardware que cumple los requisitos mínimos para admitir Skype Empresarial Server 2015, servidor de chat persistente, servidores de bases de datos y servidores de archivos. Para obtener más información, vea [Requisitos del servidor para Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Software de base de datos y sistema operativo admitidos.
    
    Para obtener más información sobre los sistemas operativos y el software de base de datos admitidos, y los requisitos de windows update, vea Requisitos del servidor [para Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Servidor front-end de Skype Empresarial Server 2015. El servidor front-end es la base para el enrutamiento del Protocolo de inicio de sesión (SIP), que permite la comunicación entre equipos que ejecutan el servidor de chat persistente y la funcionalidad de chat persistente. 
    
- Software de cola de mensajes. Usado por el servidor de chat persistente y el servicio de cumplimiento de chat persistente, si se implementa.
    
En las secciones siguientes se describen los requisitos específicos para el servidor de chat persistente y la base de datos que almacena los datos de chat persistente.

> [!NOTE] 
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, vea [Introducción a la actualización de Microsoft Teams](/microsoftteams/upgrade-start-here). Si necesita usar el chat persistente, las opciones son migrar usuarios que requieren esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015. 
  
## <a name="front-end-server-requirements"></a>Requisitos del servidor front-end

Los requisitos del servidor front-end dependen de si está implementando el servidor de chat persistente con Skype Empresarial Server 2015 Enterprise Edition o Standard Edition.
  
- Si va a implementar el servidor de chat persistente con Skype Empresarial Server 2015 Enterprise Edition, puede implementar el servidor front-end del servidor de chat persistente en uno o varios equipos independientes del grupo de servidores Enterprise Edition. No puede colocar los servidores front-end de chat persistente en el servidor front-end de Skype Empresarial Server 2015. 
    
    Un único servidor front-end del servidor de chat persistente puede admitir 20.000 usuarios activos. Puede tener un grupo de servidores de chat persistente con hasta 4 front-end activos, lo que admite un total de 80.000 usuarios simultáneos. 
    
- Si va a implementar el servidor de chat persistente con Skype Empresarial Server 2015 Standard Edition, puede asociar el chat persistente con el servidor front-end. Esta implementación de un solo servidor puede admitir hasta 20 000 usuarios. 
    
## <a name="persistent-chat-server-database-requirements"></a>Requisitos de base de datos del servidor de chat persistente

El servidor de chat persistente requiere SQL Server de base de datos para almacenar el contenido y el historial del salón de chat, los datos de configuración, los datos de aprovisionamiento de usuarios y otros metadatos relevantes. Opcionalmente, usa la base de datos de cumplimiento de chat persistente para almacenar datos de cumplimiento. Las bases de datos de chat persistente se pueden colocar en la misma SQL Server, o incluso en la misma instancia SQL, que las bases de datos back-end. 
  
- Si va a instalar el servidor de chat persistente con Skype Empresarial Server 2015 Enterprise Edition, para garantizar un rendimiento óptimo, se recomienda instalar el almacén de archivos de chat persistente.
    
- Si va a instalar el servidor de chat persistente con la edición estándar de Skype Empresarial Server 2015, puede implementar el servidor back-end del almacén de chat persistente en la instancia SQL Server Express local.
    
- La base de datos de chat persistente (mgc) y la base de datos de cumplimiento (mgccomp) se pueden encontrar en la misma instancia de SQL Server o en servidores de SQL diferentes.
    
Para preparar una plataforma de servidor de base de datos, asegúrese de que cada equipo cumple los requisitos de hardware y, a continuación, instale el software de requisitos previos. La plataforma de servidor para los servidores de bases de datos de chat persistente requiere el mismo hardware que el servidor de bases de datos back-end de Skype Empresarial Server 2015. Para obtener más información, vea [Requisitos del servidor para Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
  
En el servidor de bases de datos, asegúrese de que está instalada una de las siguientes aplicaciones de software:

- Microsoft SQL Server 2017 con el service pack más reciente.

- Microsoft SQL Server 2016 con Service Pack 1 y debe ejecutar con la actualización acumulativa de Skype Empresarial Server 7 o versiones posteriores. Se recomienda ejecutar SQL Server 2016 con el service pack más reciente. Para obtener más información sobre cómo instalar Microsoft SQL Server 2016, vea [Install SQL Server 2016](/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).

- Microsoft SQL Server 2014 y debe ejecutar con la actualización acumulativa 6 o versiones posteriores de Skype Empresarial Server. Se recomienda ejecutar SQL Server 2014 con el service pack más reciente. Para obtener más información sobre cómo instalar Microsoft SQL Server 2014, [vea Install SQL Server 2014](/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).

- Microsoft SQL Server 2012 (edición de 64 bits) y se recomienda ejecutar con el service pack más reciente. Para obtener más información sobre cómo instalar Microsoft SQL Server 2012, vea [Install SQL Server 2012](/previous-versions/sql/sql-server-2012/bb500395(v=sql.110)).

## <a name="persistent-chat-server-certificate-requirements"></a>Requisitos de certificado del servidor de chat persistente

Para obtener más información acerca de la adquisición de certificados, la creación de la base de datos SQL Server y la creación de almacenes de archivos, vea [Deploy Skype for Business Server 2015](../../deploy/deploy.md). 
  
## <a name="for-more-information"></a>Más información

Para obtener más información acerca de los requisitos de hardware y software, consulte los siguientes temas:
  
- [Requisitos del servidor para Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Requisitos de entorno para Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
