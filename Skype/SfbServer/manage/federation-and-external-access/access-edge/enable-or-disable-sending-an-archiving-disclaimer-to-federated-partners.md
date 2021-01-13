---
title: Habilitar o deshabilitar el envío de una renuncia de archivado a socios federados
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 1f0238e177e74dc1263208f9a6a350158825d825
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817360"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>Habilitar o deshabilitar el envío de un aviso de declinación de responsabilidades de archivado a socios federados en Skype Empresarial Server

En el momento en que implementa los servidores perimetrales y habilita la federación para la organización, debe especificar si desea enviar de forma automática la notificación de renuncia de archivado a los socios federados. Si archiva las comunicaciones externas, debe habilitar el envío de notificaciones de renuncia de archivado. Para cambiar esa configuración, siga el procedimiento de este tema.

> [!NOTE]
> En el procedimiento siguiente, se presupone que ya ha habilitado la federación para la organización. Para obtener más información sobre cómo habilitar la federación, vea [Habilitar o deshabilitar el acceso de usuarios remotos.](enable-or-disable-remote-user-access.md)


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>Para habilitar o deshabilitar el envío de una renuncia de archivado a socios federados:

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 

3.  En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y en **Configuración perimetral de acceso**.

4.  En la pestaña **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y en **Mostrar detalles**.

5.  En **Editar configuración perimetral de acceso**, vaya a **Habilitar comunicaciones con usuarios federados** y active o desactive la casilla **Enviar notificación de renuncia de archivado a los socios federados** para habilitar o deshabilitar el envío automático de notificaciones de renuncia de archivado.

6.  Haga clic en **Confirmar**.

Para permitir que los usuarios federados colaboren con usuarios en su implementación de Skype Empresarial Server, también debe haber configurado al menos una directiva de acceso externo para admitir el acceso de usuarios federados. Para obtener más información sobre cómo controlar el acceso a dominios federados específicos, consulte Configurar la [compatibilidad con dominios externos permitidos.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Habilitar o deshabilitar el aviso de declinación de responsabilidades de archivado mediante Windows PowerShell cmdlets

El uso del aviso de declinación de responsabilidades de archivado se puede administrar mediante Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration archivado. Este cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell. 

## <a name="to-enable-the-archiving-disclaimer"></a>Para habilitar el aviso de declinación de responsabilidades de archivado

  - Para habilitar la renuncia de archivado, establezca la propiedad **EnableArchivingDisclaimer** en True ($True):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>Para deshabilitar el aviso de declinación de responsabilidades de archivado

  - Para deshabilitar la renuncia de archivado, establezca la propiedad **EnableArchivingDisclaimer** en False ($False):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


