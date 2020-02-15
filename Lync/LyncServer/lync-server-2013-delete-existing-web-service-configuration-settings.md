---
title: 'Lync Server 2013: eliminar las opciones de configuración de un servicio web existente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete existing Web Service configuration settings
ms:assetid: c2b96f4c-4b07-48e6-9ca6-55bc0e0cf5a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182582(v=OCS.15)
ms:contentKeyID: 48185333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f54a83dc52a8dcdacd07c7d4464f46155d1860a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-existing-web-service-configuration-settings-in-lync-server-2013"></a>Eliminación de las opciones de configuración de un servicio web existente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Siga estos pasos para eliminar las opciones de configuración del servicio Web.

<div>

## <a name="to-delete-web-service-configuration-settings"></a>Para eliminar las opciones de configuración de un servicio Web

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Servicio web**.

4.  En la página **servicio Web** , en el campo de búsqueda, escriba todo o parte del nombre de la Directiva que desea eliminar.

5.  En la lista de directivas, seleccione la directiva que desee, haga clic en **Editar** y, a continuación, en **Eliminar**.

6.  Haga clic en **Aceptar**.

</div>

<div>

## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>Eliminación de opciones de configuración del servicio Web mediante cmdlets de Windows PowerShell

Puede eliminar las opciones de configuración del servicio Web con Windows PowerShell y el cmdlet **Remove-CsWebServiceConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>Para eliminar una colección específica de opciones de configuración de un servicio Web

  - El siguiente comando quita la configuración de seguridad del servicio Web que se aplica al sitio de Redmond:
    
        Remove-CsWebServiceConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>Para eliminar todas las opciones de configuración de los servicios web que se aplican al ámbito del sitio

  - El siguiente comando quita todas las configuraciones de seguridad del servicio Web que se aplican al ámbito de servicio:
    
        Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>Para eliminar todas las opciones de configuración de los servicios web que permiten la autenticación de certificados

  - El siguiente comando quita toda la configuración de seguridad del servicio Web que permite el uso de la autenticación de certificados:
    
        Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration

</div>

Para obtener más información, consulte [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration).

</div>

<div>

## <a name="see-also"></a>Vea también


[Configuración de la autenticación en el panel de control de Lync Server 2013](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

