---
title: Requisitos de hardware y software para el archivado en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
description: 'Resumen: Leer este tema para obtener información acerca de los requisitos de hardware y software para archiving en Skype para Business Server 2015.'
ms.openlocfilehash: d8d8039e95a3b578551d0db6ff219fe8f3c1e5c5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Requisitos de hardware y software para el archivado en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información acerca de los requisitos de hardware y software para archiving en Skype para Business Server 2015.
  
Skype para archiving empresarial servidor 2015 ahora forma parte de la función de Front-End, por lo que no necesitará instalar a un servidor independiente. Sin embargo, debe tener en cuenta los siguientes requisitos:
  
- Requisitos de infraestructura
    
- Requisitos previos de software
    
- Requisitos de almacenamiento de datos
    
## <a name="infrastructure-requirements"></a>Requisitos de infraestructura

Skype para requerimientos de infraestructura de Archiving de Business Server son los mismos que la implementación de Skype para Business Server. Para obtener más información, consulte [requisitos para su Skype para el entorno empresarial](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). 
  
## <a name="prerequisite-software-requirements"></a>Requisitos previos de software

Requisitos previos de archiving para Skype para Business Server son más simples que las versiones anteriores de Lync Server por los motivos siguientes: 
  
- Porque ya no es una función de servidor de archivado, no es necesario instalar un servidor independiente para archiving. En cambio, los agentes unificados de recolección de datos se instalan y activan de forma automática en cada grupo de servidores front-end Enterprise Edition y en cada servidor Standard Edition. Necesitará habilitar y publicar la topología de archivado por medio del Generador de topologías.
    
- Archiving utiliza el Skype para almacenamiento de archivos de Business Server para el almacenamiento temporal de reunión archivos de contenido, por lo que no configurar un almacén de archivos independientes para archiving.
    
- En Skype para Business Server, Microsoft Message Queue Server no se requiere.
    
## <a name="data-storage-requirements"></a>Requisitos de almacenamiento de datos

Es preciso configurar la infraestructura para el almacenamiento del archivado. Esto incluye seleccionar una de las siguientes opciones o ambas:
  
- **Almacenamiento de información de Microsoft Exchange**. Los archivos del contenido de reuniones, como las presentaciones de PowerPoint, se archivan como datos adjuntos. Si desea almacenar Skype para archivar datos de negocio con datos de cumplimiento de normas de Exchange, debe utilizar Exchange para la implementación de Exchange y asegúrese de que el tamaño máximo de almacenamiento admite el almacenamiento de los archivos de contenido de la reunión. Debe implementar Exchange antes de implementar y habilitar el archivado mediante la opción de integración de Microsoft Exchange. 
    
    Si decide utilizar el almacenamiento de información de Exchange, no es necesario implementar bases de datos SQL Server independientes para archiving, a menos que tenga Skype para usuarios de negocios que no están alojados en los servidores de Exchange. Si implementar archiving mediante la opción de integración de Microsoft Exchange, Skype para archivar datos de negocio se almacena con los datos de cumplimiento de normas de Exchange sólo para los usuarios que están alojados en los servidores de Exchange. 
    
- **Skype para el almacenamiento de archiving Business Server**. Dar soporte a usuarios que no están alojados en servidores de Exchange, o si no desea utilizar la opción de integración de Microsoft Exchange, debe implementar archiving de almacenamiento utilizando una base de datos de SQL Server. Skype para Business Server admite las siguientes versiones de 64 bits de SQL Server:
    
  - Microsoft SQL Server 2008 R2 Enterprise
    
  - Microsoft SQL Server 2008 R2 Standard
    
  - Microsoft SQL Server 2012 Enterprise
    
  - Estándar de Microsoft SQL Server 2012
    
  - Microsoft SQL Server Enterprise de 2014
    
  - Microsoft SQL Server Standard de 2014
    
    > [!NOTE]
    > No se admiten las versiones de Microsoft SQL Server Express para archiving. no se admiten las versiones de 32 bits de SQL Server. Para los requisitos de SQL Server y restricciones adicionales, consulte [requisitos para su Skype para el entorno empresarial](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). 
  
    Debe configurar las plataformas SQL Server antes de implementar y habilitar el archivado. Si la cuenta que se usará para publicar la topología tiene los derechos y permisos de administrador apropiados, puede crear la base de datos de archivado (LcsLog) al publicar la topología. También puede crear la base de datos más adelante, incluida como parte del procedimiento de instalación. Para obtener más información acerca de SQL Server, consulte [SQL Server TechCenter](https://go.microsoft.com/fwlink/p/?linkID=129045).
    
    El aumento en la carga del archivado puede ser considerable. Por lo tanto, debe asegurarse de que es adecuado para servidores frontales archivado está habilitado en el que espacio en disco.
    

