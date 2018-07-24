---
title: Directiva de archivado crear nuevos o editar los existentes
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
ROBOTS: NOINDEX, NOFOLLOW
description: 'Use las directivas de archivado para controlar el archivado de comunicaciones internas y externas en su implementación para los usuarios que están hospedados en Skype para Business Server. Las directivas de archivado incluyen la directiva global y, de forma opcional, una o varias directivas de usuario y de sitio:'
ms.openlocfilehash: 9bb8057cd7d3d6b82e55a6045713f0183b3d3b01
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21000800"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a>Directiva de archivado: Crear nueva o editar existente
 
Use las directivas de archivado para controlar el archivado de comunicaciones internas y externas en su implementación para los usuarios que están hospedados en Skype para Business Server. Las directivas de archivado incluyen la directiva global y, de forma opcional, una o varias directivas de usuario y de sitio:
  
- **Directiva global** La directiva global se crea de forma predeterminada en todos los Skype para las implementaciones de servidores empresariales. Puede editarla, pero no eliminarla. Si intenta eliminarla, todas las opciones se restablecerán a los valores predeterminados.
    
- **Directivas de sitio (opcionales)** Puede especificar uno o varios sitios las directivas de archivado, que cada uno de los cuales se pueden configurar para habilitar y deshabilitar el archivado de comunicaciones internas o externas para un sitio específico. Una directiva de sitio reemplaza a la directiva global, pero solo para los sitios especificados en las directivas de sitios de archivado. Las directivas de sitio se pueden editar o eliminar.
    
- **Directivas de usuario (opcionales)** Puede especificar uno o varios usuarios directivas de archivado, que cada uno de los cuales se pueden configurar para habilitar y deshabilitar el archivado de comunicaciones internas o externas para un usuario específico. Una directiva de usuario reemplaza a las directivas globales y de sitio, pero solo para los usuarios a los que asigne una directiva de usuario. Las directivas de usuario se pueden editar o eliminar.
    
> [!NOTE]
> Si utiliza la integración de Exchange para almacenar datos de archivado en Microsoft Exchange, a continuación, Exchange archivado de control de las directivas para los usuarios alojados en Exchange. Para habilitar el archivado para aquellos usuarios, se debe colocar el buzón del usuario en suspensión en contexto. 
  
Especifique las siguientes opciones para configurar los ajustes de una nueva directiva de archivado o una existente:
- **Nombre** Cada directiva de archivado requiere un nombre. El nombre se determina por el tipo de directiva que está agregando o editando:
    
  - **Directiva global** El nombre predeterminado es Global. Se puede cambiar a un nombre más descriptivo. Por ejemplo, Contoso norteamericanos organización.
    
  - **Directiva de sitio** Los sitios enumerados en este cuadro de diálogo incluyen todos los sitios disponibles en su implementación. Haga clic en un único sitio para seleccionarlo. Por ejemplo, centro de datos de Redmond.
    
  - **Directiva de usuario** Especifique un nombre adecuado, como el nombre de un usuario específico o el nombre de un grupo de usuarios o un equipo de la organización. Por ejemplo, Departamento Legal.
    
- **Descripción** Esto es opcional. Usar para proporcionar información adicional, como el ámbito o el uso de la directiva. Por ejemplo, coordinarse con los departamentos Legal de otros sitios.
    
- **Archivar las comunicaciones internas** Seleccione esta casilla para habilitar el archivado de comunicaciones en la red interna. Esta opción no está habilitada de forma predeterminada en ninguna directiva.
    
- **Archivar comunicaciones externas** Seleccione esta casilla para habilitar el archivado de comunicaciones que incluyan los usuarios externos, como los usuarios remotos, (incluidos los usuarios anónimos y configuración de mensajería instantánea pública) y los socios federados. Esta opción no está habilitada de forma predeterminada en ninguna directiva.
    
Para obtener información detallada acerca de la característica de archivado y capacidades, que incluye la integración de Exchange, consulte [Plan para el archivado en Skype para Business Server](../../../plan-your-deployment/archiving/archiving.md), [implementar el archivado de Skype para Business Server](../../../deploy/deploy-archiving/deploy-archiving.md)y [administrar el archivado en Skype para la empresa Servidor](../../../manage/archiving/archiving.md).

