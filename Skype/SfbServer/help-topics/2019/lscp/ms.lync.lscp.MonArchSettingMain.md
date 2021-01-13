---
title: Configuración de archivado
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
ROBOTS: NOINDEX, NOFOLLOW
description: 'Las configuraciones de archivado se usan para controlar las opciones de archivado para la implementación de Skype Empresarial Server, incluida la habilitación y deshabilitación de las siguientes opciones:'
ms.openlocfilehash: 56ab256d79a22ce8b08efc9ad135d4c8309ff5d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833600"
---
# <a name="archiving-configuration"></a>Configuración de archivado
 
Las configuraciones de archivado se usan para controlar las opciones de archivado para la implementación de Skype Empresarial Server, incluida la habilitación y deshabilitación de las siguientes opciones:
  
- Bloquear sesiones de mensajería instantánea o conferencias si no se pueden archivar
    
- Integración con el almacenamiento de Exchange para los usuarios que están en Exchange
    
- Purgar datos archivados
    
Las configuraciones de archivado incluyen la configuración global y, de forma opcional, una o varias configuraciones de archivado de sitio y grupo:
  
- **Configuración global** La configuración global se crea de forma predeterminada en todas las implementaciones de Skype Empresarial Server. Puede editar la configuración global, pero no puede eliminar esta configuración de archivado. Si intenta eliminarla, todas las opciones se restablecerán a los valores predeterminados.
    
- **Configuración del sitio (opcional)** Puede especificar una o varias configuraciones de archivado de sitios, cada una de las cuales puede configurar para controlar las opciones de archivado de un sitio específico. Una configuración de sitio anula la configuración global, pero solo para los sitios especificados en las configuraciones de sitios de archivado. Puede editar o eliminar las configuraciones de sitios.
    
- **Configuración del grupo de servidores (opcional)** Puede especificar una o más configuraciones de archivado de grupo para controlar las opciones de archivado de un grupo específico. Una configuración de grupo anula la configuración global y la configuración del sitio, pero solo para los grupos especificados en las configuraciones de grupos de archivado. Puede editar o eliminar las configuraciones de grupos.
    
> [!NOTE]
> Las configuraciones de archivado se aplican a los usuarios que están en Skype Empresarial Server y, si usa Exchange para almacenar datos de archivado en Microsoft Exchange, a los usuarios que están en Exchange, pero se implementan de forma ligeramente diferente para los usuarios de Exchange. Las diferencias se describen en la siguiente sección. 
  
La página **Configuración de archivado** muestra cada directiva de archivado configurada para su implementación. También muestra el nombre de la directiva, el ámbito (global, sitio o usuario) y qué opciones de archivado están habilitadas para cada configuración de archivado. En la página **Configuración de archivado**, tiene las siguientes opciones:
- **Nuevo** Puede agregar una o varias de las siguientes configuraciones de archivado opcionales.
    
  - Configuración de sitio
    
  - Configuración del grupo de servidores
    
- **Editar** Puede cambiar las opciones de cualquiera de las configuraciones de archivado que aparecen en la página. Al usar esta opción, puede hacer lo siguiente:
    
  - **Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones de archivado para la configuración de archivado seleccionada. Solo puede mostrar detalles para una configuración de archivado cada vez.
    
  - **Seleccionar todo** Esta opción selecciona todas las configuraciones de archivado de la lista.
    
  - **Eliminar** Esta opción elimina todas las configuraciones de archivado seleccionadas.
    
- **Acción** Puede usar esta opción para habilitar o deshabilitar rápidamente el archivado de sesiones de mensajería instantánea o sesiones de conferencia web en cualquier configuración que aparezca en la página, en lugar de editar la configuración. Las opciones disponibles en **Acción** dependen de qué opción esté especificada actualmente en la configuración de archivado. Todas las opciones están disponibles, excepto la opción en efecto actualmente para la configuración de archivado. Las opciones incluyen lo siguiente:
    
  - **Archivar sesiones de mensajería instantánea**
    
  - **Archivar sesiones de mensajería instantánea y conferencias web**
    
  - **Deshabilitar archivado**
    
- **Actualizar** Puede actualizar la página **Configuración de** archivado para comprobar el estado de las opciones de todas las configuraciones de archivado.
    
Para obtener más información sobre la característica y las capacidades de archivado, incluida la integración de Exchange, vea [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), Deploy archiving for Skype for Business [Server](../../../deploy/deploy-archiving/deploy-archiving.md)y Manage archiving in Skype for [Business Server](../../../manage/archiving/archiving.md).

