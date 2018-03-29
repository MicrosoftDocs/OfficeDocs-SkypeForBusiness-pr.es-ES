---
title: Configuración de archivado
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: 'Utilice las configuraciones de archivado para controlar opciones para su Skype para la implementación de Business Server, incluyendo la habilitación y deshabilitación de las siguientes opciones de archivado:'
ms.openlocfilehash: e32c42d5ef945b360ce4992ea9a33658bcc4068a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="archiving-configuration"></a>Configuración de archivado
 
Utilice las configuraciones de archivado para controlar opciones para su Skype para la implementación de Business Server, incluyendo la habilitación y deshabilitación de las siguientes opciones de archivado:
  
- Bloquear sesiones de mensajería instantánea o conferencias si no se pueden archivar
    
- Integración con almacenamiento de información de Exchange de 2013, para los usuarios alojados en Exchange de 2013
    
- Purgar datos archivados
    
Las configuraciones de archivado están formadas por la configuración global y, de forma opcional, por una o varias configuraciones de archivado de sitio y grupo:
  
- **Configuración global** La configuración global se crea de forma predeterminada en todos los Skype para implementaciones de servidores empresariales. La configuración global se puede editar, pero no eliminar. Si intenta eliminarla, todas las opciones se restablecerán a los valores predeterminados.
    
- **Configuración del sitio (opcional)** Puede especificar uno o más archivado configuraciones de sitios, que cada uno de los cuales puede configurar al control de opciones de un sitio específico de archivado. Una configuración de sitio reemplaza a la configuración global, pero solo en los sitios especificados en las configuraciones de sitio de archivado. Las configuraciones de sitio se pueden editar o eliminar.
    
- **Configuración del conjunto (opcional)** Puede especificar uno o más grupo Configuración de archivado, al control de opciones de un grupo específico de archivado. Una configuración de grupo reemplaza a la configuración global y la configuración del sitio, pero solo en los grupos especificados en las configuraciones de grupo de archivado. Las configuraciones de grupo se pueden editar o eliminar.
    
> [!NOTE]
> Archivado de configuraciones que se aplican a los usuarios alojados en Skype para Business Server y, si utiliza Exchange para almacenar datos de archivado en Microsoft Exchange, los usuarios alojados en Exchange de 2013, pero se implementan de forma ligeramente distinta para usuarios alojados en Exchange de 2013. En la siguiente sección se describen estas diferencias. 
  
La página **Configuración de archivado** muestra cada directiva de archivado configurada en la implementación. También muestra el nombre de la directiva, el ámbito (global, sitio o usuario) y qué opciones de archivado están habilitadas para cada configuración de archivado. En la página **Configuración de archivado** dispone de las siguientes opciones:
- **Nuevo** Puede agregar uno o varios de cada una de las siguientes configuraciones de archivado opcionales.
    
  - Configuración de sitio
    
  - Configuración del grupo de servidores
    
- **Editar** Puede cambiar las opciones de cualquiera de las configuraciones de archivado que aparecen en la página. Al usar esta opción, puede hacer lo siguiente:
    
  - **Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones de archiving para la configuración de archivado seleccionada. Solo puede mostrar detalles para una configuración de archivado cada vez.
    
  - **Seleccionar todo** Esta opción selecciona todas las configuraciones de archivado en la lista.
    
  - **Eliminar** Esta opción elimina todas las configuraciones de archivado seleccionadas.
    
- **Acción** Puede utilizar esta opción rápidamente habilitar o deshabilitar el archivado de las sesiones de mensajería instantánea o sesiones de conferencias web en cualquier configuración que aparecen en la página, en lugar de modificar la configuración. Las opciones disponibles en **Acción** dependen de qué opción esté especificada actualmente en la configuración de archivado. Todas las opciones están disponibles, excepto la opción en vigor actualmente para la configuración de archivado. Las opciones son estas:
    
  - **Archivar sesiones de mensajería instantánea**
    
  - **Archivar sesiones de mensajería instantánea y conferencias web**
    
  - **Deshabilitar archivado**
    
- **Actualizar** Puede actualizar la página de **Configuración de Archiving** para comprobar el estado de las opciones de todas las configuraciones de archivado.
    
Para obtener más información acerca de la característica de archivado y capacidades, incluida la integración de Exchange, consulte [Plan para archiving en Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [implementar archiving de Skype para Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)y [Administrar archiving en Skype para 2015 empresariales de servidor](../../manage/archiving/archiving.md).

