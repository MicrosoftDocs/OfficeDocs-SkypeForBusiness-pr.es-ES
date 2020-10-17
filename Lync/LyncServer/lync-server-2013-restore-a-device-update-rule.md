---
title: 'Lync Server 2013: restaurar una regla de actualización de dispositivos'
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
ms.openlocfilehash: 20c6b6084577979264648e706c70fb6387b47971
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511637"
---
# <a name="restore-a-device-update-rule-in-lync-server-2013"></a>Restaurar una regla de actualización de dispositivos en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Para desinstalar una regla de actualización de dispositivos de los dispositivos de su implementación, restáurela. La restauración de una regla de actualización de dispositivos desinstala la actualización y reinstala la versión anterior de dicha regla.

Puede restaurar una regla de actualización de dispositivos con el panel de control de Lync Server o Windows PowerShell.

<div>

## <a name="to-restore-device-update-rules-by-using-lync-server-control-panel"></a>Para restaurar reglas de actualización de dispositivos mediante el panel de control de Lync Server

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, en el botón de navegación **actualización de dispositivos** .

4.  En la página **actualización de dispositivo** , realice una de las siguientes acciones:
    
      - Para restaurar una regla, seleccione esa regla.
    
      - Para restaurar todas las reglas, haga clic en **Editar**y, a continuación, haga clic en **seleccionar todo**.

5.  Haga clic en el menú **acción** y, a continuación, en **restaurar**.

</div>

<div>

## <a name="restoring-device-update-rules-by-using-windows-powershell-cmdlets"></a>Restauración de reglas de actualización de dispositivos mediante cmdlets de Windows PowerShell

Las reglas de actualización de dispositivos también se pueden restaurar mediante Windows PowerShell y el cmdlet **restore-CsDeviceUpdateRule** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.

<div>


> [!NOTE]  
> Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .



</div>

<div>

## <a name="to-restore-a-single-device-update-rule-on-a-server"></a>Para restaurar una única regla de actualización de dispositivos en un servidor

  - El siguiente comando restaura la regla de actualización de dispositivos d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 en el servidor Web atl-cs-001.litwareinc.com:
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-restore-all-the-device-update-rules-on-a-server"></a>Para restaurar todas las reglas de actualización de dispositivos en un servidor

  - Este comando restaura todas las reglas de actualización de dispositivos en el servidor Web atl-cs-001.litwareinc.com:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

</div>

Para obtener más información, consulte el tema de ayuda del cmdlet [restore-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

