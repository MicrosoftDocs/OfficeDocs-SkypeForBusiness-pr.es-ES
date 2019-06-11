---
title: 'Lync Server 2013: Ver las opciones de configuración de la actualización de dispositivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View Device Update configuration settings
ms:assetid: aa6a70a9-bd77-4606-b797-ea6a3bab9cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994059(v=OCS.15)
ms:contentKeyID: 51803970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4c334e44212116418a953b2bbf84ece75063f8b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850114"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-device-update-configuration-settings-in-lync-server-2013"></a>Ver las opciones de configuración de la actualización de dispositivos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-20_

Puede ver las opciones de configuración del servicio de actualización de dispositivos mediante el shell de administración de Lync Server y el cmdlet **Get-CsDeviceUpdateConfiguration** , que puede ejecutar desde el shell de administración de lync Server 2013 o desde una sesión remota de Windows. PowerShell

<div>


> [!NOTE]  
> Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 mediante PowerShell remoto" en.



</div>

<div>


<div>


  - Para ver información sobre todas las rutas de voz, escriba el siguiente comando en el shell de administración de Lync Server y presione ENTRAR:
    
        Get-CsDeviceUpdateConfiguration
    
    Este comando devolverá información similar a la siguiente:
    
        Identity               : Global
        ValidLogFileTypes      : {Watson, Config, Diaglog, CELog}
        ValidLogFileExtensions : {.dmp, .clg, .clg1, .clg2...}
        MaxLogFileSize         : 1024000
        MaxLogCacheLimit       : 512000
        LogCleanUpInterval     : 10.00:00:00
        LogFlushInterval       : 00:05:00
        LogCleanUpTimeOfDay    :

</div>

Para obtener más información sobre este cmdlet, consulte el tema de ayuda en [obtener-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateConfiguration).

</div>

</div>

<span> </span>

</div>

</div>

</div>

