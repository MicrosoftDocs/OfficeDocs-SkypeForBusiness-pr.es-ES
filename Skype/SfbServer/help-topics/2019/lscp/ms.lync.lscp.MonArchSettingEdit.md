---
title: Configuración de archivado crear nuevos o editar los existentes
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
ms.openlocfilehash: 93bddc8bbba3280ae4e40c0031e65acc6965aa72
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2018
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>Configuración de archivado: Crear nueva o editar existente
 
Las configuraciones de archivado sirven para controlar las opciones de archivado de su implementación. Las configuraciones de archivado constan de la configuración global y, de forma opcional, de una o varias configuraciones de sitio y grupo:
  
- **Configuración global** La configuración global se crea de forma predeterminada. La configuración global se puede editar, pero no eliminar. Si intenta eliminarla, todas las opciones se restablecerán a los valores predeterminados.
    
- **Configuración de sitio (opcional)** Puede especificar uno o varios sitios las configuraciones de archivado, que cada uno de los cuales puede configurar para controlar las opciones de un sitio específico de archivado. Una configuración de sitio reemplaza a la configuración global, pero solo en los sitios especificados en las configuraciones de sitio de archivado. Las configuraciones de sitio se pueden editar o eliminar.
    
- **Configuración de grupo de servidores (opcional)** Puede especificar uno o más del grupo las configuraciones de archivado, al control de las opciones para un grupo específico de archivado. Una configuración de grupo reemplaza a la configuración global y la configuración del sitio, pero solo en los grupos especificados en las configuraciones de grupo de archivado. Las configuraciones de grupo se pueden editar o eliminar.
    
> [!NOTE]
> Las configuraciones de archivado se aplican a los usuarios hospedados en Skype para Business Server y, si habilita la opción de integración de Microsoft Exchange para usar Exchange 2013 para almacenar datos de archivado en Microsoft Exchange, para los usuarios alojados en Exchange 2013. Sin embargo, algunas de las opciones se implementan ligeramente diferente para los usuarios alojados en Exchange 2013, tal como se describe en la siguiente sección. 
  
Especifique las siguientes opciones para configurar los ajustes de una nueva configuración de archivado o de una ya existente:
- **Nombre** Cada configuración de archivado requiere un nombre. El nombre se determina por el tipo de configuración que está agregando o editando:
    
  - **Configuración global** El nombre predeterminado es Global. Por ejemplo, Contoso norteamericanos organización.
    
  - **Configuración de sitio** La lista contiene los sitios disponibles en su implementación. Haga clic en un único sitio para seleccionarlo. Por ejemplo, centro de datos de Redmond.
    
  - **Configuración de grupo de servidores** Especifique un nombre adecuado, que puede ser el nombre del servidor Standard Edition o un grupo de servidores Front-End específico de la implementación. Por ejemplo, división de Marketing.
    
- **Descripción** Esto es opcional. Usar para proporcionar información adicional, como el ámbito o el uso de la configuración. Por ejemplo, coordinarse con los departamentos Legal de otros sitios.
    
- **Configuración de archivado** Las opciones incluyen lo siguiente:
    
  - **Archivar sesiones de mensajería instantánea**
    
  - **Archivar sesiones de mensajería instantánea y conferencias web**
    
  - **Deshabilitar archivado**
    
- **Bloque de mensajería instantánea (IM) o sesiones de conferencia web si se produce un error de archivado** Errores incluyen lo siguiente:
    
  - **Mensajería instantánea** un error podría ser un problema con el servicio de almacenamiento o base de datos completa. En este caso, la mensajería instantánea se bloquea para los usuarios que tienen el archivado habilitado.
    
  - **Conferencia** Un error podría ser un recurso compartido de archivo no está disponible o un problema con el servicio de almacenamiento. En este caso, todas las conferencias activas hospedadas en el grupo de servidores en el momento del error se cambian al modo restringido y no se puede activar conferencias nuevas.
    
    Tanto el servicio de mensajería instantánea como el servicio de conferencias se recuperan automáticamente después de que se corrijan los errores.
    
- **Integración de Microsoft Exchange** Seleccione esta opción si tiene usuarios que están hospedados en Exchange 2013. Con esta opción, Exchange 2013 se usa para almacenar los datos de los usuarios, si sus buzones de correo se han colocado en suspensión en contexto. Si todos los usuarios están hospedados en Exchange 2013, no es necesario configurar bases de datos de SQL Server independientes para el almacenamiento de datos de archivado.
    
- **Habilitar la depuración de datos de archivado** Seleccione esta opción para habilitar la depuración y especificar las opciones de depuración, que incluyen lo siguiente:
    
  - Purgado después de un número específico de días que indique.
    
  - Depuración después de los datos de archivado se han exportado (que incluye datos que se han cargado en Exchange, si habilita la integración de Microsoft Exchange).
    
    > [!NOTE]
    > Si habilita la integración de Microsoft Exchange, depuración para los usuarios alojados en Exchange 2013 y con sus buzones de correo que se colocan en suspensión en contexto se controla mediante Exchange. La única excepción es para los archivos de la conferencia, que se almacenan en el recurso compartido de archivos de Lync Server. Estos archivos se purgan desde el recurso compartido de archivos sólo después de que los archivos se han exportado (que se cargan a Exchange), si selecciona la opción para purgar los datos después de haber exportado los datos de archivado, o después del número máximo especificado de días, si especifica un número máximo de días de retención. 
  
Para obtener información detallada acerca de la característica de archivado y capacidades, que incluye la integración de Exchange, vea [Planear el archivado en Skype para Business Server 2015](../../../plan-your-deployment/archiving/archiving.md), [implementar el archivado de Skype para Business Server 2015](../../../deploy/deploy-archiving/deploy-archiving.md)y [administrar el archivado en Skype para 2015 empresariales de servidor](../../../manage/archiving/archiving.md).

