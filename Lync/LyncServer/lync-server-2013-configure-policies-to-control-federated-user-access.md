---
title: 'Lync Server 2013: Configurar directivas para controlar el acceso de usuarios federados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control federated user access
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fb009561c36395ee31a49986f2db0103cbe096b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-federated-user-access-in-lync-server-2013"></a>Configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-05_

Al configurar directivas para admitir las comunicaciones con socios federados, las directivas se aplican a los usuarios de dominios federados. Puede configurar una o más directivas de acceso de usuarios externos para controlar si los usuarios de dominios federados pueden colaborar con los usuarios de Lync Server 2013. Para controlar el acceso de usuarios federados, puede configurar directivas en el nivel global, de sitio y de usuario. La configuración de directiva de Lync Server que se aplica a un nivel de Directiva puede invalidar la configuración que se aplica a otro nivel de directiva. La prioridad de la Directiva de Lync Server es: la Directiva de usuario (más influencia) reemplaza a una directiva de sitio y, después, una directiva de sitio invalida una directiva global (menor influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.

<div>


> [!NOTE]  
> Puede configurar directivas para controlar el acceso de usuarios federados, incluso si no ha habilitado la Federación de su organización. Sin embargo, las directivas que configure solo estarán vigentes cuando tenga habilitada la Federación de su organización. Para obtener más información sobre cómo habilitar la Federación, vea <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013</A> en la documentación de implementación o en la documentación de operaciones. Además, si especifica una directiva de usuario para controlar el acceso de usuarios federados, la Directiva solo se aplica a los usuarios que están habilitados para Lync Server 2013 y están configurados para usar la Directiva.



</div>

<div>

## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>Para configurar una directiva para admitir el acceso de usuarios de dominios federados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

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

Para habilitar el acceso de usuarios federados, también debe habilitar la compatibilidad con la Federación de su organización. Para obtener más información, vea [habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).

Si se trata de una directiva de usuario, también debe aplicar la Directiva a los usuarios que desee que puedan colaborar con los usuarios federados. Para obtener más información, consulte [asignar una directiva de acceso de usuarios externos a un usuario habilitado de Lync en Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).

</div>

<div>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Para configurar una directiva existente mediante Windows PowerShell para admitir el acceso de usuarios de dominios federados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Escriba lo siguiente en el shell de administración de Lync Server:
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    Un comando de ejemplo que establecerá la directiva global de acceso de usuarios federados en habilitado, acceso de dominio XMPP a acceso de usuarios remotos habilitado a acceso de usuarios remotos a habilitado, acceso de proveedor público a habilitado y concesión de la posibilidad de usar audio y vídeo para los proveedores públicos que lo admitan:
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    <div>
    

    > [!TIP]  
    > El parámetro "EnablePublicCloudAudioVideoAccess" no tiene una selección correspondiente en el panel de control de Lync Server.

    
    </div>

</div>

<div>

## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Para crear una nueva directiva con Windows PowerShell para admitir el acceso de usuarios de dominios federados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Escriba lo siguiente en el shell de administración de Lync Server:
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    Un ejemplo de creación de una nueva Directiva de sitio:
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

</div>

<div>

## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Para eliminar o restablecer una directiva con Windows PowerShell para admitir el acceso de usuarios de dominios federados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Escriba lo siguiente en el shell de administración de Lync Server
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    Un ejemplo de restablecimiento de la directiva global (la directiva global solo puede tener su configuración desinstalada). No se puede eliminar la Directiva):
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    Para quitar una directiva de sitio, escriba:
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    Elimina la Directiva de sitio de Redmond. Para eliminar una directiva de usuario denominada UserEAPPolicy, escriba:
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

</div>

<div>

## <a name="see-also"></a>Vea también


[Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[Asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync en Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  


[Administrar dominios federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Administrar proveedores federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[Nuevo: CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

