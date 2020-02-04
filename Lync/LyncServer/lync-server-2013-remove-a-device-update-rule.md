---
title: 'Lync Server 2013: quitar una regla de actualización de dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a Device Update rule
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994066(v=OCS.15)
ms:contentKeyID: 51803977
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d367c507ea2e8871231248b1f29d7d033dedbe9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-device-update-rule-in-lync-server-2013"></a>Quitar una regla de actualización de dispositivo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Al quitar una regla de actualización de dispositivo, se sacará de él permanentemente de la cola de actualizaciones de dispositivos.

Quitar una regla es diferente de desinstalar una actualización de los dispositivos de su implementación o de su dispositivo de prueba. Para desinstalar una actualización aprobada de su implementación, *restaure* la regla de actualización de dispositivos. Para obtener más información, consulte [restaurar una regla de actualización de dispositivos en Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md). Para desinstalar una actualización que no haya aprobado de sus dispositivos de prueba, puede *restablecerla* . Para obtener más información, consulte [restablecer una regla de actualización de dispositivo en Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).

Puede quitar una regla de actualización de dispositivo con el panel de control de Lync Server o Windows PowerShell.

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a>Para quitar las reglas de actualización de dispositivos mediante el panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, haga clic en el botón de navegación de **actualización de dispositivos** .

4.  En la página **actualización de dispositivo** , siga uno de estos procedimientos:
    
      - Para quitar una regla, seleccione la que quiera eliminar.
    
      - Para quitar todas las reglas, haga clic en el menú **Editar** y, a continuación, haga clic en **seleccionar todo**.

5.  Haga clic en **Editar** y después en **Eliminar**.

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a>Quitar las reglas de actualización de dispositivos mediante cmdlets de Windows PowerShell

Las reglas de actualización de dispositivos también se pueden quitar con Windows PowerShell y el cmdlet **Remove-CsDeviceUpdateRule** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a>Para quitar una regla de actualización de un solo dispositivo de un servidor

  - El siguiente comando quita la regla de actualización de dispositivo d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 del servidor Web en atl-cs-001.litwareinc.com.
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a>Para quitar todas las reglas de actualización de dispositivos de un servidor

  - Este comando quita todas las reglas de actualización de dispositivos del servidor Web en atl-cs-001.litwareinc.com.
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

Para obtener más información, vea el tema de ayuda sobre el cmdlet [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) .

</div>

<div>

## <a name="see-also"></a>Vea también


[Aprobar una regla de actualización de dispositivo en Lync Server 2013](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

