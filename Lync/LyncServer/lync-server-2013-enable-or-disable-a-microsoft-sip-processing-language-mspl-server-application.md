---
title: 'Lync Server 2013: habilitar o deshabilitar una aplicación de servidor de Microsoft SIP Processing language (MSPL)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable a Microsoft SIP Processing Language (MSPL) server application
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182573(v=OCS.15)
ms:contentKeyID: 48185145
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da7ff3379f0e32166ceb263e1dbda46117b6984a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a>Habilitar o deshabilitar una aplicación de servidor de Microsoft SIP Processing language (MSPL) en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Puede usar el panel de control de Lync Server para habilitar o deshabilitar aplicaciones de servidor de Microsoft SIP Processing language (MSPL) que se ejecutan en su entorno de Lync Server 2013. Estas aplicaciones solo son aplicaciones de script que usan un lenguaje de scripting en lugar de la API de Microsoft Lync 2013 Preview.

No todos los scripts se pueden habilitar o deshabilitar. Por ejemplo, el script DefaultRouting está habilitado y esta opción no se puede cambiar para DefaultRouting.

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a>Para habilitar o deshabilitar una aplicación de servidor MSPL

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **topología** y después haga clic en **aplicación de servidor**.

4.  En la página de la **aplicación servidor** , haga clic en un encabezado de columna para ordenar las aplicaciones, si es necesario, y, a continuación, haga clic en la aplicación de servidor que desea modificar.

5.  Haga clic en **acción**.

6.  Haga clic en **Habilitar aplicación** o deshabilitar **aplicación** (es decir, si el script admite esta opción).

</div>

<div>

## <a name="see-also"></a>Vea también


[Marcar una aplicación de Microsoft SIP Processing language (MSPL) como crítica o incrítica en Lync Server 2013](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[Ver las aplicaciones de servidor del lenguaje de procesamiento de SIP de Microsoft (MSPL) de Lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[Administración de la topología de Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

