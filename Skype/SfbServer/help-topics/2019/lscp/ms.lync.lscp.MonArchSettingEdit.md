---
title: Configuración de archivado Crear nuevo o editar existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
ROBOTS: NOINDEX, NOFOLLOW
description: 'Las configuraciones de archivado se usan para controlar las opciones de archivado de la implementación. Las configuraciones de archivado incluyen la configuración global y, de forma opcional, una o varias configuraciones de sitio y grupo:'
ms.openlocfilehash: 01c14b482fb546a83d9cff8bdbbfd75f8f81f1bd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597734"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>Configuración de archivado: Crear nuevos o editar los existentes
 
Las configuraciones de archivado se usan para controlar las opciones de archivado de la implementación. Las configuraciones de archivado incluyen la configuración global y, de forma opcional, una o varias configuraciones de sitio y grupo:
  
- **Configuración global** La configuración global se crea de forma predeterminada. Puede editar la configuración global, pero no puede eliminar esta configuración de archivado. Si intenta eliminarla, todas las opciones se restablecerán a los valores predeterminados.
    
- **Configuración del sitio (opcional)** Puede especificar una o varias configuraciones de archivado de sitios, cada una de las cuales puede configurar para controlar las opciones de archivado de un sitio específico. Una configuración de sitio anula la configuración global, pero solo para los sitios especificados en las configuraciones de sitios de archivado. Puede editar o eliminar las configuraciones de sitios.
    
- **Configuración del grupo (opcional)** Puede especificar una o varias configuraciones de archivado de grupo para controlar las opciones de archivado de un grupo específico. Una configuración de grupo anula la configuración global y la configuración del sitio, pero solo para los grupos especificados en las configuraciones de grupos de archivado. Puede editar o eliminar las configuraciones de grupos.
    
> [!NOTE]
> Las configuraciones de archivado se aplican a los usuarios que se hospedaron en Skype Empresarial Server y, si habilita la opción de integración de Microsoft Exchange para usar Exchange para almacenar datos de archivado en Microsoft Exchange, a los usuarios que se hospedaron en Exchange. Sin embargo, algunas opciones se implementan de forma ligeramente diferente para los usuarios que se Exchange, como se describe en la sección siguiente. 
  
Para configurar los ajustes para una nueva configuración de archivado o una existente, especifique las siguientes opciones:
- **Nombre** Cada configuración de archivado requiere un nombre. El nombre se determina por el tipo de configuración que está agregando o editando:
    
  - **Configuración global** El nombre predeterminado es Global. Por ejemplo, Organización Contoso de los Estados Unidos.
    
  - **Configuración del sitio** La lista contiene los sitios disponibles en la implementación. Haga clic en un solo sitio para seleccionarlo. Por ejemplo, Centro de datos de Redmond.
    
  - **Configuración del grupo** Especifique un nombre adecuado, que puede ser el nombre de un grupo de servidores front-end específico o un servidor Standard Edition en la implementación. Por ejemplo, División de marketing.
    
- **Descripción** Esto es opcional. Úselo para proporcionar detalles adicionales, como el ámbito o el uso de la configuración. Por ejemplo, Coordinación con departamentos legales de otros sitios.
    
- **Configuración de archivado** Entre las opciones se incluyen las siguientes:
    
  - **Archivar sesiones de mensajería instantánea**
    
  - **Archivar sesiones de mensajería instantánea y conferencias web**
    
  - **Deshabilitar archivado**
    
- **Bloquear sesiones de mensajería instantánea (MI)** o conferencia web si se produce un error en el archivado Entre los errores se incluyen los siguientes:
    
  - **MI** Un error podría ser una base de datos completa o un problema con el servicio de almacenamiento. En este caso, la mensajería instantánea se bloquea para usuarios que tienen el archivado habilitado.
    
  - **Conferencia** Un error puede ser un recurso compartido de archivos no disponible o un problema con el servicio de almacenamiento. En este caso, todas las conferencias activas alojadas en el grupo de servidores en el momento del error se cambian al modo restringido y no se puede activar conferencias nuevas.
    
    Tanto el servicio de mensajería instantánea como de conferencias se recuperan automáticamente después de que se corrigen los errores.
    
- **Integración Exchange Microsoft** Seleccione esta opción si tiene usuarios que están en el Exchange. Con esta opción, Exchange se usa para almacenar datos para esos usuarios, si sus buzones se han colocado en In-Place retención. Si todos los usuarios se encuentran en Exchange, no es necesario configurar bases de datos independientes SQL Server para el almacenamiento de datos de archivado.
    
- **Habilitar la depuración de datos de archivado** Seleccione esta opción para habilitar la depuración y especificar las opciones de depuración, que incluyen lo siguiente:
    
  - Purgado después de un número específico de días que indique.
    
  - Depuración después de exportar los datos de archivado (que incluye los datos que se han cargado en Exchange, si habilita la integración Exchange Microsoft).
    
    > [!NOTE]
    > Si habilita la integración de Microsoft Exchange, la depuración de usuarios ubicados en Exchange y con sus buzones colocados en In-Place la retención se controla mediante Exchange. La única excepción es para los archivos de conferencia, que se almacenan en el recurso compartido de archivos de Lync Server. Estos archivos se purgan del recurso compartido de solo después de que los archivos se hayan exportado (cargado a Exchange), si selecciona la opción para purgar datos después de que se exporten los datos de archivado o después de un número máximo especificado de días, si especifica un número máximo de días para la retención. 
  
Para obtener más información sobre la característica y las funcionalidades de archivado, incluida la integración de Exchange, vea [Plan for archiving in Skype Empresarial Server](../../../plan-your-deployment/archiving/archiving.md), Deploy archiving for [Skype Empresarial Server](../../../deploy/deploy-archiving/deploy-archiving.md)y Manage archiving [in Skype Empresarial Server](../../../manage/archiving/archiving.md).

