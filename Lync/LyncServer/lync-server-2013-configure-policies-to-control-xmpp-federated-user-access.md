---
title: 'Lync Server 2013: Configurar directivas para controlar el acceso de usuarios federados de XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control XMPP federated user access
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552446(v=OCS.15)
ms:contentKeyID: 48679557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc79a915d0735f87c0852dff0ba4228b1e391fd8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a>Configurar directivas para controlar el acceso de usuarios federados de XMPP en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Esta documentación es preliminar y está sujeta a cambios. Los temas en blanco que se incluyen actúan como marcadores de posición.

Al configurar directivas para la compatibilidad de los socios federados protocolo de presencia y mensajería extensible (XMPP), las directivas se aplican a los usuarios de XMPP Federated Domains, pero no a los usuarios de proveedores de servicios de mensajería instantánea (mi) protocolo de inicio de sesión (SIP) (por ejemplo, Windows Live) o dominios federados de SIP. Configure un **socio de XMPP federado** para cada dominio de XMPP federado que desee permitir a los usuarios que añadan contactos y se comuniquen con ellos. Las directivas de socios de XMPP federados solo están disponibles en un solo ámbito, aunque no se define como una directiva global, actúa como una directiva global. Para definir una directiva global, de sitio o de usuario para los asociados de Federación de XMPP, debe configurar el ámbito de la Directiva creando y configurando en primer lugar la Directiva de acceso externo para el ámbito que necesite. Para obtener más información sobre los tipos de directivas que puede configurar para el acceso externo y la Federación, consulte [administrar la Federación y el acceso externo a Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) en la documentación de operaciones.

<div>


> [!NOTE]  
> Todas las directivas de <STRONG>Federación y acceso externo</STRONG> se aplican mediante aprovisionamiento en banda. Las directivas que se aplican al usuario, pertenecen a un sitio o que se encuentran en ámbito global se comunican al cliente durante el inicio de sesión. Puede configurar directivas para controlar el acceso al socio XMPP federado, incluso si no ha habilitado la Federación de XMPP para su organización. Sin embargo, las directivas que configure se aplicarán solamente cuando tenga la Federación XMPP Partner implementada, habilitada y configurada para su organización. Para obtener más información sobre cómo implementar y configurar la Federación de socios XMPP, vea <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">configurar la Federación SIP, la Federación XMPP y la mensajería instantánea pública en Lync Server 2013</A> en la documentación de implementación. Además, si especifica una directiva de usuario en la Directiva de acceso externo para controlar los socios federados de XMPP, la Directiva solo se aplica a los usuarios que están habilitados para Lync Server 2013 y se han configurado para usar la Directiva.



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a>Para editar una directiva global para los socios de XMPP federados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**y, después, en **Directiva de acceso externo**.

4.  En la página **Directiva de acceso externo** , haga lo siguiente para la directiva global:

5.  Haga clic en la directiva global, haga clic en **Editar**y, a continuación, haga clic en Mostrar detalles.

6.  Proporcione una descripción para la directiva global (opcional).

7.  Seleccione **Habilitar comunicaciones con usuarios federados**.

8.  Seleccione **Habilitar comunicaciones con usuarios federados de XMPP**.

9.  Haga clic en **confirmar** para guardar los cambios en la directiva global.

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a>Para crear un sitio o una directiva de usuario para socios de XMPP federados

1.  Haga clic en **nuevo**y, a continuación, en **Directiva del sitio** o **Directiva de usuario**. En **seleccionar un sitio**, haga clic en el sitio adecuado de la lista y, a continuación, haga clic en **Aceptar**.

2.  Proporcione una descripción para la Directiva de sitio (opcional).

3.  En el sitio o la Directiva de usuario, seleccione **habilitar las comunicaciones con usuarios federados**.

4.  Seleccione **Habilitar comunicaciones con usuarios federados de XMPP**.

5.  Haga clic en **confirmar** para guardar los cambios en el sitio o en la Directiva de usuario.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a>Para editar una directiva existente para socios de XMPP federados

1.  Para cambiar una directiva existente, seleccione la directiva correspondiente en la lista, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

2.  Cambiar o actualizar la descripción de la Directiva (opcional).

3.  Active o desactive **Habilitar comunicaciones con usuarios federados**.

4.  Active o desactive **Habilitar comunicaciones con usuarios federados de XMPP**.

5.  Haga clic en **confirmar** para guardar los cambios en la Directiva.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Para editar una directiva existente para los socios de XMPP federados mediante Windows PowerShell

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Escriba lo siguiente en el shell de administración de Lync Server:
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Un comando de ejemplo que establecerá la directiva global para el acceso de usuarios federados a verdadero (habilitado) y el acceso al dominio XMPP a verdadero (habilitado):
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a>Para crear un sitio o una directiva de usuario para socios de XMPP federados con Windows PowerShell

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Escriba lo siguiente en el shell de administración de Lync Server:
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Un comando de ejemplo que establecerá una directiva de sitio para el sitio de Redmond para el acceso de usuarios federados a habilitado y el acceso al dominio XMPP a habilitado:
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Para eliminar una directiva existente para los socios de XMPP federados mediante Windows PowerShell

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Escriba lo siguiente en el shell de administración de Lync Server:
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    Un comando de ejemplo que eliminará una directiva de usuario:
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  Un comando de ejemplo que restablecerá la directiva global a los valores predeterminados:
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a>Vea también


[Asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync en Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[Administrar socios federados XMPP para su organización en Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
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

