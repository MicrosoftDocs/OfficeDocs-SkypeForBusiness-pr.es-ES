---
title: Configuración de archivado crear nuevo o editar existente
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
description: 'Las configuraciones de archivado sirven para controlar las opciones de archivado de su implementación. Las configuraciones de archivado constan de la configuración global y, de forma opcional, de una o varias configuraciones de sitio y grupo:'
ms.openlocfilehash: 49227ded326c893d42852796e9c783a2dc4096cd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>Configuración de archivado: Crear nueva o editar existente
 
Las configuraciones de archivado sirven para controlar las opciones de archivado de su implementación. Las configuraciones de archivado constan de la configuración global y, de forma opcional, de una o varias configuraciones de sitio y grupo:
  
- **Configuración global** La configuración global se crea de forma predeterminada. La configuración global se puede editar, pero no eliminar. Si intenta eliminarla, todas las opciones se restablecerán a los valores predeterminados.
    
- **Configuración del sitio (opcional)** Puede especificar uno o más archivado configuraciones de sitios, que cada uno de los cuales puede configurar al control de opciones de un sitio específico de archivado. Una configuración de sitio reemplaza a la configuración global, pero solo en los sitios especificados en las configuraciones de sitio de archivado. Las configuraciones de sitio se pueden editar o eliminar.
    
- **Configuración del conjunto (opcional)** Puede especificar uno o más grupo archivado configuraciones, al control de opciones de un grupo específico de archivado. Una configuración de grupo reemplaza a la configuración global y la configuración del sitio, pero solo en los grupos especificados en las configuraciones de grupo de archivado. Las configuraciones de grupo se pueden editar o eliminar.
    
> [!NOTE]
> Archivado de configuraciones que se aplican a los usuarios alojados en Skype para Business Server y, si habilita la opción de integración de Microsoft Exchange usar Exchange 2013 para almacenar datos de archiving en Microsoft Exchange, los usuarios alojados en Exchange de 2013. Sin embargo, algunas opciones se implementan ligeramente diferente para usuarios alojados en Exchange de 2013, tal como se describe en la sección siguiente. 
  
Especifique las siguientes opciones para configurar los ajustes de una nueva configuración de archivado o de una ya existente:
- **Nombre** Cada configuración de archivado requiere un nombre. El nombre se determina por el tipo de configuración que está agregando o editando:
    
  - **Configuración global** El nombre predeterminado es Global. Por ejemplo, Contoso North American organización.
    
  - **Configuración de sitio** La lista contiene los sitios disponibles en la implementación. Haga clic en un solo sitio para seleccionarlo. Por ejemplo, el centro de datos de Redmond.
    
  - **Configuración del grupo** Especifique un nombre apropiado, que puede ser el nombre del servidor Standard Edition o un grupo específico de Front-End de su implementación. Por ejemplo, división de Marketing.
    
- **Descripción** Esto es opcional. Utilizarlo para proporcionar detalles adicionales, como el ámbito o el uso de la configuración. Por ejemplo, coordinar con los departamentos legales de otros sitios.
    
- **Configuración de archivado** Las siguientes opciones:
    
  - **Archivar sesiones de mensajería instantánea**
    
  - **Archivar sesiones de mensajería instantánea y conferencias web**
    
  - **Deshabilitar archivado**
    
- **Bloquear mensajería instantánea (IM) o sesiones de conferencias web si se produce un error de archivado** Los errores siguientes:
    
  - **IM** un error podría ser un problema con el servicio de almacenamiento o base de datos completa. En este caso, la mensajería instantánea se bloquea para los usuarios que tienen el archivado habilitado.
    
  - **Conferencia** Un error podría ser un problema con el servicio de almacenamiento de información o un recurso compartido de archivo no disponible. En este caso, todas las conferencias activas hospedadas en el grupo de servidores en el momento del error se cambian al modo restringido y no se puede activar conferencias nuevas.
    
    Tanto el servicio de mensajería instantánea como el servicio de conferencias se recuperan automáticamente después de que se corrijan los errores.
    
- **Integración de Microsoft Exchange** Seleccione esta opción si tiene usuarios que están alojados en Exchange de 2013. Con esta opción, Exchange 2013 se utiliza para almacenar los datos de los usuarios si sus buzones se encuentran en posesión en el lugar. Si todos los usuarios alojados en Exchange de 2013, no necesitará configurar bases de datos SQL Server independientes para el almacenamiento de archiving de datos.
    
- **Habilitar la purga de datos de archivado** Seleccione esta opción para habilitar la purga y especificar opciones de purgantes, que incluyen los siguientes:
    
  - Purgado después de un número específico de días que indique.
    
  - Purga de los datos de archivado se ha exportado (que incluye los datos que se han cargado a Exchange, si habilita la integración de Microsoft Exchange).
    
    > [!NOTE]
    > Si habilita la integración de Microsoft Exchange, purga los usuarios alojados en Exchange 2013 y con sus buzones colocados en posesión en el lugar es controlado por Exchange. La única excepción es para los archivos de la conferencia, que se almacenan en el recurso compartido de archivos de Lync Server. Estos archivos se purgan desde el recurso compartido de archivo después de que los archivos se han exportado (cargado a Exchange), si selecciona la opción para purgar los datos después de haber exportado los datos de archivado o después del número máximo especificado de días, si se especifica un número máximo de días de retención. 
  
Para obtener más información acerca de la característica de archivado y capacidades, incluida la integración de Exchange, consulte [Plan para archiving en Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [implementar archiving de Skype para Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)y [Administrar archiving en Skype para 2015 empresariales de servidor](../../manage/archiving/archiving.md).

