---
title: Habilitar o deshabilitar el envío de una renuncia de archivado a socios federados
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 859b4e295a90fd44ce69efe4af7daa63ddc8812c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197866"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>Habilitar o deshabilitar el envío de una renuncia de archivado a los socios federados en Skype para Business Server

En el momento en que implementan los servidores perimetrales y habilitado la federación para su organización, debe ha especificado si se envían automáticamente la renuncia de archivado a los socios federados. Si archiva las comunicaciones externas, debe habilitar el envío de una renuncia de archivado. Use el procedimiento de este tema para cambiar dicha configuración.

> [!NOTE]
> El siguiente procedimiento se supone que ya ha habilitado la federación para su organización. Para obtener información detallada acerca de cómo habilitar la federación, vea [Habilitar o deshabilitar el acceso de usuarios remotos](enable-or-disable-remote-user-access.md).


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>Para habilitar o deshabilitar el envío de una renuncia de archivado a los socios federados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Acceso de usuarios externos**, haga clic en **Configuración perimetral de acceso**.

4.  En la ficha **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y, luego, en **Mostrar detalles**.

5.  En **Editar configuración perimetral de acceso**, en **Habilitar las comunicaciones con los usuarios federados**, active o desactive la casilla de verificación **Enviar declinación de responsabilidades a los socios federados de archivado** para habilitar o deshabilitar el envío automáticamente el archivado declinación de responsabilidades.

6.  Haga clic en **Confirmar**.

Para habilitar los usuarios federados puedan colaborar con los usuarios de su Skype para la implementación de Business Server, debe haber configurado también al menos una directiva de acceso externo para admitir el acceso de usuarios federados. Para obtener información detallada acerca de cómo controlar el acceso de dominios federados concretos, vea [Configurar compatibilidad para dominios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Habilitar o deshabilitar la renuncia de archivado mediante el uso de cmdlets de Windows PowerShell

El uso de la renuncia de archivado se puede administrar mediante el uso de Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration. Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. 

## <a name="to-enable-the-archiving-disclaimer"></a>Para habilitar la renuncia de archivado

  - Para habilitar la declinación de responsabilidades de archivado, establezca el valor de la propiedad **EnableArchivingDisclaimer** en True ($True):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>Para deshabilitar la renuncia de archivado

  - Para deshabilitar la declinación de responsabilidades de archivado, establezca el valor de la propiedad **EnableArchivingDisclaimer** en False ($False):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


