---
title: "Ver el estado de los servicios en ejecución en un equipo con Lync Server 2013"
TOCTitle: "Afficher le statut des services s’exécutant sur un ordi. dans Lync Server 2013"
ms:assetid: f41918e7-4c02-431e-840a-88a1f36ae499
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182606(v=OCS.15)
ms:contentKeyID: 48277176
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ver el estado de los servicios que se están ejecutando en un equipo con Lync Server 2013

 

_**Última modificación del tema:** 2013-02-22_

Puede usar Panel de control de Lync Server 2013 para ver todos los servicios que se están ejecutando en un equipo específico de su topología de Lync Server y ver el estado de cada servicio.

## Para ver el estado de los servicios que se ejecutan en un equipo

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Topología** .

4.  En la página **Estado**, ordene o busque la lista, según el caso, para encontrar el equipo que le interesa y, a continuación, haga clic en el nombre del equipo.

5.  Siga uno de estos procedimientos:
    
      - Para ver el estado más reciente de los servicios que se ejecutan en el equipo, haga clic en **Obtener estado del servicio**.
    
      - Para ver una lista de los servicios concretos que se ejecutan en el equipo y el estado de cada servicio, haga clic en **Propiedades** y, a continuación, haga clic en **Cerrar** para volver a la lista.

## Consulta del estado de los servicios usando los cmdlets Shell de administración de Lync Server

También puede ver el estado de los servicios usando Shell de administración de Lync Server y el cmdlet **Get-CsWindowsService**. Puede ejecutar este cmdlet desde Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para ver el estado de los servicios

  - Para ver el estado de los servicios en un equipo, escriba un comando similar al siguiente en Shell de administración de Lync Server y pulse Entrar:
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    Este comando devolverá información similar a la siguiente:
    
        RoleName                                  Status
        --------                                  ------
        {W3SVC}                                   Running
        {CentralManagement}                       Running
        {ClsAgent}                                Running
        {Registrar, UserServer, EdgeServer}       Running
        {ApplicationServer}                       Running
        {ConferencingServer}                      Running
        {MediationServer}                         Running

Para obtener información detallada, consulte [Get-CsWindowsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService).

## Vea también

#### Otros recursos

[Administrar dispositivos, teléfonos y aplicaciones cliente en Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

