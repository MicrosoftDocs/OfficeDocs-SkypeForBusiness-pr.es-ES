---
title: Directiva de archivado
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
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
description: 'Las directivas de archivado se usan para habilitar y deshabilitar el archivado para los usuarios que están en Skype Empresarial Server. En cada directiva de archivado, puede habilitar o deshabilitar el archivado para una de las siguientes opciones o ambas:'
ms.openlocfilehash: 19bc0612208e719b7a963bf4c7f0dc6a9cc69537
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826950"
---
# <a name="archiving-policy"></a>Directiva de archivado
 
Las directivas de archivado se usan para habilitar y deshabilitar el archivado para los usuarios que están en Skype Empresarial Server. En cada directiva de archivado, puede habilitar o deshabilitar el archivado para una de las siguientes opciones o ambas:
  
- Comunicaciones internas
    
- Comunicaciones externas (comunicaciones que incluyen al menos un usuario de fuera de su red interna)
    
Las directivas de archivado incluyen la directiva global y, de forma opcional, una o varias directivas de archivado de usuario y de sitio:
  
- **Directiva global** La directiva global se crea de forma predeterminada en todas las implementaciones. Puede editar la directiva global, pero no puede eliminar esta directiva. Si intenta eliminarla, todas las opciones se restablecerán a los valores predeterminados.
    
- **Directiva de sitio (opcional)** Puede especificar una o más directivas de archivado de sitios, cada una de las cuales puede configurar para habilitar y deshabilitar el archivado de comunicaciones internas o externas para un único sitio. Una directiva de sitio anula la directiva global, pero solo para los sitios especificados en sus directivas de sitios de archivado. Puede editar o eliminar las directivas de sitios.
    
- **Directiva de usuario (opcional)** Puede especificar una o más directivas de archivado de usuarios, cada una de las cuales puede configurar para habilitar y deshabilitar el archivado de comunicaciones internas o externas para un usuario o grupo de usuarios específicos. Una directiva de usuarios anula las directivas global y de sitio, pero solo para los usuarios y grupos de usuarios a los que asigne las directivas de archivado de nivel de usuario. Puede editar o eliminar las directivas de usuarios.
    
> [!NOTE]
> Las directivas de archivado solo se aplican a los usuarios que están en Skype Empresarial Server. Si usa la integración de Exchange para almacenar datos de archivado en Microsoft Exchange, las directivas de Exchange 2013 controlan el archivado para los usuarios que están en Exchange 2013. Para habilitar el archivado para esos usuarios, el buzón del usuario debe colocarse en In-Place retención. 
  
La página **Directiva de archivado** muestra cada directiva de archivado configurada para su implementación. También muestra el nombre de la directiva, el ámbito (global, sitio o usuario) y qué opciones de archivado están habilitadas para cada directiva de archivado. En la página **Directiva de archivado**, tiene las siguientes opciones:
- **Nuevo** Puede agregar una o varias de las siguientes directivas de archivado opcionales:
    
  - Directiva de sitio
    
  - Directiva de usuario
    
- **Editar** Puede cambiar las opciones de cualquiera de las directivas de archivado que aparecen en la página. Al usar esta opción, puede hacer lo siguiente:
    
  - **Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones de archivado de una directiva de archivado.
    
  - **Seleccionar todo** Esta opción selecciona todas las directivas de archivado de la lista.
    
  - **Eliminar** Esta opción elimina todas las directivas de archivado seleccionadas.
    
- **Acción** Puede usar esta opción para habilitar o deshabilitar rápidamente el archivado de comunicaciones internas o externas en cualquier directiva que aparezca en la página, en lugar de editar la directiva. Las opciones disponibles en **Acción** dependen de qué opción esté especificada actualmente en la directiva de archivado. Todas las opciones están disponibles, excepto la opción en efecto actualmente para la directiva de archivado. Las opciones incluyen lo siguiente:
    
  - **Habilitar archivado de comunicaciones internas**
    
  - **Deshabilitar archivado de comunicaciones internas**
    
  - **Habilitar archivado de comunicaciones externas**
    
  - **Deshabilitar archivado de comunicaciones externas**
    
- **Actualizar** Puede actualizar la página **Directiva de** archivado para comprobar el estado de las opciones de todas las directivas de archivado.
    
Para obtener más información sobre la característica y las capacidades de archivado, incluida la integración de Exchange, vea [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), Deploy archiving for Skype for Business Server [2015](../../deploy/deploy-archiving/deploy-archiving.md)y [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).

