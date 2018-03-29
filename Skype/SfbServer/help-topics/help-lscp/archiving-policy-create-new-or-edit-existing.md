---
title: Política de archiving cree nuevos o edite los existentes
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
description: 'Utilice directivas de archivado para controlar el archivado de comunicaciones internas y externas en la implementación para los usuarios que están alojados en Skype para Business Server. Las directivas de archivado incluyen la directiva global y, de forma opcional, una o varias directivas de usuario y de sitio:'
ms.openlocfilehash: af8038371cd421b0232ce2df0ba92aa5b079702e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="archiving-policy-create-new-or-edit-existing"></a>Directiva de archivado: Crear nueva o editar existente
 
Utilice directivas de archivado para controlar el archivado de comunicaciones internas y externas en la implementación para los usuarios que están alojados en Skype para Business Server. Las directivas de archivado incluyen la directiva global y, de forma opcional, una o varias directivas de usuario y de sitio:
  
- **Directiva global** La directiva global se crea de forma predeterminada en todos los Skype para implementaciones de servidores empresariales. Puede editarla, pero no eliminarla. Si intenta eliminarla, todas las opciones se restablecerán a los valores predeterminados.
    
- **Políticas del sitio (opcionales)** Puede especificar uno o más sitios archivado directivas, que cada una de las cuales se puede configurar para habilitar y deshabilitar el archivado de comunicaciones internas o externas para un sitio específico. Una directiva de sitio reemplaza a la directiva global, pero solo para los sitios especificados en las directivas de sitios de archivado. Las directivas de sitio se pueden editar o eliminar.
    
- **Directivas de usuario (opcionales)** Puede especificar uno o más archivado directivas de usuario, que cada uno de los cuales se puede configurar para habilitar y deshabilitar el archivado de comunicaciones internas o externas para un usuario específico. Una directiva de usuario reemplaza a las directivas globales y de sitio, pero solo para los usuarios a los que asigne una directiva de usuario. Las directivas de usuario se pueden editar o eliminar.
    
> [!NOTE]
> Si utiliza la integración de Exchange para almacenar archivar los datos en Microsoft Exchange, a continuación, las directivas de Exchange 2013 control archivado para usuarios alojados en Exchange de 2013. Para habilitar el archivado de los usuarios, el buzón del usuario debe colocarse en posesión en el lugar. 
  
Especifique las siguientes opciones para configurar los ajustes de una nueva directiva de archivado o una existente:
- **Nombre** Cada directiva de archivado requiere un nombre. El nombre se determina por el tipo de directiva que está agregando o editando:
    
  - **Directiva global** El nombre predeterminado es Global. Puede cambiarlo a un nombre más descriptivo. Por ejemplo, Contoso North American organización.
    
  - **Directiva de sitio** Los sitios que aparecen en este cuadro de diálogo incluyen todos los sitios disponibles en la implementación. Haga clic en un solo sitio para seleccionarlo. Por ejemplo, el centro de datos de Redmond.
    
  - **Directiva de usuario** Especifique un nombre apropiado, como el nombre de un usuario específico o el nombre de un grupo de usuarios o un equipo de la organización. Por ejemplo, Departamento Legal.
    
- **Descripción** Esto es opcional. Utilizarlo para proporcionar detalles adicionales, como el ámbito o el uso de la directiva. Por ejemplo, coordinar con los departamentos legales de otros sitios.
    
- **Archivar las comunicaciones internas** Active esta casilla de verificación para habilitar el archivado de comunicaciones en la red interna. Esta opción no está habilitada de forma predeterminada en ninguna directiva.
    
- **Archivar las comunicaciones externas** Active esta casilla de verificación para habilitar el archivado de comunicaciones que incluyen los usuarios externos, como los usuarios remotos, (incluidos los usuarios anónimos y configuración de PIC) y los socios federados. Esta opción no está habilitada de forma predeterminada en ninguna directiva.
    
Para obtener más información acerca de la característica de archivado y capacidades, incluida la integración de Exchange, consulte [Plan para archiving en Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [implementar archiving de Skype para Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)y [Administrar archiving en Skype para 2015 empresariales de servidor](../../manage/archiving/archiving.md).

