---
title: Configuración de archivado crear nuevos o editar los existentes
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
ROBOTS: NOINDEX, NOFOLLOW
description: 'Las configuraciones de archivado sirven para controlar las opciones de archivado de su implementación. Las configuraciones de archivado constan de la configuración global y, de forma opcional, de una o varias configuraciones de sitio y grupo:'
ms.openlocfilehash: 9c48387c18919b4713c57232ee21f5bf5b22adbe
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32215398"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>Configuración de archivado: Crear nueva o editar existente
 
Las configuraciones de archivado sirven para controlar las opciones de archivado de su implementación. Las configuraciones de archivado constan de la configuración global y, de forma opcional, de una o varias configuraciones de sitio y grupo:
  
- **Configuración global** La configuración global se crea de forma predeterminada. La configuración global se puede editar, pero no eliminar. Si intenta eliminarla, todas las opciones se restablecerán a los valores predeterminados.
    
- **Configuración de sitio (opcional)** Puede especificar uno o varios sitios las configuraciones de archivado, que cada uno de los cuales puede configurar para controlar las opciones de un sitio específico de archivado. Una configuración de sitio reemplaza a la configuración global, pero solo en los sitios especificados en las configuraciones de sitio de archivado. Las configuraciones de sitio se pueden editar o eliminar.
    
- **Configuración de grupo de servidores (opcional)** Puede especificar uno o más del grupo las configuraciones de archivado, al control de las opciones para un grupo específico de archivado. Una configuración de grupo reemplaza a la configuración global y la configuración del sitio, pero solo en los grupos especificados en las configuraciones de grupo de archivado. Las configuraciones de grupo se pueden editar o eliminar.
    
> [!NOTE]
> Las configuraciones de archivado se aplican a los usuarios hospedados en Skype para Business Server y, si habilita la opción de integración de Microsoft Exchange para usar Exchange para almacenar datos de archivado en Microsoft Exchange, para los usuarios alojados en Exchange. Sin embargo, algunas de las opciones se implementan ligeramente diferente para los usuarios alojados en Exchange, tal como se describe en la siguiente sección. 
  
Especifique las siguientes opciones para configurar los ajustes de una nueva configuración de archivado o de una ya existente:
- **Nombre** Cada configuración de archivado requiere un nombre. El nombre se determina por el tipo de configuración que está agregando o editando:
    
  - **Configuración global** El nombre predeterminado es Global. Por ejemplo, Contoso norteamericanos organización.
    
  - **Configuración de sitio** La lista contiene los sitios disponibles en su implementación. Haga clic en un único sitio para seleccionarlo. Por ejemplo, centro de datos de Redmond.
    
  - **Configuración de grupo de servidores** Especifique un nombre adecuado, que puede ser el nombre del servidor Standard Edition o un grupo de servidores Front-End específico de la implementación. Por ejemplo, división de Marketing.
    
- **Descripción** Esto es opcional. Usar para proporcionar información adicional, como el ámbito o el uso de la configuración. Por ejemplo, coordinarse con los departamentos Legal de otros sitios.
    
- **Configuración de archivado** Las opciones incluyen lo siguiente:
    
  - **Archivar sesiones de mensajería instantánea (MI)**
    
  - **Archivar sesiones de mensajería instantánea y conferencias web**
    
  - **Deshabilitar archivado**
    
- **Bloque de mensajería instantánea (IM) o sesiones de conferencia web si se produce un error de archivado** Errores incluyen lo siguiente:
    
  - **Mensajería instantánea** un error podría ser un problema con el servicio de almacenamiento o base de datos completa. En este caso, la mensajería instantánea se bloquea para los usuarios que tienen el archivado habilitado.
    
  - **Conferencia** Un error podría ser un recurso compartido de archivo no está disponible o un problema con el servicio de almacenamiento. En este caso, todas las conferencias activas alojadas en el grupo de servidores en el momento del error se cambian al modo restringido y no se puede activar conferencias nuevas.
    
    Tanto la mensajería instantánea como las conferencias se recuperan automáticamente después de que se corrigen los errores.
    
- **Integración de Microsoft Exchange** Seleccione esta opción si tiene usuarios que están ubicados en Exchange. Con esta opción, Exchange se usa para almacenar los datos de los usuarios, si sus buzones de correo se han colocado en suspensión en contexto. Si todos los usuarios están ubicados en Exchange, no es necesario configurar bases de datos de SQL Server independientes para el almacenamiento de datos de archivado.
    
- **Habilitar la depuración de datos de archivado** Seleccione esta opción para habilitar la depuración y especificar las opciones de depuración, que incluyen lo siguiente:
    
  - Purgado después de un número específico de días que indique.
    
  - Depuración después de los datos de archivado se han exportado (que incluye datos que se han cargado en Exchange, si habilita la integración de Microsoft Exchange).
    
    > [!NOTE]
    > Si habilita la integración de Microsoft Exchange, depuración para los usuarios alojados en Exchange y con sus buzones de correo que se colocan en suspensión en contexto se controla mediante Exchange. La única excepción es para los archivos de la conferencia, que se almacenan en el recurso compartido de archivos de Lync Server. These files are purged from the file share only after the files have been exported (uploaded to Exchange), if you select the option to purge data after the archiving data has been exported, or after the specified maximum number of days, if you specify a maximum number of days for retention. 
  
Para obtener información detallada acerca de la característica de archivado y capacidades, que incluye la integración de Exchange, consulte [Plan para el archivado en Skype para Business Server](../../../plan-your-deployment/archiving/archiving.md), [implementar el archivado de Skype para Business Server](../../../deploy/deploy-archiving/deploy-archiving.md)y [administrar el archivado en Skype para la empresa Servidor](../../../manage/archiving/archiving.md).

