---
title: Asignación de una directiva de plan de marcado por usuario
TOCTitle: Asignación de una directiva de plan de marcado por usuario
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49889506
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Asignación de una directiva de plan de marcado por usuario

 

_**Última modificación del tema:** 2013-02-22_

Para completar la configuración de cuentas de usuario para los usuarios de Telefonía IP empresarial o para los usuarios de conferencias de acceso telefónico local, asigne un plan de marcado. Las cuentas de usuario emplearán automáticamente el plan de marcado global o, si existe, el plan de marcado del sitio, en los casos en los que no se asigne explícitamente un plan de marcado creado particularmente para el usuario. Si desea usar el plan de marcado global o del sitio para todos los usuarios habilitados para Enterprise Voice, puede omitir esta sección.

## Para asignar un plan de marcado mediante el Panel de control de Lync Server 2013

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el cuadro **Buscar usuarios** , escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar** .

5.  En la tabla, haga clic en la cuenta de usuario que desee asignar un plan de marcado.

6.  En el menú **Editar**, haga clic en **Mostrar detalles**.

7.  En la página **Editar usuario de Lync Server**, en **Telefonía**, haga clic en **Telefonía IP empresarial**.

8.  Haga clic en **Directiva de plan de marcado** y luego seleccione el plan de marcado que desee.

9.  Haga clic en **Confirmar**.

Para obtener más información sobre cómo configurar planes de marcado, consulte el tema [Configurar planes de marcado en Lync Server 2013](lync-server-2013-configuring-dial-plans.md).

## Para asignar un plan de marcado mediante el Shell de administración de Lync Server 2013

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Para asignar un plan de marcado específico del usuario, ejecute lo siguiente en el símbolo del sistema:
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    Por ejemplo:
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    En este ejemplo, al usuario con nombre para mostrar Carlos Tudela se le asigna el plan de marcado específico del usuario con el nombre **DialPlanJapan**.

Para ver los detalles de la asignación de un plan de marcado de usuario o de la ejecución del cmdlet **Grant-CsDialPlan**, consulte la documentación de [Shell de administración de Lync Server](lync-server-2013-lync-server-management-shell.md).

## Asignar un plan de marcado por usuario mediante cmdlets de Windows PowerShell

Los planes de marcado por usuario también pueden asignarse mediante el uso de Windows PowerShell y del cmdlet **Grant-CsdialPlan**. Este cmdlet puede ejecutarse bien desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Asignar un plan de marcado por usuario a un solo usuario

  - El siguiente comando permite asignar el plan de marcado RedmondDialPlan al usuario Ken Myer.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## Asignar un plan de marcado por usuario a varios usuarios

  - Este comando asigna el plan de marcado por usuario RedmondDialPlan a todos los usuarios que trabajen en la ciudad de Redmond. Para obtener más información sobre el parámetro LdapFilter que se utiliza en este comando, consulte la documentación del cmdlet [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser).
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## Desasignar un plan de marcado por usuario

  - Este comando desasigna cualquier plan de marcado por usuario previamente asignado a Ken Myer. Una vez desasignado el plan de marcado por usuario, Ken Myer será administrado automáticamente utilizando el plan de marcado global, su plan de marcado de sitio local (si es que existe uno) o el plan de marcado de ámbito de servicio asignado a este registrador o puerta de enlace de RTC. Los planes de marcado de ámbito de servicio tienen prioridad sobre cualquier plan de marcado de sitio local, y los planes de marcado de sitio local tienen prioridad sobre cualquier plan de marcado global.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

Para obtener más información, consulte el tema de ayuda correspondiente al cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsDialPlan).

## Vea también

#### Otros recursos

[Configurar planes de marcado en Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Cuentas de usuario habilitadas para Lync Server 2013](lync-server-2013-user-accounts-enabled-for-lync-server.md)

