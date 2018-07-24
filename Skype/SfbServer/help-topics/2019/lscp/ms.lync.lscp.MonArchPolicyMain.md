---
title: Directiva de archivado
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
ROBOTS: NOINDEX, NOFOLLOW
description: 'Use las directivas de archivado para habilitar y deshabilitar el archivado para los usuarios alojados en Skype para Business Server. En cada directiva de archivado, puede habilitar o deshabilitar el archivado para una de las siguientes opciones (o ambas):'
ms.openlocfilehash: d673aa5474864d99895efc1e16e1e307f078c72f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20973824"
---
# <a name="archiving-policy"></a>Directiva de archivado
 
Use las directivas de archivado para habilitar y deshabilitar el archivado para los usuarios alojados en Skype para Business Server. En cada directiva de archivado, puede habilitar o deshabilitar el archivado para una de las siguientes opciones (o ambas):
  
- Comunicaciones internas
    
- Comunicaciones externas (comunicaciones que incluyen al menos un usuario de fuera de su red interna)
    
Las directivas de archivado están formadas por la directiva global y, de forma opcional, por una o varias directivas de archivado de usuario y de sitio:
  
- **Directiva global** La directiva global se crea de forma predeterminada en todas las implementaciones. Puede editarla, pero no eliminarla. Si intenta eliminarla, todas las opciones se restablecerán a los valores predeterminados.
    
- **Directiva de sitio (opcional)** Puede especificar uno o varios sitios las directivas de archivado, que cada uno de los cuales se pueden configurar para habilitar y deshabilitar el archivado de comunicaciones internas o externas de un solo sitio. Una directiva de sitio reemplaza a la directiva global, pero solo para los sitios especificados en las directivas de sitio de archivado. Las directivas de sitio se pueden editar o eliminar.
    
- **Directiva de usuario (opcional)** Puede especificar uno o varios usuarios directivas de archivado, que cada uno de los cuales se pueden configurar para habilitar y deshabilitar el archivado de comunicaciones internas o externas para un usuario específico o grupo de usuarios. Una directiva de usuario reemplaza a las directivas globales y de sitio, pero solo para los usuarios y grupos de usuarios que tengan asignadas directivas de archivado de nivel de usuario. Las directivas de usuario se pueden editar o eliminar.
    
> [!NOTE]
> Las directivas de archivado se aplican sólo a los usuarios hospedados en Skype para Business Server. Si utiliza la integración de Exchange para almacenar datos de archivado en Microsoft Exchange, a continuación, Exchange archivado de control de las directivas para los usuarios alojados en Exchange. Para habilitar el archivado para aquellos usuarios, se debe colocar el buzón del usuario en suspensión en contexto. 
  
La página **Directiva de archivado** muestra cada directiva de archivado configurada en la implementación. También refleja el nombre de la directiva, el ámbito (global, sitio o usuario) y qué opciones de archivado están habilitadas para cada directiva de archivado. En la página **Directiva de archivado**, dispone de las siguientes opciones:
- **Nuevo** Puede agregar uno o varios de cada una de las directivas de archivado opcionales siguientes:
    
  - Directiva de sitio
    
  - Directiva de usuario
    
- **Editar** Puede cambiar las opciones de cualquiera de las directivas de archivado que aparecen en la página. Al usar esta opción, puede hacer lo siguiente:
    
  - **Mostrar detalles.** Con esta opción se abre un cuadro de diálogo en el que puede cambiar las opciones de archivado de una directiva de archivado.
    
  - **Seleccionar todo.** Esta opción selecciona todas las directivas de archivado de la lista.
    
  - **Eliminar.** Esta opción elimina todas las directivas de archivado seleccionadas.
    
- **Acción** Puede usar esta opción para habilitar o deshabilitar el archivado de comunicaciones internas o externas en cualquier directiva que aparece en la página, en lugar de modificar la directiva de rápidamente. Las opciones disponibles en **Acción** dependen de qué opción esté especificada actualmente en la directiva de archivado. Todas las opciones están disponibles, excepto la opción en vigor actualmente para la directiva de archivado. Las opciones son estas:
    
  - **Habilitar archivado de comunicaciones internas**
    
  - **Deshabilitar archivado de comunicaciones internas**
    
  - **Habilitar archivado de comunicaciones externas**
    
  - **Deshabilitar archivado de comunicaciones externas**
    
- **Actualizar** Puede actualizar la página **Directiva de archivado** para comprobar el estado de las opciones de todas las directivas de archivado.
    
Para obtener información detallada acerca de la característica de archivado y capacidades, que incluye la integración de Exchange, consulte [Plan para el archivado en Skype para Business Server](../../../plan-your-deployment/archiving/archiving.md), [implementar el archivado de Skype para Business Server](../../../deploy/deploy-archiving/deploy-archiving.md)y [administrar el archivado en Skype para la empresa Servidor](../../../manage/archiving/archiving.md).

