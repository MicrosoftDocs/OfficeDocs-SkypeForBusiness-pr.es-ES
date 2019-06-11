---
title: 'Lync Server 2013: aprobar una regla de actualización de dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Approve a Device Update rule
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994053(v=OCS.15)
ms:contentKeyID: 51803964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa560be6b8c341310c4831277902dab6f2e5552c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="approve-a-device-update-rule-in-lync-server-2013"></a>Aprobar una regla de actualización de dispositivo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Después de importar una regla de actualización de dispositivo, se instala en los dispositivos de prueba. Si las pruebas se realizan correctamente y desea implementar la actualización a su organización, puede aprobarla mediante el panel de control de Lync Server o Windows PowerShell.

<div>

## <a name="to-approve-a-device-update-rule-by-using-lync-server-control-panel"></a>Para aprobar una regla de actualización de dispositivo con el panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la página **actualización de dispositivo** , siga uno de estos procedimientos:
    
      - Para aprobar una regla, selecciónela.
    
      - Para aprobar todas las reglas, haga clic en **Editar**y, a continuación, haga clic en **seleccionar todo**.

4.  Haga clic en **acción**y, a continuación, en **aprobar**.

</div>

<div>

## <a name="approving-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>Aprobar una regla de actualización de dispositivo mediante cmdlets de Windows PowerShell

Las reglas de actualización de dispositivos también pueden aprobarse con Windows PowerShell y el cmdlet approven **-CsDeviceUpdateRule** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.

<div>


> [!NOTE]  
> Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 mediante PowerShell remoto" en.



</div>

<div>

## <a name="to-approve-a-single-device-update-rule"></a>Para aprobar una regla de actualización de un único dispositivo

  - El siguiente comando aprueba la regla de actualización de dispositivo d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 se encuentra en el servidor Web atl-cs-001.litwareinc.com:
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

</div>

<div>

## <a name="to-approve-multiple-device-update-rules"></a>Para aprobar varias reglas de actualización de dispositivos

  - Este comando aprueba todas las reglas de actualización de dispositivos para los dispositivos marcados por Microsoft:
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

</div>

Para obtener más información, vea el tema de ayuda para el cmdlet approven [-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) .

</div>

<div>

## <a name="see-also"></a>Vea también


[Importar reglas de actualización de dispositivos en Lync Server 2013](lync-server-2013-import-device-update-rules.md)  
[Restaurar una regla de actualización de dispositivo en Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

