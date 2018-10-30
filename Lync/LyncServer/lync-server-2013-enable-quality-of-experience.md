---
title: Habilitar calidad de la experiencia
TOCTitle: Habilitar calidad de la experiencia
ms:assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182583(v=OCS.15)
ms:contentKeyID: 48276648
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar calidad de la experiencia

 

_**Última modificación del tema:** 2013-02-23_

La calidad de la experiencia (QoE) registra datos numéricos que indican la calidad de los medios e información sobre los participantes, nombres de los dispositivos, controladores, direcciones IP y tipos de extremos que se usan en las llamadas y las sesiones. Para más información, consulte [Planeamiento de la supervisión en Lync Server 2013](lync-server-2013-planning-for-monitoring.md) en la documentación de planeación.

Para habilitar QoE en toda la organización o en cada uno de sus sitios, realice el procedimiento siguiente.


> [!NOTE]
> Para habilitar QoE, en primer lugar debe instalar el Servidor de supervisión y conectarlo a una base de datos back-end de supervisión. Para más información, consulte <A href="lync-server-2013-deploying-monitoring.md">Implementación de supervisión en Lync Server 2013</A>.



## Para habilitar QoE con Panel de control de Lync Server:

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o se asigne al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y en **Datos de calidad de la experiencia**.

4.  En la página **Datos de calidad de la experiencia**, haga clic en la colección adecuada de la tabla, en **Acción** y en **Habilitar QoE**.

## Habilitar QoE mediante cmdlets de Windows PowerShell

Puede habilitar QoE con Windows PowerShell y el cmdlet **Set-CsQoEConfiguration**. Ejecute este cmdlet desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para habilitar QoE para una sola ubicación:

  - Para habilitar QoE, defina el parámetro EnableQoE en True ($True).
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

## Para deshabilitar QoE para una ubicación única:

  - Para deshabilitar QoE, establezca el parámetro EnableQoE en False ($False). Así no se desinstala la supervisión. Se detiene la recopilación y el almacenaje de los datos de QoE.
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

## Para habilitar QoE en varias ubicaciones con un comando único:

  - Este comando habilita QoE para todos los valores de configuración de QoE que se usan actualmente en la organización.
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

Para más información, consulte [Set-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsQoEConfiguration).

## Vea también

#### Otros recursos

[Planeamiento de la supervisión en Lync Server 2013](lync-server-2013-planning-for-monitoring.md)  
[Implementación de supervisión en Lync Server 2013](lync-server-2013-deploying-monitoring.md)

