---
title: "Lync Server 2013: Directivas para el control de acceso de usuarios federados de XMPP"
TOCTitle: Configurar directivas para controlar el acceso de usuarios federados de XMPP
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ552446(v=OCS.15)
ms:contentKeyID: 49115267
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar directivas para controlar el acceso de usuarios federados de XMPP en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

Esta documentación es preliminar y está sujeta a cambios. Los temas en blanco que se incluyen actúan como marcadores de posición.

Cuando configura las directivas para admitir socios federados del Protocolo extensible de mensajería y presencia (XMPP), las directivas se aplican a los usuarios de dominios federados de XMPP, pero no a usuarios de proveedores de servicios de mensajería instantánea (IM) del Protocolo de inicio de sesión (SIP) (por ejemplo, Windows Live) o dominios federados de SIP. Configure un **Socio federado de XMPP** para cada dominio federado de XMPP al que desee que sus usuarios puedan agregar contactos y con el que puedan comunicarse. Las directivas de socios federados de XMPP están solamente disponibles en un único ámbito; pese a que no están definidas como una directiva global, actúan como una directiva global. Para definir una directiva de usuario o sitio global para los socios federados de XMPP, configure el ámbito de directiva en primer lugar creando y configurando la Directiva de acceso externo para el ámbito que necesita. Para obtener información detallada sobre los tipos de directivas que puede configurar para la federación y el acceso externo, consulte [Administración de la federación y el acceso externo a Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) en la documentación sobre operaciones.


> [!NOTE]
> Todas las directivas de <STRONG>Acceso externo y federación</STRONG> se aplican a través del aprovisionamiento en banda. Las directivas que se aplican al usuario, que pertenecen a un sitio o que tienen un ámbito global se comunican al cliente durante el inicio de sesión. Puede configurar directivas para controlar el acceso de socios federados de XMPP, incluso aunque no haya habilitado una federación de XMPP para su organización. Sin embargo, las directivas que configura entran en vigencia solo cuando tiene una federación de socios de XMPP implementada, habilitada o configurada para su organización. Para obtener información detallada sobre la implementación y configuración de la federación de socios de XMPP, consulte <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configurar la federación SIP, la federación XMPP y la mensajería instantánea pública en Lync Server 2013</A> en la documentación sobre implementación. Asimismo, si especifica una directiva de usuario en Directiva de acceso externo para controlar los socios federados de XMPP, la directiva se aplica solamente a los usuarios que están habilitados para Lync Server 2013 y configurados para utilizar la directiva.



## Editar una directiva global para socios federados de XMPP

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y, a continuación, en **Directiva de acceso externo**.

4.  En la página **Directiva de acceso externo**, realice lo siguiente para la directiva global:

5.  Haga clic en la directiva global, haga clic en **Editar** y, a continuación, en Mostrar detalles.

6.  Proporcione una descripción para la directiva global (opcional).

7.  Seleccione **Habilitar comunicaciones con usuarios federados**.

8.  Seleccione **Habilitar comunicaciones con usuarios federados XMPP**.

9.  Haga clic en **Confirmar** para guardar los cambios realizados en la directiva global.

## Crear una directiva de usuario o de sitio para socios federados de XMPP

1.  Haga clic en **Nuevo** y en **Directiva de sitio** o **Directiva de usuario**. En **Seleccionar un sitio**, haga clic en el sitio apropiado de la lista y, a continuación, en **Aceptar**.

2.  Proporcione una descripción para la directiva de sitio (opcional).

3.  En la directiva de usuario o de sitio, seleccione **Habilitar las comunicaciones con usuarios asociados**.

4.  Seleccione **Habilitar comunicaciones con usuarios federados XMPP**.

5.  Haga clic en **Confirmar** para guardar los cambios en la directiva de sitio o usuario.

## Editar una directiva existente para socios federados de XMPP

1.  Para cambiar una directiva existente, seleccione la directiva correspondiente que aparece en la lista, haga clic en **Editar** y, a continuación en **Mostrar detalles**.

2.  Modificar o actualizar la descripción de la directiva (opcional).

3.  Seleccione o anule la selección de **Habilitar las comunicaciones con usuarios asociados**.

4.  Seleccione o anule la selección de **Habilitar las comunicaciones con usuarios asociados de XMPP**.

5.  Haga clic en **Confirmar** para guardar los cambios realizados en la directiva.

## Editar una directiva existente para socios federados de XMPP utilizando el Windows PowerShell

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Escriba lo siguiente en Shell de administración de Lync Server:
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Un comando de ejemplo que establecerá la directiva general para Acceso de usuarios asociados como habilitada y para Acceso de dominios de XMPP como habilitada:
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

## Crear una directiva de usuario o de sitio para socios federados de XMPP utilizando el Windows PowerShell

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Escriba lo siguiente en Shell de administración de Lync Server:
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Un comando de ejemplo que establecerá una directiva de sitio para el sitio Redmond para Acceso de usuarios asociados como habilitada y para Acceso de dominios de XMPP como habilitada:
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

## Eliminar una directiva existente para socios federados de XMPP utilizando el Windows PowerShell

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Escriba lo siguiente en Shell de administración de Lync Server:
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    Un comando de ejemplo que eliminará una directiva de usuario:
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  Un comando de ejemplo que restablecerá la directiva global a los valores predeterminados:
    
        Remove-CsExternalAccessPolicy -Identity global

## Vea también

#### Tareas

[Asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync en Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  

#### Otros recursos

[Administrar socios federados XMPP para su organización en Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Set-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)

