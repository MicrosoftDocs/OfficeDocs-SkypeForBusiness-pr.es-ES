---
title: Habilitar o deshabilitar la detección de socios de federación
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: En el momento de implementar los servidores perimetrales y de habilitar la Federación de su organización, debe haber especificado si se debe admitir la detección automática de dominios federados de socios.
ms.openlocfilehash: a64e2056feacbee076fcaf9b0012a36f72c91523
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818401"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>Habilitar o deshabilitar la detección de socios de Federación en Skype empresarial Server

En el momento de implementar los servidores perimetrales y de habilitar la Federación de su organización, debe haber especificado si se debe admitir la detección automática de dominios federados de socios. Use el procedimiento de este tema para cambiar esa configuración.

> [!NOTE]  
> En el procedimiento siguiente se supone que ya ha habilitado la Federación de su organización. Para obtener más información sobre cómo habilitar la Federación, consulte [habilitar o deshabilitar el acceso de usuarios remotos](enable-or-disable-remote-user-access.md).

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>Para habilitar o deshabilitar la detección automática de dominios federados para su organización

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.

3.  En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**, haga clic en **configuración del borde de Access**.

4.  En la página **configuración de perímetro de Access** , haga clic en **global**, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

5.  En **Editar configuración del límite de acceso**, en **habilitar las comunicaciones con usuarios federados**, Active o desactive la casilla **Habilitar la detección** de dominios asociados para habilitar o deshabilitar la detección automática de dominios asociados.

6.  Haga clic en **Confirmar**.

Para permitir a los usuarios federados colaborar con los usuarios de su implementación de Skype empresarial Server, también debe haber configurado al menos una directiva de acceso externa para admitir el acceso de usuarios federados. Para obtener más información, vea [habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública](enable-or-disable-federation-and-public-im-connectivity.md). Para obtener más información sobre cómo controlar el acceso a determinados dominios federados, consulte [administrar dominios federados SIP](../sip-domains/manage-sip-federated-domains-for-your-organization.md) y [administrar proveedores federados de SIP](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Habilitar o deshabilitar la detección de socios de Federación mediante cmdlets de Windows PowerShell

El descubrimiento de los socios de la Federación se puede administrar mediante Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration. Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. 


## <a name="to-enable-discovery-of-federation-partners"></a>Para habilitar la detección de socios de Federación

  - Para habilitar la detección de socios de Federación, establezca el valor de la propiedad **EnablePartnerDiscovery** en True ($true). Tenga en cuenta que debe habilitar el enrutamiento SRV de DNS para poder cambiar este valor de propiedad.
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>Para deshabilitar la detección de socios de Federación

  - Para deshabilitar la detección de socios de Federación, establezca el valor de la propiedad **EnablePartnerDiscovery** en False ($false):
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

