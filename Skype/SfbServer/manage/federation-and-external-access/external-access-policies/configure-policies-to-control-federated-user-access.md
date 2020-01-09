---
title: Configurar directivas para controlar el acceso de usuarios federados
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
localization_priority: Normal
description: 'Al configurar directivas para admitir las comunicaciones con socios federados, las directivas se aplican a los usuarios de dominios federados. '
ms.openlocfilehash: d9192589191590cd96f72323681ef4df6513e36d
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991765"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a>Configurar directivas para controlar el acceso de usuarios federados en Skype empresarial Server

Al configurar directivas para admitir las comunicaciones con socios federados, las directivas se aplican a los usuarios de dominios federados. Puede configurar una o más directivas de acceso de usuarios externos para controlar si los usuarios de dominios federados pueden colaborar con los usuarios de Skype empresarial Server. Para controlar el acceso de usuarios federados, puede configurar directivas en el nivel global, de sitio y de usuario. La configuración de directiva de Skype empresarial Server que se aplica a un nivel de Directiva puede invalidar la configuración que se aplica a otro nivel de directiva. La prioridad de la Directiva de servidor de Skype empresarial es: la Directiva de usuario (más influencia) reemplaza a una directiva de sitio y, después, una directiva de sitio invalida una directiva global (menor influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.


> [!NOTE]  
> Puede configurar directivas para controlar el acceso de usuarios federados, incluso si no ha habilitado la Federación de su organización. Sin embargo, las directivas que configure solo estarán vigentes cuando tenga habilitada la Federación de su organización. Para obtener más información sobre cómo habilitar la Federación, consulte [habilitar o deshabilitar el acceso de usuarios remotos](../access-edge/enable-or-disable-remote-user-access.md).  Además, si especifica una directiva de usuario para controlar el acceso de usuarios federados, la Directiva solo se aplica a los usuarios que están habilitados para Skype empresarial Server y que se han configurado para usar la Directiva.


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>Para configurar una directiva para admitir el acceso de usuarios de dominios federados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.

3.  En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**y, después, en **Directiva de acceso externo**.

4.  En la página **Directiva de acceso externo** , realice una de las siguientes acciones:
    
      - Para configurar la directiva global para admitir el acceso de usuarios federados, haga clic en la directiva global, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.
    
      - Para crear una nueva Directiva de sitio, haga clic en **nueva**y, a continuación, haga clic en **Directiva del sitio**. En **seleccionar un sitio**, haga clic en el sitio adecuado de la lista y, a continuación, haga clic en **Aceptar**.
    
      - Para crear una nueva Directiva de usuario, haga clic en **nueva**y, a continuación, haga clic en **Directiva de usuario**. En **nueva Directiva de acceso externo**, cree un nombre único en el campo **nombre** que indique lo que cubre la Directiva de usuario (por ejemplo, **EnableFederatedUsers** para una directiva de usuario que permita las comunicaciones de usuarios de dominios federados).
    
      - Para cambiar una directiva existente, haga clic en la directiva correspondiente que aparece en la tabla, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

5.  Faculta Si desea agregar o editar una descripción, especifique la información de la Directiva en **Descripción**.

6.  Siga uno de estos pasos:
    
      - Para habilitar el acceso de usuarios federados para la Directiva, active la casilla **Habilitar comunicaciones con usuarios federados** .
    
      - Para deshabilitar el acceso de usuarios federados para la Directiva, desactive la casilla **Habilitar comunicaciones con usuarios federados** .

7.  Haga clic en **Confirmar**.

Para habilitar el acceso de usuarios federados, también debe habilitar la compatibilidad con la Federación de su organización. Para obtener más información, vea [habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

Si se trata de una directiva de usuario, también debe aplicar la Directiva a los usuarios que desee que puedan colaborar con los usuarios federados. Para obtener más información, consulte [asignar una directiva de acceso de usuarios externos](assign-an-external-user-access-policy.md).

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Para configurar una directiva existente mediante Windows PowerShell para admitir el acceso de usuarios de dominios federados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Inicie el shell de administración de Skype para Business Server: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Skype empresarial Server**y, a continuación, haga clic en **consola de administración de Skype empresarial**.

3.  Escriba lo siguiente en el shell de administración de Skype empresarial Server:
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > El parámetro "EnablePublicCloudAudioVideoAccess" no tiene una selección correspondiente en el panel de control de Skype empresarial Server.


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Para crear una nueva directiva con Windows PowerShell para admitir el acceso de usuarios de dominios federados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, **Microsoft Skype empresarial Server**y, por último, haga clic en **consola de administración de Skype empresarial Server**.

3.  Escriba lo siguiente en el shell de administración de Skype empresarial Server:
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    Un ejemplo de creación de una nueva Directiva de sitio:
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Para eliminar o restablecer una directiva con Windows PowerShell para admitir el acceso de usuarios de dominios federados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Escriba lo siguiente en el shell de administración de Skype empresarial Server
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    Un ejemplo de restablecimiento de la directiva global (la directiva global solo puede tener su configuración desinstalada). No se puede eliminar la Directiva):
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    Para quitar una directiva de sitio, escriba:
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    Elimina la Directiva de sitio de Redmond. Para eliminar una directiva de usuario denominada UserEAPPolicy, escriba:
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a>Vea también


[Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[Asignar una directiva de acceso de usuario externo](assign-an-external-user-access-policy.md)

[Administrar dominios federados SIP para la organización](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[Administrar proveedores federados SIP para la organización](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[Set-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[Nuevo: CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

