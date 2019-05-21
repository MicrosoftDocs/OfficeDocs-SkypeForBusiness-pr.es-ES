---
title: Habilitar o deshabilitar el envío de una renuncia de archivado a socios federados
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: c2f64a617cae938ffe64ec8db313402785413c49
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280218"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>Habilitar o deshabilitar el envío de una renuncia de archivado a socios federados en Skype empresarial Server

En el momento de implementar los servidores perimetrales y habilitar la Federación de su organización, debe haber especificado si se enviará automáticamente la renuncia de archivado a los socios federados. Si archiva las comunicaciones externas, debe habilitar el envío de una renuncia de archivado. Use el procedimiento de este tema para cambiar esa configuración.

> [!NOTE]
> En el procedimiento siguiente se supone que ya ha habilitado la Federación de su organización. Para obtener más información sobre cómo habilitar la Federación, consulte [habilitar o deshabilitar el acceso de usuarios remotos](enable-or-disable-remote-user-access.md).


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>Para habilitar o deshabilitar el envío de una renuncia de archivado a socios federados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**, haga clic en **configuración del borde de Access**.

4.  En la ficha **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y, luego, en **Mostrar detalles**.

5.  En **Editar configuración del límite de acceso**, en **Habilitar la comunicación con usuarios federados**, Active o desactive la casilla **Enviar renuncia de archivado a socios federados** para habilitar o deshabilitar el envío automático de archivados párrafo.

6.  Haga clic en **Confirmar**.

Para permitir a los usuarios federados colaborar con los usuarios de su implementación de Skype empresarial Server, también debe haber configurado al menos una directiva de acceso externa para admitir el acceso de usuarios federados. Para obtener más información sobre cómo controlar el acceso a dominios federados específicos, consulte [configurar la compatibilidad de dominios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Habilitar o deshabilitar la renuncia de archivado mediante cmdlets de Windows PowerShell

El uso de la renuncia de archivado se puede administrar mediante Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration. Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. 

## <a name="to-enable-the-archiving-disclaimer"></a>Para habilitar la renuncia de archivado

  - Para habilitar la declinación de responsabilidades de archivado, establezca el valor de la propiedad **EnableArchivingDisclaimer** en True ($True):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>Para deshabilitar la renuncia de archivado

  - Para deshabilitar la declinación de responsabilidades de archivado, establezca el valor de la propiedad **EnableArchivingDisclaimer** en False ($False):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


