---
title: Habilitar o deshabilitar la detección de socios de federación
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
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
description: En el momento en que implementa los servidores perimetrales y habilita la federación para la organización, debe especificar si se va a admitir la detección automática de los dominios de socios federados.
ms.openlocfilehash: e1f076b725dff149f024a3fd59f9f7d52da4e6a8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817430"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>Habilitar o deshabilitar la detección de socios de federación en Skype Empresarial Server

En el momento en que implementa los servidores perimetrales y habilita la federación para la organización, debe especificar si se va a admitir la detección automática de los dominios de socios federados. Para cambiar esa configuración, siga el procedimiento de este tema.

> [!NOTE]  
> En el procedimiento siguiente, se presupone que ya ha habilitado la federación para la organización. Para obtener más información sobre cómo habilitar la federación, vea [Habilitar o deshabilitar el acceso de usuarios remotos.](enable-or-disable-remote-user-access.md)

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>Para habilitar o deshabilitar la detección automática de dominios federados para la organización

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.

3.  En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y en **Configuración perimetral de acceso**.

4.  En la página **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y, a continuación en **Mostrar detalles**.

5.  En **Editar configuración perimetral de acceso**, en **Habilitar comunicaciones con usuarios federados**, active o desactive la casilla **Habilitar detección de dominio de socio** para habilitar o deshabilitar la detección automática de dominios de socios.

6.  Haga clic en **Confirmar**.

Para permitir que los usuarios federados colaboren con usuarios en su implementación de Skype Empresarial Server, también debe haber configurado al menos una directiva de acceso externo para admitir el acceso de usuarios federados. Para obtener más información, consulte [Habilitar o deshabilitar la federación y la conectividad de mensajería instantánea pública.](enable-or-disable-federation-and-public-im-connectivity.md) Para obtener más información sobre cómo controlar el acceso a dominios federados específicos, consulte Administrar dominios [federados SIP](../sip-domains/manage-sip-federated-domains-for-your-organization.md) y [Administrar proveedores federados SIP.](../sip-providers/manage-sip-federated-providers-for-your-organization.md)


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Habilitar o deshabilitar la detección de socios de federación mediante cmdlets Windows PowerShell federación

La detección de socios de federación se puede administrar mediante Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration federación. Este cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell. 


## <a name="to-enable-discovery-of-federation-partners"></a>Para habilitar la detección de socios de federación

  - Para habilitar la detección de socios federados, establezca el valor de la propiedad **EnablePartnerDiscovery** en True ($True). Tenga en cuenta que debe habilitar el enrutamiento SRV de DNS para poder cambiar el valor de esta propiedad.
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>Para deshabilitar la detección de socios de federación

  - Para deshabilitar la detección de socios federados, establezca el valor de la propiedad **EnablePartnerDiscovery** en False ($False).
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

