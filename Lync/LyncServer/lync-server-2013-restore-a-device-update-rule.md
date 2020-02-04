---
title: 'Lync Server 2013: restaurar una regla de actualización de dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restore a Device Update rule
ms:assetid: ac490baf-c7a0-48d9-8fd0-ba5729489341
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994061(v=OCS.15)
ms:contentKeyID: 51803972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0416092c7021d599ec7e516d72c19e8baa3c598
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restore-a-device-update-rule-in-lync-server-2013"></a>Restaurar una regla de actualización de dispositivo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Para desinstalar una regla de actualización de dispositivo de los dispositivos de su implementación, restáurela. Si restaura una regla de actualización de dispositivo, se desinstalará la actualización y se reinstalará la versión anterior de la regla.

Puede restaurar una regla de actualización de dispositivo con el panel de control de Lync Server o Windows PowerShell.

<div>

## <a name="to-restore-device-update-rules-by-using-lync-server-control-panel"></a>Para restaurar las reglas de actualización de dispositivos mediante el panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, haga clic en el botón de navegación de **actualización de dispositivos** .

4.  En la página **actualización de dispositivo** , siga uno de estos procedimientos:
    
      - Para restaurar una regla, seleccione esa regla.
    
      - Para restaurar todas las reglas, haga clic en **Editar**y, a continuación, haga clic en **seleccionar todo**.

5.  Haga clic en el menú **acción** y, a continuación, haga clic en **restaurar**.

</div>

<div>

## <a name="restoring-device-update-rules-by-using-windows-powershell-cmdlets"></a>Restauración de reglas de actualización de dispositivos mediante cmdlets de Windows PowerShell

Las reglas de actualizaciones de dispositivos también se pueden restaurar mediante Windows PowerShell y el cmdlet **restore-CsDeviceUpdateRule** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.

<div>


> [!NOTE]  
> Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 mediante PowerShell remoto" en.



</div>

<div>

## <a name="to-restore-a-single-device-update-rule-on-a-server"></a>Para restaurar una regla de actualización de un solo dispositivo en un servidor

  - El siguiente comando restaura la regla de actualización de dispositivo d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 en el servidor Web atl-cs-001.litwareinc.com:
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-restore-all-the-device-update-rules-on-a-server"></a>Para restaurar todas las reglas de actualización de dispositivos en un servidor

  - Este comando restaura todas las reglas de actualización de dispositivos en el servidor Web atl-cs-001.litwareinc.com:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

</div>

Para obtener más información, consulte el tema de ayuda para el cmdlet [restore-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

