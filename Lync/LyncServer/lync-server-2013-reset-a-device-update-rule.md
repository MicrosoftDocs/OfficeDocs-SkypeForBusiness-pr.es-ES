---
title: 'Lync Server 2013: restablecer una regla de actualización de dispositivos'
description: 'Lync Server 2013: restablecer una regla de actualización de dispositivos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset a Device Update rule
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994069(v=OCS.15)
ms:contentKeyID: 51803980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a4d42b6aee8f4cb3fd93839b4a8575059ba71cb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577846"
---
# <a name="reset-a-device-update-rule-in-lync-server-2013"></a>Restablecer una regla de actualización de dispositivos en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Si no le gusta la forma en que una actualización funciona en sus dispositivos de prueba, puede restablecer la regla de actualización de dispositivos, que elimina el estado pendiente de la regla y desinstala la actualización de los dispositivos de prueba.

Puede quitar una regla de actualización de dispositivos mediante el panel de control de Lync Server o Windows PowerShell.

<div>


> [!NOTE]  
> Para desinstalar una regla que ya haya aprobado (es decir, que esté implementada), restáurela. Para obtener más información, consulte <A href="lync-server-2013-restore-a-device-update-rule.md">restaurar una regla de actualización de dispositivos en Lync Server 2013</A>.



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a>Para restablecer una regla de actualización de dispositivos mediante el panel de control de Lync Server

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, en el botón de navegación **actualización de dispositivos** .

4.  En la página **actualización de dispositivo** , realice una de las siguientes acciones:
    
      - Para restablecer una regla, seleccione la regla que desea restablecer.
    
      - Para restablecer todas las reglas, en el menú **edición** , haga clic en **seleccionar todo**.
    
      - Para restablecer todas las reglas de una marca, use el menú columna de **marca** .

5.  Haga clic en **acción**y, a continuación, en **Cancelar actualizaciones pendientes**.
    
    <div>
    

    > [!TIP]  
    > Si está seguro de que nunca deseará implementar las reglas de actualización de dispositivos que ha cancelado, es posible que quiera eliminarlas. Para obtener más información, consulte <A href="lync-server-2013-remove-a-device-update-rule.md">quitar una regla de actualización de dispositivos en Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>Restablecimiento de una regla de actualización de dispositivos mediante cmdlets de Windows PowerShell

Las reglas de actualización de dispositivos también se pueden restablecer mediante Windows PowerShell y el cmdlet **RESET-CsDeviceUpdateRule** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.

<div>


> [!NOTE]  
> Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a>Para restablecer una regla de actualización de dispositivos específica en un servidor

  - El siguiente comando restablece la regla de actualización de dispositivos d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 en el servidor Web atl-cs-001.litwareinc.com:
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a>Para restablecer todas las reglas de actualización de dispositivos en un servidor

  - Este comando restablece todas las reglas de actualización de dispositivos en el servidor Web atl-cs-001.litwareinc.com:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a>Para restablecer todas las reglas de actualización de dispositivos que tienen una marca específica

  - En este ejemplo, se restablecen todas las actualizaciones de dispositivos en toda la organización que tienen una marca igual a Microsoft:
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

Para obtener más información, consulte el tema de ayuda para el cmdlet [RESET-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) .

</div>

<div>

## <a name="see-also"></a>Consulte también


[Aprobar una regla de actualización de dispositivos en Lync Server 2013](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

