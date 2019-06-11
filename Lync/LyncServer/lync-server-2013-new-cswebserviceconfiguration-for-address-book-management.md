---
title: 'Lync Server 2013: nuevo-CsWebServiceConfiguration para la administración de libretas de direcciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New-CsWebServiceConfiguration for Address Book management
ms:assetid: 49e4ecc5-aa3e-4dd4-a32c-b0dea3758fab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429703(v=OCS.15)
ms:contentKeyID: 48184067
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03a973ca1086a9d2ca1ce2d8f19bbb64ba8aae19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a>Nuevo: CsWebServiceConfiguration para la administración de libretas de direcciones en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

¿Quién puede ejecutar este cmdlet? de forma predeterminada, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet New-CsWebServiceConfiguration de forma local: RTCUniversalServerAdmins. Para devolver una lista de todas las funciones de control de acceso basado en roles (RBAC) a las que se ha asignado este cmdlet (incluidos los roles RBAC que haya creado usted mismo), ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsWebServiceConfiguration"}

El cmdlet New-CsWebServiceConfiguration define una nueva configuración para los servicios Web de su organización. El ámbito de la configuración de los servicios web solo puede encontrarse en el nivel de sitio o de servicio. No puede crear una nueva configuración de servicios web en el nivel global. Específicamente de interés para la libreta de direcciones es el atributo EnableGroupExansion. Si se establece en true, los servicios Web pueden responder a las solicitudes de expansión de grupo.

Por ejemplo:

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

<div>

## <a name="see-also"></a>Vea también


[New-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

