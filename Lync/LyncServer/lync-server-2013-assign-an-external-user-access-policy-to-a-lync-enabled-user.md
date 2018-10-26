---
title: "Lync Server 2013: Asignar directiva de acceso de usuario externo a usuario con Lync"
TOCTitle: Asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48275650
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-22_

Si ha habilitado un usuario para Lync Server, puede configurar la federación SIP, la federación XMPP, el acceso de usuarios remotos y la conectividad de mensajería instantánea desde el Panel de control de Lync Server mediante la aplicación de las directivas adecuadas para usuarios concretos. Por ejemplo, si ha creado una directiva que permita el acceso de usuarios remotos, debe aplicarla al usuario antes de que este pueda conectarse a Lync Server desde una ubicación remota y colaborar con usuarios internos desde dicha ubicación.


> [!NOTE]
> Para permitir el acceso de usuarios externos, debe habilitar la compatibilidad para cada tipo de acceso de usuarios externos que desee permitir y configurar las directivas adecuadas y otras opciones para controlar su uso. Para más información, consulte <A href="lync-server-2013-configuring-support-for-external-user-access.md">Configurar la compatibilidad para el acceso de usuarios externos en Lync Server 2013</A> en la documentación referente a la implementación o <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">Administración de la federación y el acceso externo a Lync Server 2013</A> en la documentación referente a operaciones.



Use el procedimiento descrito en este tema para aplicar una directiva de acceso de usuarios externos creada previamente a una o varias cuentas de usuario.

## Para aplicar una directiva de usuario externo a una cuenta de usuario

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios** y, a continuación, busque en la cuenta de usuario que desea configurar.

4.  En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, a continuación, en **Mostrar detalles** .

5.  En **Editar usuario de Lync Server** en **Directiva de acceso externo** , seleccione la directiva de usuario que desea aplicar.
    

    > [!NOTE]
    > En la configuración <STRONG>&lt;Automática&gt;</STRONG> , aplique las opciones de directiva global del servidor predeterminada.



## Asignar directivas de acceso externo por usuario mediante cmdlets de Windows PowerShell

Las directivas de acceso externo por usuario se pueden asignar con el Windows PowerShell y el cmdlet Grant-CsExternalAccessPolicy. Puede ejecutar el cmdlet desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para asignar una directiva de acceso externo por usuario a un solo usuario

  - Este comando asigna la directiva de acceso externo por usuario RedmondExternalAccessPolicy al usuario Ken Myer.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

## Para asignar una directiva de acceso externo por usuario a varios usuarios

  - Este comando asigna la directiva de acceso externo por usuario USAExternalAccessPolicy a todos los usuarios que tienen cuentas en la unidad organizativa (OU) de los Estados Unidos en Active Directory. Para más información sobre el parámetro OU utilizado en este comando, consulte la información sobre el cmdlet [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser).
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

## Para cancelar la asignación de una directiva de acceso externo por usuario

  - Este comando anula la asignación de una directiva de acceso externo por usuario que se había asignado a Ken Myer. Una vez anulada la asignación, el usuario Ken Myer será administrado por la directiva global o, si la hay, por su directiva de sitio local. Las directivas de sitio tienen preferencia sobre la directiva global.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

Si desea más información, consulte el tema de ayuda relativo al cmdlet [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy).

