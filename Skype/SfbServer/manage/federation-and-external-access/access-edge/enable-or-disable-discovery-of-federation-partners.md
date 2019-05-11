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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En el momento en que implementan los servidores perimetrales y habilitado la federación para su organización, debe ha especificado si desea admitir la detección automática de dominios de socios federados.
ms.openlocfilehash: cf12190b03df30f4a15f6ed5e0499aa97c66e576
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919517"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>Habilitar o deshabilitar la detección de los socios de federación de Skype para Business Server

En el momento en que implementan los servidores perimetrales y habilitado la federación para su organización, debe ha especificado si desea admitir la detección automática de dominios de socios federados. Use el procedimiento de este tema para cambiar dicha configuración.

> [!NOTE]  
> El siguiente procedimiento se supone que ya ha habilitado la federación para su organización. Para obtener información detallada acerca de cómo habilitar la federación, vea [Habilitar o deshabilitar el acceso de usuarios remotos](enable-or-disable-remote-user-access.md).

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>Para habilitar o deshabilitar la detección automática de dominios federados para la organización

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.

3.  En la barra de navegación izquierda, haga clic en **Acceso de usuarios externos**, haga clic en **Configuración perimetral de acceso**.

4.  En la página **Configuración perimetral de acceso** , haga clic en **Global**, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

5.  En **Editar configuración perimetral de acceso**, en **Habilitar las comunicaciones con los usuarios federados**, active o desactive la casilla de verificación **Habilitar la detección de dominio de socio** para habilitar o deshabilitar la detección automática de dominios de socios.

6.  Haga clic en **Confirmar**.

Para habilitar los usuarios federados puedan colaborar con los usuarios de su Skype para la implementación de Business Server, debe haber configurado también al menos una directiva de acceso externo para admitir el acceso de usuarios federados. Para obtener información detallada, vea [Habilitar o deshabilitar la federación y la conectividad de mensajería instantánea pública](enable-or-disable-federation-and-public-im-connectivity.md). Para obtener información detallada acerca de cómo controlar el acceso de dominios federados concretos, vea [Administrar SIP dominios federados](../sip-domains/manage-sip-federated-domains-for-your-organization.md) y [Administrar SIP proveedores federados](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Habilitar o deshabilitar la detección de socios federados mediante el uso de cmdlets de Windows PowerShell

Detección de socios federados se puede administrar mediante Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration. Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. 


## <a name="to-enable-discovery-of-federation-partners"></a>Para habilitar la detección de los socios federados

  - Para habilitar la detección de socios federados, establezca el valor de la propiedad **EnablePartnerDiscovery** en True ($True). Tenga en cuenta que debe habilitar DNS SRV enrutamiento con el fin de cambiar este valor de la propiedad.
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>Para deshabilitar la detección de socios federados

  - Para deshabilitar la detección de socios federados, establezca el valor de la propiedad **EnablePartnerDiscovery** en False ($False):
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

