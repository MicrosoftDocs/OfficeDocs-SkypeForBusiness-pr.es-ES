---
title: Habilitar el Registro de detalles de llamadas
TOCTitle: Habilitar el Registro de detalles de llamadas
ms:assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg520980(v=OCS.15)
ms:contentKeyID: 48274986
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar el Registro de detalles de llamadas

 

_**Última modificación del tema:** 2013-02-23_

El registro detallado de llamadas (CDR) registra la información de uso y diagnóstico sobre actividades punto a punto, incluida la mensajería instantánea, llamadas de voz sobre IP (VoIP), uso compartido de aplicaciones, transferencia de archivos y reuniones. Los datos de uso pueden servir para calcular el retorno de la inversión y los datos de diagnóstico se pueden usar para solucionar problemas de actividades punto a punto y reuniones.

Use el procedimiento siguiente para habilitar el registro detallado de llamadas (CDR) en toda la organización o en cada sitio de la organización.


> [!NOTE]
> Para poder habilitar el CDR debe configurar la supervisión y una base de datos de supervisión. Para obtener más información, consulte <A href="lync-server-2013-deploying-monitoring.md">Implementación de supervisión en Lync Server 2013</A>.



## Habilitar CDR utilizando Panel de control de Lync Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o se asigne al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, en **Registro detallado de llamadas**.

4.  En la página **Registro detallado de llamadas**, haga clic en el sitio apropiado de la lista, seleccione **Acción** y, a continuación, haga clic en **Habilitar CDR**.
    

    > [!NOTE]
    > CDR habilitado de forma predeterminada.



## Habilitar CDR utilizando los cmdlets Shell de administración de Lync Server

También puede habilitar CDR utilizando Windows PowerShell y el cmdlet **Set-CsCdrConfiguration**. Este cmdlet puede ejecutarse ya sea desde el Shell de administración de Lync Server 2013 o bien desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para habilitar CDR para una única ubicación

  - Para deshabilitar CDR, establezca el parámetro EnableCDR en True ($True).
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True

## Para deshabilitar CDR para una única ubicación

  - Para deshabilitar CDR, establezca el parámetro EnableCDR en False ($False). Esto no desinstala la supervisión; pausa la recopilación y el almacenamiento de datos de CDR.
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

## Utilizar un único comando para habilitar CDR en varias ubicaciones

  - Este comando habilita CDR para todos los parámetros de CDR que se encuentran actualmente en uso en su organización.
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True

Para obtener más información, consulte el tema de ayuda del cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCdrConfiguration).

## Vea también

#### Otros recursos

[Planeamiento de la supervisión en Lync Server 2013](lync-server-2013-planning-for-monitoring.md)  
[Implementación de supervisión en Lync Server 2013](lync-server-2013-deploying-monitoring.md)

