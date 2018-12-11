---
title: Configurar directivas para controlar el acceso de usuarios federados
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Al configurar directivas para admitir comunicaciones con los socios federados, las directivas se aplican a los usuarios de dominios federados. '
ms.openlocfilehash: fcb4b0651c81316e06ab659430c3b0e9e5664e64
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222992"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a>Configurar directivas para controlar el acceso de usuarios federados en Skype para Business Server

Al configurar directivas para admitir comunicaciones con los socios federados, las directivas se aplican a los usuarios de dominios federados. Puede configurar uno o más directivas de acceso de usuarios externos para controlar si los usuarios de dominios federados puedan colaborar con su Skype para los usuarios de Business Server. Para controlar el acceso de usuarios federados, puede configurar las directivas a nivel global, sitio y el nivel de usuario. Skype para la configuración de directiva de Business Server que se aplican en un nivel de directiva puede invalidar la configuración que se aplica en el nivel de directiva de otra. Skype para la prioridad de la directiva de Business Server es: directiva de usuario (más influencia) reemplaza una directiva de sitio y, a continuación, una directiva de sitio invalida una directiva Global (menos influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.


> [!NOTE]  
> Puede configurar directivas para controlar el acceso de usuarios federados, incluso si no ha habilitado la federación para su organización. Sin embargo, las directivas que configurar entren en vigor sólo cuando tenga federación habilitada para su organización. Para obtener información detallada acerca de cómo habilitar la federación, vea [Habilitar o deshabilitar el acceso de usuarios remotos](../access-edge/enable-or-disable-remote-user-access.md).  Además, si se especifica una directiva de usuario para controlar el acceso de usuarios federados, la directiva se aplica sólo a los usuarios que están habilitados para Skype para Business Server y configurados para utilizar la directiva.


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>Para configurar una directiva para admitir el acceso de usuarios de dominios federados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.

3.  En la barra de navegación izquierda, haga clic en **Acceso de usuarios externos**y, a continuación, haga clic en **Directiva de acceso externo**.

4.  En la página **Directiva de acceso externo** , realice una de las siguientes:
    
      - Para configurar la directiva global para admitir el acceso de usuarios federados, haga clic en la directiva global, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.
    
      - Para crear una nueva directiva de sitio, haga clic en **nuevo**y, a continuación, haga clic en **Directiva de sitio**. En **Seleccionar un sitio**, haga clic en el sitio apropiado de la lista y, a continuación, haga clic en **Aceptar**.
    
      - Para crear una nueva directiva de usuario, haga clic en **nuevo**y, a continuación, haga clic en **Directiva de usuario**. En la **Nueva directiva de acceso externo**, cree un nombre único en el campo **nombre** que indica qué usuario cubiertos por la directiva (por ejemplo, **EnableFederatedUsers** para una directiva de usuario que permite a comunicaciones para los usuarios de dominio federado).
    
      - Para cambiar una directiva existente, haga clic en la directiva correspondiente que aparece en la tabla, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

5.  (Opcional) Si desea agregar o editar una descripción, especifique la información de la directiva en **Descripción**.

6.  Siga uno de estos pasos:
    
      - Para habilitar el acceso de usuarios federados para la directiva, active la casilla de verificación **Habilitar las comunicaciones con los usuarios federados** .
    
      - Para deshabilitar el acceso de usuarios federados para la directiva, desactive la casilla de verificación **Habilitar las comunicaciones con los usuarios federados** .

7.  Haga clic en **Confirmar**.

Para habilitar el acceso de usuarios federados, también debe habilitar la compatibilidad para la federación en la organización. Para obtener información detallada, vea [Habilitar o deshabilitar la federación y la conectividad de mensajería instantánea pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

Si se trata de una directiva de usuario, también debe aplicar la directiva a los usuarios que desea que puedan colaborar con los usuarios federados. Para obtener información detallada, vea [asignar una directiva de acceso de usuarios externos](assign-an-external-user-access-policy.md).

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Para configurar una directiva existente con Windows PowerShell para admitir el acceso de usuarios de dominios federados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Iniciar el Skype para Shell de administración de negocios Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para Business Server**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.

3.  Escriba lo siguiente en el Skype para Shell de administración de servidor empresarial:
    
    ```
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > El parámetro "EnablePublicCloudAudioVideoAccess" no tiene una selección correspondiente en el Skype para el Panel de Control de servidor empresarial


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Para crear una nueva directiva de uso de Windows PowerShell para admitir el acceso de usuarios de dominios federados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Microsoft Skype para Business Server**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.

3.  Escriba lo siguiente en el Skype para Shell de administración de servidor empresarial:
    
    ```
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    Un ejemplo de creación de una nueva directiva de sitio:
    
    ```
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Para eliminar o restablecer una directiva de uso de Windows PowerShell para admitir el acceso de usuarios de dominios federados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Escriba lo siguiente en el Skype para Shell de administración de servidor empresarial
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    Un ejemplo de restablecimiento de la directiva global (la directiva global sólo puede tener su configuración se ha quitado. La directiva no se puede eliminar):
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    Para quitar una directiva de sitio, escriba:
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    Elimina la directiva de sitio Redmond. Para eliminar una directiva de usuario denominada UserEAPPolicy, escriba:
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a>Consulte también


[Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[Asignar una directiva de acceso de usuarios externos](assign-an-external-user-access-policy.md)

[Administrar dominios federados SIP para la organización](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[Administrar proveedores federados SIP para la organización](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[Set-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[Nueva CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

