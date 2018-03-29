---
title: Directiva de archivado
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
description: 'Utilizar directivas de archivado para habilitar y deshabilitar el archivado para usuarios alojados en Skype para Business Server. En cada directiva de archivado, puede habilitar o deshabilitar el archivado para una de las siguientes opciones (o ambas):'
ms.openlocfilehash: eea3f7eb71bcf3928e2976b9468cea6bf94b4ab1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="archiving-policy"></a>Directiva de archivado
 
Utilizar directivas de archivado para habilitar y deshabilitar el archivado para usuarios alojados en Skype para Business Server. En cada directiva de archivado, puede habilitar o deshabilitar el archivado para una de las siguientes opciones (o ambas):
  
- Comunicaciones internas
    
- Comunicaciones externas (comunicaciones que incluyen al menos un usuario de fuera de su red interna)
    
Las directivas de archivado están formadas por la directiva global y, de forma opcional, por una o varias directivas de archivado de usuario y de sitio:
  
- **Directiva global** La directiva global se crea de forma predeterminada en todas las implementaciones. Puede editarla, pero no eliminarla. Si intenta eliminarla, todas las opciones se restablecerán a los valores predeterminados.
    
- **Directiva de sitio (opcional)** Puede especificar uno o más sitios archivado directivas, que cada una de las cuales se puede configurar para habilitar y deshabilitar el archivado de comunicaciones internas o externas para un único sitio. Una directiva de sitio reemplaza a la directiva global, pero solo para los sitios especificados en las directivas de sitio de archivado. Las directivas de sitio se pueden editar o eliminar.
    
- **Directiva de usuario (opcional)** Puede especificar uno o más archivado directivas de usuario, que cada uno de los cuales se puede configurar para habilitar y deshabilitar el archivado de comunicaciones internas o externas para un usuario específico o grupo de usuarios. Una directiva de usuario reemplaza a las directivas globales y de sitio, pero solo para los usuarios y grupos de usuarios que tengan asignadas directivas de archivado de nivel de usuario. Las directivas de usuario se pueden editar o eliminar.
    
> [!NOTE]
> Políticas de archiving se aplican sólo a los usuarios alojados en Skype para Business Server. Si utiliza la integración de Exchange para almacenar archivar los datos en Microsoft Exchange, a continuación, las directivas de Exchange 2013 control archivado para usuarios alojados en Exchange de 2013. Para habilitar el archivado de los usuarios, el buzón del usuario debe colocarse en posesión en el lugar. 
  
La página **Directiva de archivado** muestra cada directiva de archivado configurada en la implementación. También refleja el nombre de la directiva, el ámbito (global, sitio o usuario) y qué opciones de archivado están habilitadas para cada directiva de archivado. En la página **Directiva de archivado**, dispone de las siguientes opciones:
- **Nuevo** Puede agregar uno o varios de cada una de las siguientes políticas de Archiving opcionales:
    
  - Directiva de sitio
    
  - Directiva de usuario
    
- **Editar** Puede cambiar las opciones de cualquiera de las directivas de archivado que aparecen en la página. Al usar esta opción, puede hacer lo siguiente:
    
  - **Mostrar detalles.** Con esta opción se abre un cuadro de diálogo en el que puede cambiar las opciones de archivado de una directiva de archivado.
    
  - **Seleccionar todo.** Esta opción selecciona todas las directivas de archivado de la lista.
    
  - **Eliminar.** Esta opción elimina todas las directivas de archivado seleccionadas.
    
- **Acción** Puede utilizar esta opción para habilitar o deshabilitar el archivado de comunicaciones internas o externas en cualquier directiva aparecerán en la página, en lugar de modificar la directiva rápidamente. Las opciones disponibles en **Acción** dependen de qué opción esté especificada actualmente en la directiva de archivado. Todas las opciones están disponibles, excepto la opción en vigor actualmente para la directiva de archivado. Las opciones son estas:
    
  - **Habilitar archivado de comunicaciones internas**
    
  - **Deshabilitar archivado de comunicaciones internas**
    
  - **Habilitar archivado de comunicaciones externas**
    
  - **Deshabilitar archivado de comunicaciones externas**
    
- **Actualizar** Puede actualizar la página **Política de Archiving** para comprobar el estado de las opciones de todas las políticas de Archiving.
    
Para obtener más información acerca de la característica de archivado y capacidades, incluida la integración de Exchange, consulte [Plan para archiving en Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [implementar archiving de Skype para Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)y [Administrar archiving en Skype para 2015 empresariales de servidor](../../manage/archiving/archiving.md).

