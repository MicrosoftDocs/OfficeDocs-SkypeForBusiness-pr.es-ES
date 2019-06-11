---
title: 'Lync Server 2013: eliminar la configuración de registro existente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete existing Registrar configuration settings
ms:assetid: ae43cd75-cae4-4f78-b037-779a2cdb583b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182571(v=OCS.15)
ms:contentKeyID: 48185132
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9fe0ee46ff823a5184ee79f3b06bb02bb68115d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-existing-registrar-configuration-settings-in-lync-server-2013"></a>Eliminar las opciones de configuración de registrador existentes en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Siga estos pasos para eliminar un registrador.

<div>

## <a name="to-delete-registrar-configuration-settings"></a>Para eliminar las opciones de configuración del registrador

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Registrador**.

4.  En la página **Registrador**, en el campo de búsqueda, escriba el nombre completo o parcial del registrador que desea eliminar.

5.  En la lista, haga clic en el registrador que desee, haga clic en **Editar** y luego en **Eliminar**.

6.  Haga clic en **Aceptar**.

</div>

<div>

## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>Quitar opciones de configuración de registrar mediante cmdlets de Windows PowerShell

Puede eliminar la configuración del registrador con Windows PowerShell y el cmdlet **Remove-CsProxyConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>Para quitar un conjunto específico de opciones de configuración de seguridad del registrador

  - El siguiente comando quita las opciones de configuración de seguridad del registrador aplicadas al servidor perimetral atl-edge-011.litwareinc.com:
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>Para quitar todas las opciones de configuración de seguridad del registrador aplicadas al ámbito de sitio

  - El siguiente comando quita todas las opciones de configuración de seguridad del registrador aplicadas al servicio del registrador:
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>Para quitar todas las opciones de configuración de seguridad del registrador que permiten la autenticación NTLM

  - El siguiente comando elimina todas las opciones de configuración de seguridad del registrador que permiten el uso de NTLM para la autenticación de cliente:
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

</div>

Para obtener más información, consulte [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration).

</div>

</div>

<span> </span>

</div>

</div>

</div>

