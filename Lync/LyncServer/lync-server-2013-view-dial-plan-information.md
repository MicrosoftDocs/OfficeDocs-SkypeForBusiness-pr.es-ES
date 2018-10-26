---
title: Ver la información del plan de marcado en Lync Server 2013
TOCTitle: Ver la información del plan de marcado en Lync Server 2013
ms:assetid: 25ed0112-a8a7-418a-8c2c-580081be692a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ687997(v=OCS.15)
ms:contentKeyID: 49888969
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ver la información del plan de marcado en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

Para ver información para un plan de marcado existente, lleve a cabo los pasos del siguiente procedimiento. Si desea crear un plan de marcado nuevo, vea [Crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

## Para ver información acerca de un plan de marcado desde Panel de control de Lync Server

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Plan de marcado** .

4.  En la página **Plan de marcado** , haga doble clic en el nombre del plan de marcado.
    

    > [!NOTE]
    > Puede ver información para un plan de marcado cada vez.



## Ver planes de marcado mediante cmdlets Windows PowerShell

  - Los planes de marcado también se pueden ver mediante el Interfaz de la línea de comandos Windows PowerShell y el cmdlet **Get-CsDialPlan**. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde la sesión de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).
    
    Para ver información acerca de todos los planes de marcado, escriba el siguiente comando en el Shell de administración de Lync Server y, a continuación, presiones ENTRAR:
    
        Get-CsDialPlan
    
    Ese comando devolverá información similar a la siguiente:
    
        Identity                 : Global
        Description              :
        DialinConferencingRegion :
        NormalizationRules       : {Description=;
                                   Pattern=^(\d+)$;Translation=$1;Name=
                                   KeepAll;IsInternalExtension=False}
        CountryCode              :
        State                    :
        City                     :
        ExternalAccessPrefix     :
        SimpleName               : DefaultProfile
        OptimizeDeviceDialing    : False

## Vea también

#### Tareas

[Crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)

