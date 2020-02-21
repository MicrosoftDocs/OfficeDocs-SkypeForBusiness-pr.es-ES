---
title: 'Lync Server 2013: configurar directivas para controlar el acceso de usuarios federados de XMPP'
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
ms.openlocfilehash: 31889fa60f86d269e5efab696c2c27e48cc55d59
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a>Configurar directivas para controlar el acceso de usuarios federados de XMPP en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Esta documentación es preliminar y está sujeta a cambios. Los temas en blanco se incluyen para referencia futura.

Cuando configura las directivas para admitir socios federados del Protocolo extensible de mensajería y presencia (XMPP), las directivas se aplican a los usuarios de dominios federados de XMPP, pero no a usuarios de proveedores de servicios de mensajería instantánea (IM) del Protocolo de inicio de sesión (SIP) (por ejemplo, Windows Live) o dominios federados de SIP. Configure un **Socio federado de XMPP** para cada dominio federado de XMPP al que desee que sus usuarios puedan agregar contactos y con el que puedan comunicarse. Las directivas de socios federados de XMPP están solamente disponibles en un único ámbito; pese a que no están definidas como una directiva global, actúan como una directiva global. Para definir una directiva de usuario o sitio global para los socios federados de XMPP, configure el ámbito de directiva en primer lugar creando y configurando la Directiva de acceso externo para el ámbito que necesita. Para obtener más información sobre los tipos de directivas que puede configurar para el acceso externo y la Federación, consulte [Managing Federation and external Access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) en la documentación de operaciones.

<div>


> [!NOTE]  
> Todas las directivas de <STRONG>Acceso externo y federación</STRONG> se aplican a través del aprovisionamiento en banda. Las directivas que se aplican al usuario, que pertenecen a un sitio o que tienen un ámbito global se comunican al cliente durante el inicio de sesión. Puede configurar directivas para controlar el acceso de socios federados de XMPP, incluso aunque no haya habilitado una federación de XMPP para su organización. Sin embargo, las directivas que configura entran en vigencia solo cuando tiene una federación de socios de XMPP implementada, habilitada o configurada para su organización. Para obtener información detallada sobre la implementación y la configuración de la Federación del asociado XMPP, consulte <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configuring SIP Federation, XMPP Federation and Public Instant Messaging in Lync Server 2013</A> en la documentación sobre implementación. Además, si especifica una directiva de usuario en la Directiva de acceso externo para controlar los socios federados XMPP, la Directiva solo se aplicará a los usuarios que estén habilitados para Lync Server 2013 y que estén configurados para usar la Directiva.



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a>Editar una directiva global para socios federados de XMPP

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En el barra de navegación izquierda, haga clic en  **Acceso para usuarios externos ** y, a continuación, en  **Directiva de acceso externo **.

4.  En la página **Directiva de acceso externo**, realice lo siguiente para la directiva global:

5.  Haga clic en la directiva global, haga clic en **Editar** y, a continuación, en Mostrar detalles.

6.  Proporcione una descripción para la directiva global (opcional).

7.  Seleccione **Habilitar las comunicaciones con usuarios asociados**.

8.  Seleccione **Habilitar comunicaciones con usuarios federados de XMPP**.

9.  Haga clic en **Confirmar** para guardar los cambios realizados en la directiva global.

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a>Crear una directiva de usuario o de sitio para socios federados de XMPP

1.  Haga clic en **Nuevo** y en **Directiva de sitio** o **Directiva de usuario**. En **Seleccionar un sitio**, haga clic en el sitio apropiado de la lista y, a continuación, en **Aceptar**.

2.  Proporcione una descripción para la directiva de sitio (opcional).

3.  En la directiva de usuario o de sitio, seleccione **Habilitar las comunicaciones con usuarios asociados**.

4.  Seleccione **Habilitar las comunicaciones con usuarios asociados de XMPP**.

5.  Haga clic en **Confirmar** para guardar los cambios realizados en la directiva de usuario o de sitio.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a>Editar una directiva existente para socios federados de XMPP

1.  Para cambiar una directiva existente, seleccione la directiva correspondiente que aparece en la lista, haga clic en **Editar** y, a continuación en **Mostrar detalles**.

2.  Modificar o actualizar la descripción de la directiva (opcional).

3.  Seleccione o anule la selección de **Habilitar las comunicaciones con usuarios asociados**.

4.  Seleccione o anule la selección de **Habilitar las comunicaciones con usuarios asociados de XMPP**.

5.  Haga clic en **Confirmar** para guardar los cambios realizados en la directiva.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Para editar una directiva existente para socios federados de XMPP mediante Windows PowerShell

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Escriba lo siguiente en el shell de administración de Lync Server:
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Un comando de ejemplo que establecerá la directiva global para el acceso de usuarios federados en verdadero (habilitado) y el acceso de dominio XMPP a verdadero (habilitado):
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a>Para crear una directiva de usuario o de sitio para socios federados de XMPP mediante Windows PowerShell

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Escriba lo siguiente en el shell de administración de Lync Server:
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Un comando de ejemplo que establecerá una directiva de sitio para el sitio Redmond para Acceso de usuarios asociados como habilitada y para Acceso de dominios de XMPP como habilitada:
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Para eliminar una directiva existente para socios federados de XMPP mediante Windows PowerShell

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Escriba lo siguiente en el shell de administración de Lync Server:
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    Un comando de ejemplo que eliminará una directiva de usuario:
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  Un comando de ejemplo que restablecerá la directiva global a los valores predeterminados:
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a>Consulta también


[Asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync en Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[Administrar socios federados XMPP en Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

