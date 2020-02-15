---
title: Configuración de directivas para controlar el acceso de usuarios federados
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
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
description: 'Al configurar directivas para admitir comunicaciones con socios federados, las directivas se aplican a los usuarios de dominios federados. '
ms.openlocfilehash: 447aad751ce6fc91bf2d6b80c8a14e92f9d4da82
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037410"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a>Configuración de directivas para controlar el acceso de usuarios federados en Skype empresarial Server

Al configurar directivas para admitir comunicaciones con socios federados, las directivas se aplican a los usuarios de dominios federados. Puede configurar una o más directivas de acceso de usuarios externos para controlar si los usuarios de dominios federados pueden colaborar con los usuarios de Skype empresarial Server. Puede configurar directivas de nivel global, de sitio y de usuario para controlar el acceso de usuarios federados. La configuración de directivas de Skype empresarial Server que se aplica a un nivel de Directiva puede invalidar la configuración que se aplica en otro nivel de directiva. La prioridad de la Directiva de Skype empresarial Server es: la Directiva de usuario (más influencia) reemplaza una directiva de sitio y, a continuación, una directiva de sitio invalida una directiva global (menor influencia). Esto significa que cuanto más cerca esté la configuración de la Directiva, el objeto al que afecta la Directiva, más influencia tendrá en el objeto.


> [!NOTE]  
> Puede configurar directivas para controlar el acceso de usuarios federados, incluso aunque no haya habilitado una federación para la organización. Sin embargo, las directivas que configure únicamente surtirán efecto cuando haya habilitado la federación en la organización. Para obtener información detallada acerca de la habilitación de la Federación, consulte [habilitar o deshabilitar el acceso de usuarios remotos](../access-edge/enable-or-disable-remote-user-access.md).  Además, si especifica una directiva de usuario para controlar el acceso de usuarios federados, la Directiva solo se aplica a los usuarios que están habilitados para Skype empresarial Server y que están configurados para usar la Directiva.


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>Para configurar una directiva para permitir el acceso de usuarios de dominios federados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.

3.  En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y, a continuación, en **Directiva de acceso externo**.

4.  En la página **Directiva de acceso externo**, siga uno de estos procedimientos:
    
      - Para configurar la directiva global para permitir el acceso de usuarios federados, haga clic en la directiva global, en **Editar** y en **Mostrar detalles**.
    
      - Para crear una directiva de sitio nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de sitio**. En **Seleccionar un sitio**, haga clic en el sitio apropiado de la lista y, a continuación, en **Aceptar**.
    
      - Para crear una directiva de usuario nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de usuario**. En **Nueva directiva de acceso externo**, cree un nombre único en el campo **Nombre** que indique lo que cubre la directiva de usuario (por ejemplo, **PermitirUsuariosFederados** para una directiva de usuario que permita comunicaciones para usuarios de dominios federados).
    
      - Para cambiar una directiva existente, haga clic en la directiva correspondiente que aparece en la tabla, en **Editar** y, a continuación en **Mostrar detalles**.

5.  (Opcional) Si quiere agregar o editar una descripción, especifique la información para la directiva en **Descripción**.

6.  Siga uno de estos procedimientos:
    
      - Para habilitar el acceso de usuarios federados para la directiva, active la casilla **Habilitar comunicaciones con usuarios federados**.
    
      - Para deshabilitar el acceso de usuarios federados para la directiva, desactive la casilla **Habilitar comunicaciones con usuarios federados**.

7.  Haga clic en **Confirmar**.

Para habilitar el acceso de usuarios federados, también debe admitir una federación en la organización. Para obtener más información, consulte [habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

Si se trata de una directiva de usuario, también tiene que aplicar la directiva a los usuarios que desee que puedan colaborar con usuarios federados. Para obtener más información, consulte [asignar una directiva de acceso de usuario externo](assign-an-external-user-access-policy.md).

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Para configurar una directiva existente mediante Windows PowerShell para permitir el acceso de usuarios de dominios federados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, en **todos los programas**, en **Skype empresarial Server**y, a continuación, en **Shell de administración de Skype empresarial Server**.

3.  Escriba lo siguiente en el shell de administración de Skype empresarial Server:
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > El parámetro "EnablePublicCloudAudioVideoAccess" no tiene una selección correspondiente en el panel de control de Skype empresarial Server


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Para crear una nueva Directiva mediante Windows PowerShell para permitir el acceso de usuarios de dominios federados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, **todos los programas**, **Microsoft Skype empresarial Server**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.

3.  Escriba lo siguiente en el shell de administración de Skype empresarial Server:
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    Un ejemplo de creación de una nueva directiva de sitio:
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Para eliminar o restablecer una Directiva mediante Windows PowerShell para permitir el acceso de usuarios de dominios federados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Escriba lo siguiente en el shell de administración de Skype empresarial Server
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    Un ejemplo de restablecimiento de la directiva global (la directiva global solo puede tener su parámetro eliminado. La directiva no se puede eliminar):
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    Para quitar una directiva de sitio, escriba:
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    Elimina la directiva de sitio Redmond. Para eliminar una directiva de usuario denominada UserEAPPolicy, escriba:
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a>Vea también


[Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[Asignar una directiva de acceso de usuario externo](assign-an-external-user-access-policy.md)

[Administrar dominios federados SIP para la organización](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[Administrar proveedores federados SIP para la organización](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

