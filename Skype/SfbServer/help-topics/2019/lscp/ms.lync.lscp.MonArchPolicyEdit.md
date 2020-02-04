---
title: Directiva de archivado crear nuevo o editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
ROBOTS: NOINDEX, NOFOLLOW
description: 'Use las directivas de archivado para controlar el archivado de las comunicaciones internas y externas de la implementación para los usuarios alojados en Skype empresarial Server. Las directivas de archivado incluyen la directiva global y, de forma opcional, una o varias directivas de usuario y de sitio:'
ms.openlocfilehash: 1eb1f0060e80fbb7d325f5fbe1b7a247d6d006b6
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691225"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a>Directiva de archivado: Crear nueva o editar existente
 
Use las directivas de archivado para controlar el archivado de las comunicaciones internas y externas de la implementación para los usuarios alojados en Skype empresarial Server. Las directivas de archivado incluyen la directiva global y, de forma opcional, una o varias directivas de usuario y de sitio:
  
- **Directiva global** La directiva global se crea de forma predeterminada en todas las implementaciones de Skype empresarial Server. Puede editarla, pero no eliminarla. Si intenta eliminarla, todas las opciones se restablecerán a los valores predeterminados.
    
- **Directivas de sitio (opcional)** Puede especificar una o más directivas de archivado de sitio, cada una de las cuales puede configurar para habilitar y deshabilitar el archivado de comunicaciones internas o externas para un sitio específico. Una directiva de sitio reemplaza a la directiva global, pero solo para los sitios especificados en las directivas de sitios de archivado. Las directivas de sitio se pueden editar o eliminar.
    
- **Directivas de usuario (opcional)** Puede especificar una o más directivas de archivado de usuario, cada una de las cuales puede configurar para habilitar y deshabilitar el archivado de las comunicaciones internas o externas para un usuario específico. Una directiva de usuario reemplaza a las directivas globales y de sitio, pero solo para los usuarios a los que asigne una directiva de usuario. Las directivas de usuario se pueden editar o eliminar.
    
> [!NOTE]
> Si usa la integración de Exchange para almacenar los datos de archivado en Microsoft Exchange, las directivas de Exchange controlan el archivado para los usuarios alojados en Exchange. Para habilitar el archivado de los usuarios, el buzón del usuario debe estar en conservación local. 
  
Especifique las siguientes opciones para configurar los ajustes de una nueva directiva de archivado o una existente:
- **Nombre** Cada directiva de archivado requiere un nombre. El nombre se determina por el tipo de directiva que está agregando o editando:
    
  - **Directiva global** El nombre predeterminado es global. Puedes cambiarlo a un nombre más descriptivo. Por ejemplo, organización de la Norteamérica de contoso.
    
  - **Directiva de sitio** Los sitios que aparecen en este cuadro de diálogo incluyen todos los sitios disponibles en la implementación. Haga clic en un solo sitio para seleccionarlo. Por ejemplo, centro de datos de Redmond.
    
  - **Directiva de usuario** Especifique un nombre apropiado, como el nombre de un usuario específico o el nombre de un grupo de usuarios o de un equipo de su organización. Por ejemplo, departamento legal.
    
- **Descripción** Esto es opcional. Utilícelo para proporcionar detalles adicionales, como el ámbito o el uso de la Directiva. Por ejemplo, coordine con departamentos jurídicos de otros sitios.
    
- **Archivar comunicaciones internas** Seleccione esta casilla para habilitar el archivado de comunicaciones en la red interna. Esta opción no está habilitada de forma predeterminada en ninguna directiva.
    
- **Archivar comunicaciones externas** Seleccione esta casilla para habilitar el archivado de comunicaciones que incluyen usuarios externos, como usuarios remotos (incluidos los usuarios de configuración anónima y PIC) y socios federados. Esta opción no está habilitada de forma predeterminada en ninguna directiva.
    
Para obtener información sobre la característica y capacidades de archivado, incluyendo la integración de Exchange, consulte [planear el archivado en Skype empresarial Server](../../../plan-your-deployment/archiving/archiving.md), [implementar el archivado para Skype empresarial Server](../../../deploy/deploy-archiving/deploy-archiving.md)y [administrar el archivado en Skype empresarial Server](../../../manage/archiving/archiving.md).

