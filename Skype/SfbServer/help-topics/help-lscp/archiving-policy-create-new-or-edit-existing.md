---
title: Directiva de archivado Crear nueva o editar existente
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
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
description: 'Las directivas de archivado se usan para controlar el archivado de comunicaciones internas y externas en la implementación para los usuarios que están en Skype Empresarial Server. Las directivas de archivado incluyen la directiva global y, opcionalmente, una o más directivas de sitio y usuario:'
ms.openlocfilehash: 9c852c592776f9e529c11dd46272715af52e8111
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826970"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a>Directiva de archivado: Crear nuevos o editar los existente
 
Las directivas de archivado se usan para controlar el archivado de comunicaciones internas y externas en la implementación para los usuarios que están en Skype Empresarial Server. Las directivas de archivado incluyen la directiva global y, opcionalmente, una o más directivas de sitio y usuario:
  
- **Directiva global** La directiva global se crea de forma predeterminada en todas las implementaciones de Skype Empresarial Server. Puede editar la directiva global, pero no puede eliminar esta directiva. Si intenta eliminarla, todas las opciones se restablecerán a los valores predeterminados.
    
- **Directivas de sitio (opcional)** Puede especificar una o más directivas de archivado de sitios, cada una de las cuales puede configurar para habilitar y deshabilitar el archivado de comunicaciones internas o externas para un sitio específico. Una directiva de sitio invalida la directiva global, pero solo para los sitios especificados en las directivas de archivado. Puede editar o eliminar las directivas de sitios.
    
- **Directivas de usuario (opcional)** Puede especificar una o más directivas de archivado de usuario, cada una de las cuales puede configurar para habilitar y deshabilitar el archivado para las comunicaciones internas o externas de un usuario específico. Una directiva de usuario reemplaza la directiva global y las directivas de sitio, pero solo para los usuarios a los que asigna una directiva de usuario. Puede editar o eliminar las directivas de usuarios.
    
> [!NOTE]
> Si usa la integración de Exchange para almacenar datos de archivado en Microsoft Exchange, las directivas de Exchange 2013 controlan el archivado para los usuarios que están en Exchange 2013. Para habilitar el archivado para esos usuarios, el buzón del usuario debe colocarse en In-Place retención. 
  
Para configurar las opciones de una directiva de archivado nueva o existente, especifique las siguientes opciones:
- **Nombre** Cada directiva de archivado requiere un nombre. El nombre viene determinado por el tipo de directiva que está agregando o editando:
    
  - **Directiva global** El nombre predeterminado es Global. Puede cambiarlo a un nombre más descriptivo. Por ejemplo, Organización Contoso de los Estados Unidos.
    
  - **Directiva de sitio** Los sitios enumerados en este cuadro de diálogo incluyen todos los sitios disponibles en la implementación. Haga clic en un solo sitio para seleccionarlo. Por ejemplo, Centro de datos de Redmond.
    
  - **Directiva de usuario** Especifique un nombre adecuado, como el nombre de un usuario específico o el nombre de un grupo de usuarios o equipo de su organización. Por ejemplo, Departamento legal.
    
- **Descripción** Esto es opcional. Úselo para proporcionar detalles adicionales, como el ámbito o el uso de la directiva. Por ejemplo, Coordinación con departamentos legales de otros sitios.
    
- **Archivar comunicaciones internas** Active esta casilla para habilitar el archivado de comunicaciones en la red interna. De forma predeterminada, esto no está habilitado en ninguna directiva.
    
- **Archivar comunicaciones externas** Active esta casilla para habilitar el archivado de comunicaciones que incluyan usuarios externos, como usuarios remotos (incluidos usuarios anónimos y de configuración PIC) y socios federados. De forma predeterminada, esto no está habilitado en ninguna directiva.
    
Para obtener más información sobre la característica y las capacidades de archivado, incluida la integración de Exchange, vea [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), Deploy archiving for Skype for Business Server [2015](../../deploy/deploy-archiving/deploy-archiving.md)y [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).

