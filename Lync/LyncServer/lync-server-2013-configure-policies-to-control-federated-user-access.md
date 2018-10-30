﻿---
title: "Lync Server 2013: Config. directivas para controlar el acceso de usuarios federados"
TOCTitle: Configurar directivas para controlar el acceso de usuarios federados
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48275277
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013

 

_**Última modificación del tema:** 2014-02-05_

Al configurar directivas para admitir comunicaciones con socios federados, las directivas se aplican a los usuarios de dominios federados. Puede configurar una o varias directivas de acceso de usuarios externos para controlar si los usuarios de dominios federados pueden colaborar con sus usuarios de Lync Server 2013. Puede configurar directivas de nivel global, de sitio y de usuario para controlar el acceso de usuarios federados. La configuración de directiva de Lync Server que se aplica en un nivel de directiva puede invalidar la configuración que se aplica en otro nivel de directiva. La precedencia de directiva de Lync Server es esta: la directiva de usuario (de mayor influencia) invalida una directiva de sitio, y una directiva de sitio invalida una directiva global (de menor influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.


> [!NOTE]
> Puede configurar directivas para controlar el acceso de usuarios federados, incluso aunque no haya habilitado una federación para la organización. Sin embargo, las directivas que configure únicamente surtirán efecto cuando haya habilitado la federación en la organización. Si desea información sobre cómo activar la federación, consulte <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Habilitar y deshabilitar el acceso de usuarios remotos en Lync Server 2013</A> en la documentación de la implementación o la de operaciones. Además, si especifica una directiva de usuario para controlar el acceso de usuarios federados, la directiva solo se aplica a usuarios habilitados para Lync Server 2013 y que estén configurados para usar la directiva.



## Para configurar una directiva para permitir el acceso de usuarios de dominios federados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y, a continuación, en **Directiva de acceso externo**.

4.  En la página **Directiva de acceso externo**, siga uno de estos procedimientos:
    
      - Para configurar la directiva global para permitir el acceso de usuarios federados, haga clic en la directiva global, en **Editar** y, a continuación, en **Mostrar detalles**.
    
      - Para crear una directiva de sitio nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de sitio** . En **Seleccionar un sitio** , haga clic en el sitio apropiado de la lista y, a continuación, en **Aceptar** .
    
      - Para crear una directiva de usuario nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de usuario** . En **Nueva directiva de acceso externo** , cree un nombre único en el campo **Nombre** que indique lo que cubre la directiva de usuario (por ejemplo, **PermitirUsuariosFederados** para una directiva de usuario que permita comunicaciones para usuarios de dominios federados).
    
      - Para cambiar una directiva existente, haga clic en la directiva correspondiente que aparece en la tabla, en **Editar** y, a continuación, en **Mostrar detalles**.

5.  (Opcional) Si quiere agregar o editar una descripción, especifique la información para la directiva en **Descripción**.

6.  Siga uno de estos pasos:
    
      - Para habilitar el acceso de usuarios federados para la directiva, active la casilla **Habilitar comunicaciones con usuarios federados**.
    
      - Para deshabilitar el acceso de usuarios federados para la directiva, desactive la casilla **Habilitar comunicaciones con usuarios federados**.

7.  Haga clic en **Confirmar**.

Para habilitar el acceso de usuarios federados, también debe admitir una federación en la organización. Para más información, vea [Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).

Si se trata de una directiva de usuario, también tiene que aplicar la directiva a los usuarios que desee que puedan colaborar con usuarios federados. Para más información, vea [Asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync en Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).

## Para configurar una directiva existente con Windows PowerShell para admitir el acceso de usuarios de dominios federados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Escriba lo siguiente en Shell de administración de Lync Server:
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    
    Un comando de ejemplo que establecerá la directiva global para Acceso de usuarios federados en habilitado, Acceso de dominio XMPP en habilitado, Acceso de usuarios remotos en habilitado, Acceso de proveedores públicos en habilitado y conceder la capacidad de usar audio y vídeo de los proveedores públicos que lo admitan:
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    > [!TIP]  
    > El parámetro “EnablePublicCloudAudioVideoAccess” no tiene una selección correspondiente en el Panel de control de Lync Server
    


## Para crear una nueva directiva con Windows PowerShell para admitir el acceso de usuarios de dominios federados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Escriba lo siguiente en Shell de administración de Lync Server:
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    Un ejemplo de creación de una nueva directiva de sitio:
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

## Para eliminar o restablecer una directiva con Windows PowerShell para admitir el acceso de usuarios de dominios federados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Escriba lo siguiente en Shell de administración de Lync Server:
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    Un ejemplo de restablecimiento de la directiva global (la directiva global solo puede tener su parámetro eliminado. La directiva no se puede eliminar):
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    Para quitar una directiva de sitio, escriba:
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    Elimina la directiva de sitio Redmond. Para eliminar una directiva de usuario denominada UserEAPPolicy, escriba:
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

## Vea también

#### Tareas

[Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[Asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync en Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  

#### Otros recursos

[Administrar dominios federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Administrar proveedores federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[Set-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)

