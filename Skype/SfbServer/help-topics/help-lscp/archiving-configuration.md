---
title: Configuración de archivado
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: 'Las configuraciones de archivado se usan para controlar las opciones de archivado de la implementación de Skype empresarial Server, incluida la activación y desactivación de las siguientes opciones:'
ms.openlocfilehash: 8f3ed4289d68359cb8eb0d4cb0bfc3a303c53dd3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299851"
---
# <a name="archiving-configuration"></a>Configuración de archivado
 
Las configuraciones de archivado se usan para controlar las opciones de archivado de la implementación de Skype empresarial Server, incluida la activación y desactivación de las siguientes opciones:
  
- Bloquear sesiones de mensajería instantánea o conferencias si no se pueden archivar
    
- Integración con el almacenamiento de Exchange 2013, para usuarios alojados en Exchange 2013
    
- Purgar datos archivados
    
Las configuraciones de archivado están formadas por la configuración global y, de forma opcional, por una o varias configuraciones de archivado de sitio y grupo:
  
- **Configuración global** La configuración global se crea de forma predeterminada en todas las implementaciones de Skype empresarial Server. La configuración global se puede editar, pero no eliminar. Si intenta eliminarla, todas las opciones se restablecerán a los valores predeterminados.
    
- **Configuración del sitio (opcional)** Puede especificar una o más configuraciones de archivado de sitio, cada una de las cuales puede configurar para controlar las opciones de archivado de un sitio específico. Una configuración de sitio reemplaza a la configuración global, pero solo en los sitios especificados en las configuraciones de sitio de archivado. Las configuraciones de sitio se pueden editar o eliminar.
    
- **Configuración del grupo (opcional)** Puede especificar una o más configuraciones de archivado de grupo para controlar las opciones de archivado de un grupo específico. Una configuración de grupo reemplaza a la configuración global y la configuración del sitio, pero solo en los grupos especificados en las configuraciones de grupo de archivado. Las configuraciones de grupo se pueden editar o eliminar.
    
> [!NOTE]
> Las configuraciones de archivado se aplican a los usuarios alojados en Skype empresarial Server y, si usa Exchange para almacenar los datos de archivado en Microsoft Exchange, para los usuarios alojados en Exchange 2013, pero se implementan de un modo ligeramente diferente para los usuarios alojados en Exchange 2013. En la siguiente sección se describen estas diferencias. 
  
La página **Configuración de archivado** muestra cada directiva de archivado configurada en la implementación. También muestra el nombre de la directiva, el ámbito (global, sitio o usuario) y qué opciones de archivado están habilitadas para cada configuración de archivado. En la página **Configuración de archivado** dispone de las siguientes opciones:
- **Nuevo** Puede Agregar una o más de las siguientes configuraciones de archivo opcionales.
    
  - Configuración de sitio
    
  - Configuración del grupo de servidores
    
- **Editar** Puede cambiar las opciones de cualquiera de las configuraciones de archivado que aparecen en la página. Al usar esta opción, puede hacer lo siguiente:
    
  - **Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones de archivado para la configuración de archivado seleccionada. Solo puede mostrar detalles para una configuración de archivado cada vez.
    
  - **Seleccionar todo** Esta opción selecciona todas las configuraciones de archivado de la lista.
    
  - **Eliminar** Esta opción elimina todas las configuraciones de archivado seleccionadas.
    
- **Acción** Puede usar esta opción para habilitar o deshabilitar rápidamente el archivado de sesiones de mensajería instantánea o de conferencias web en cualquier configuración que aparezca en la página, en lugar de editar la configuración. Las opciones disponibles en **Acción** dependen de qué opción esté especificada actualmente en la configuración de archivado. Todas las opciones están disponibles, excepto la opción en vigor actualmente para la configuración de archivado. Las opciones son estas:
    
  - **Archivar sesiones de mensajería instantánea**
    
  - **Archivar sesiones de mensajería instantánea y conferencias web**
    
  - **Deshabilitar archivado**
    
- **Actualizar** Puede actualizar la página **configuración** de archivado para comprobar el estado de las opciones de todas las configuraciones de archivado.
    
Para obtener más información sobre las funciones y características de archivado, como la integración de Exchange, consulte [planear el archivado en Skype empresarial server 2015](../../plan-your-deployment/archiving/archiving.md), [implementar el archivado para Skype empresarial Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)y [administrar el archivado en Skype para Business Server 2015](../../manage/archiving/archiving.md).

