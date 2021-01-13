---
title: Configuración de archivado Crear nueva o editar existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
description: 'Las configuraciones de archivado se usan para controlar las opciones de archivado de la implementación. Las configuraciones de archivado incluyen la configuración global y, de forma opcional, una o varias configuraciones de sitio y grupo:'
ms.openlocfilehash: e0f56e125919bcb27cd9523213c92b7906e89ff0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827020"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>Configuración de archivado: Crear nuevos o editar los existentes
 
Las configuraciones de archivado se usan para controlar las opciones de archivado de la implementación. Las configuraciones de archivado incluyen la configuración global y, de forma opcional, una o varias configuraciones de sitio y grupo:
  
- **Configuración global** La configuración global se crea de forma predeterminada. Puede editar la configuración global, pero no puede eliminar esta configuración de archivado. Si intenta eliminarla, todas las opciones se restablecerán a los valores predeterminados.
    
- **Configuración del sitio (opcional)** Puede especificar una o varias configuraciones de archivado de sitios, cada una de las cuales puede configurar para controlar las opciones de archivado de un sitio específico. Una configuración de sitio anula la configuración global, pero solo para los sitios especificados en las configuraciones de sitios de archivado. Puede editar o eliminar las configuraciones de sitios.
    
- **Configuración del grupo de servidores (opcional)** Puede especificar una o más configuraciones de archivado de grupo para controlar las opciones de archivado de un grupo específico. Una configuración de grupo anula la configuración global y la configuración del sitio, pero solo para los grupos especificados en las configuraciones de grupos de archivado. Puede editar o eliminar las configuraciones de grupos.
    
> [!NOTE]
> Las configuraciones de archivado se aplican a los usuarios que están en Skype Empresarial Server y, si habilita la opción de integración de Microsoft Exchange para usar Exchange 2013 para almacenar datos de archivado en Microsoft Exchange, a los usuarios que están en Exchange 2013. Sin embargo, algunas opciones se implementan de forma ligeramente diferente para los usuarios que se encuentran en Exchange 2013, como se describe en la sección siguiente. 
  
Para configurar los ajustes para una nueva configuración de archivado o una existente, especifique las siguientes opciones:
- **Nombre** Cada configuración de archivado requiere un nombre. El nombre se determina por el tipo de configuración que está agregando o editando:
    
  - **Configuración global** El nombre predeterminado es Global. Por ejemplo, Organización Contoso de los Estados Unidos.
    
  - **Configuración del sitio** La lista contiene los sitios disponibles en la implementación. Haga clic en un solo sitio para seleccionarlo. Por ejemplo, Centro de datos de Redmond.
    
  - **Configuración del grupo de servidores** Especifique un nombre adecuado, que puede ser el nombre de un grupo de servidores front-end específico o un servidor Standard Edition en la implementación. Por ejemplo, División de marketing.
    
- **Descripción** Esto es opcional. Úselo para proporcionar detalles adicionales, como el ámbito o el uso de la configuración. Por ejemplo, Coordinación con departamentos legales de otros sitios.
    
- **Configuración de archivado** Entre las opciones se incluyen las siguientes:
    
  - **Archivar sesiones de mensajería instantánea**
    
  - **Archivar sesiones de mensajería instantánea y conferencias web**
    
  - **Deshabilitar archivado**
    
- **Bloquear sesiones de mensajería instantánea (MI)** o conferencias web si se produce un error de archivado Entre los errores se incluyen los siguientes:
    
  - **Un** error de mensajería instantánea podría ser una base de datos completa o un problema con el servicio de almacenamiento. En este caso, la mensajería instantánea se bloquea para usuarios que tienen el archivado habilitado.
    
  - **Conferencias** Un error podría ser un recurso compartido de archivos no disponible o un problema con el servicio de almacenamiento. En este caso, todas las conferencias activas alojadas en el grupo de servidores en el momento del error se cambian al modo restringido y no se puede activar conferencias nuevas.
    
    Tanto el servicio de mensajería instantánea como de conferencias se recuperan automáticamente después de que se corrigen los errores.
    
- **Integración de Microsoft Exchange** Seleccione esta opción si tiene usuarios que están en Exchange 2013. Con esta opción, Exchange 2013 se usa para almacenar datos de esos usuarios, si sus buzones se han colocado en In-Place retención. Si todos los usuarios están ubicados en Exchange 2013, no es necesario configurar bases de datos de SQL Server independientes para el almacenamiento de datos de archivado.
    
- **Habilitar la depuración de datos de archivado** Seleccione esta opción para habilitar la depuración y especificar opciones de depuración, entre las que se incluyen las siguientes:
    
  - Purgado después de un número específico de días que indique.
    
  - Depuración después de exportar los datos de archivado (que incluye los datos que se han cargado en Exchange, si habilita la integración de Microsoft Exchange).
    
    > [!NOTE]
    > Si habilita la integración de Microsoft Exchange, Exchange controla la purga de los usuarios ubicados en Exchange 2013 y con sus buzones de correo en la retención local de In-Place. La única excepción es para los archivos de conferencia, que se almacenan en el recurso compartido de archivos de Lync Server. Estos archivos se purgan del recurso compartido de solo después de que los archivos se hayan exportado (cargado a Exchange), si selecciona la opción para purgar datos después de que se exporten los datos de archivado o después de un número máximo especificado de días, si especifica un número máximo de días para la retención. 
  
Para obtener más información sobre la característica y las capacidades de archivado, incluida la integración de Exchange, vea [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), Deploy archiving for Skype for Business Server [2015](../../deploy/deploy-archiving/deploy-archiving.md)y [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).

