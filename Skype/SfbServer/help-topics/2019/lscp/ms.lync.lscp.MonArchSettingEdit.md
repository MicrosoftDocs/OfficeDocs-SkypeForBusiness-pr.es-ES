---
title: Configuración de archivado crear nuevo o editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
ROBOTS: NOINDEX, NOFOLLOW
description: 'Las configuraciones de archivado sirven para controlar las opciones de archivado de su implementación. Las configuraciones de archivado constan de la configuración global y, de forma opcional, de una o varias configuraciones de sitio y grupo:'
ms.openlocfilehash: 68d5de88fc56441989e8ffc9ceabfd3236179d1f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291981"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>Configuración de archivado: Crear nueva o editar existente
 
Las configuraciones de archivado sirven para controlar las opciones de archivado de su implementación. Las configuraciones de archivado constan de la configuración global y, de forma opcional, de una o varias configuraciones de sitio y grupo:
  
- **Configuración global** La configuración global se crea de forma predeterminada. La configuración global se puede editar, pero no eliminar. Si intenta eliminarla, todas las opciones se restablecerán a los valores predeterminados.
    
- **Configuración del sitio (opcional)** Puede especificar una o más configuraciones de archivado de sitio, cada una de las cuales puede configurar para controlar las opciones de archivado de un sitio específico. Una configuración de sitio reemplaza a la configuración global, pero solo en los sitios especificados en las configuraciones de sitio de archivado. Las configuraciones de sitio se pueden editar o eliminar.
    
- **Configuración del grupo (opcional)** Puede especificar una o más configuraciones de archivado de grupo para controlar las opciones de archivado de un grupo específico. Una configuración de grupo reemplaza a la configuración global y la configuración del sitio, pero solo en los grupos especificados en las configuraciones de grupo de archivado. Las configuraciones de grupo se pueden editar o eliminar.
    
> [!NOTE]
> Las configuraciones de archivado se aplican a los usuarios alojados en Skype empresarial Server y, si habilita la opción de integración de Microsoft Exchange para usar Exchange para almacenar los datos de archivado en Microsoft Exchange, para los usuarios alojados en Exchange. Sin embargo, algunas opciones se implementan de forma ligeramente distinta para los usuarios alojados en Exchange, como se describe en la sección siguiente. 
  
Especifique las siguientes opciones para configurar los ajustes de una nueva configuración de archivado o de una ya existente:
- **Nombre** Cada configuración de archivado requiere un nombre. El nombre se determina por el tipo de configuración que está agregando o editando:
    
  - **Configuración global** El nombre predeterminado es global. Por ejemplo, organización de la Norteamérica de contoso.
    
  - **Configuración del sitio** La lista contiene los sitios disponibles en la implementación. Haga clic en un solo sitio para seleccionarlo. Por ejemplo, centro de datos de Redmond.
    
  - **Configuración del grupo** Especifique un nombre apropiado, que puede ser el nombre de un grupo de servidores front-end específico o de un servidor Standard Edition en su implementación. Por ejemplo, División de marketing.
    
- **Descripción** Esto es opcional. Utilícelo para proporcionar detalles adicionales, como el ámbito o el uso de la configuración. Por ejemplo, coordine con departamentos jurídicos de otros sitios.
    
- **Configuración** de archivado Entre las opciones se incluyen las siguientes:
    
  - **Archivar sesiones de mensajería instantánea (MI)**
    
  - **Archivar sesiones de mensajería instantánea y conferencias web**
    
  - **Deshabilitar archivado**
    
- **Bloquear sesiones de mensajería instantánea (mi) o conferencias web si falla** el archivado Entre los errores se incluyen los siguientes:
    
  - **Mensaje instantáneo** un error puede ser una base de datos completa o un problema con el servicio de almacenamiento. En este caso, la mensajería instantánea se bloquea para los usuarios que tienen el archivado habilitado.
    
  - **Conferencias** Un error podría ser un recurso compartido de archivos no disponible o un problema con el servicio de almacenamiento. En este caso, todas las conferencias activas alojadas en el grupo de servidores en el momento del error se cambian al modo restringido y no se puede activar conferencias nuevas.
    
    Tanto la mensajería instantánea como las conferencias se recuperan automáticamente después de que se corrigen los errores.
    
- **Integración con Microsoft Exchange** Seleccione esta opción si tiene usuarios alojados en Exchange. Con esta opción, Exchange se usa para almacenar datos de esos usuarios, si sus buzones se han colocado en una conservación local. Si todos los usuarios están alojados en Exchange, no es necesario configurar bases de datos de SQL Server independientes para el almacenamiento de datos de archivado.
    
- **Habilitar la purga de datos de archivado** Seleccione esta opción para habilitar la purga y especificar las opciones de purgado, entre las que se incluyen las siguientes:
    
  - Purgado después de un número específico de días que indique.
    
  - Purgar después de exportar los datos de archivado (que incluye los datos que se han cargado en Exchange, si se habilita la integración de Microsoft Exchange).
    
    > [!NOTE]
    > Si habilita la integración de Microsoft Exchange, la depuración de usuarios alojados en Exchange y con sus buzones colocados en la conservación local está controlada por Exchange. La única excepción es para los archivos de conferencia, que se almacenan en el recurso compartido de archivos de Lync Server. These files are purged from the file share only after the files have been exported (uploaded to Exchange), if you select the option to purge data after the archiving data has been exported, or after the specified maximum number of days, if you specify a maximum number of days for retention. 
  
Para más información sobre la característica y capacidades de archivado, como la integración de Exchange, consulte [planear el archivado en Skype empresarial Server](../../../plan-your-deployment/archiving/archiving.md), [implementar el archivado para Skype empresarial Server](../../../deploy/deploy-archiving/deploy-archiving.md)y [administrar el archivado en Skype empresarial. Servidor](../../../manage/archiving/archiving.md).

