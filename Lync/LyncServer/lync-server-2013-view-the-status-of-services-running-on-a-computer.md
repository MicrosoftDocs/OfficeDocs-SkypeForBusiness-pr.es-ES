---
title: 'Lync Server 2013: ver el estado de los servicios que se ejecutan en un equipo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View the status of services running on a computer
ms:assetid: f41918e7-4c02-431e-840a-88a1f36ae499
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182606(v=OCS.15)
ms:contentKeyID: 48185804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52f7b1628f9e9fcd99eea84ebda2cbfe934fc7d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850092"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-the-status-of-services-running-on-a-computer-in-lync-server-2013"></a>Ver el estado de los servicios que se ejecutan en un equipo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

Puede usar el panel de control de Lync Server 2013 para ver todos los servicios que se están ejecutando en un equipo específico de su topología de Lync Server y ver el estado de cada servicio.

<div>

## <a name="to-view-the-status-of-services-running-on-a-computer"></a>Para ver el estado de los servicios que se ejecutan en un equipo

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **topología**.

4.  En la página **Estado** , ordene o busque la lista, según sea necesario, para buscar el equipo que le interesa y, a continuación, haga clic en el nombre del equipo.

5.  Siga uno de estos pasos:
    
      - Para ver el estado más reciente de los servicios que se ejecutan en el equipo, haga clic en **obtener estado del servicio**.
    
      - Para ver una lista de los servicios específicos que se ejecutan en el equipo y el estado de cada servicio, haga clic en **propiedades**y, a continuación, haga clic en **cerrar** para volver a la lista.

</div>

<div>

## <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>Ver el estado del servicio con cmdlets de Windows PowerShell

También puede ver el estado del servicio con Windows PowerShell y el cmdlet **Get-CsWindowsService** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-view-service-status"></a>Para ver el estado del servicio

  - Para ver el estado del servicio en un equipo, escriba un comando similar al siguiente en el shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
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

</div>

Para obtener más información, vea [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).

</div>

<div>

## <a name="see-also"></a>Vea también


[Administrar dispositivos, teléfonos y aplicaciones cliente en Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

