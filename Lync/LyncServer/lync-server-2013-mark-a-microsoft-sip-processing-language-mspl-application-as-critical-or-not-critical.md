---
title: 'Lync Server 2013: marcar una aplicación de lenguaje de procesamiento SIP de Microsoft (MSPL) como crítica o no crítica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 419a162e355434972216f0c47d79850af28cd244
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a>Marcar una aplicación de Microsoft SIP Processing language (MSPL) como crítica o incrítica en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Las aplicaciones de servidor de Microsoft SIP Processing language (MSPL) son aplicaciones de solo script que usan el lenguaje de scripts MSPL en lugar de la API 2010 de Microsoft Lync. Algunas aplicaciones de servidor MSPL se especifican como críticas. Si una secuencia de comandos es crítica, la secuencia de comandos debe iniciarse durante el inicio del sistema para que Lync Server 2013 se inicie. Si se produce un error en la secuencia de comandos mientras Lync Server se está ejecutando, el servidor no se cierra, pero deja de enviar tráfico al script y escribe los errores en el registro de eventos.

Puede usar el panel de control de Lync Server para marcar las aplicaciones de servidor de Microsoft SIP Processing language (MSPL) como críticas o desmarcarlas.

No todos los scripts admiten esta opción. Por ejemplo, el script DefaultRouting se marca como crítico, y esta opción no se puede cambiar para DefaultRouting.

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a>Para marcar o desmarcar una aplicación de servidor de MSPL como crítica

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **topología** y después haga clic en **aplicación de servidor**.

4.  En la página de la **aplicación servidor** , haga clic en un encabezado de columna para ordenar las aplicaciones, si es necesario, y, a continuación, haga clic en la aplicación de servidor que desea modificar.

5.  Haga clic en **acción**.

6.  Haga clic en **marcar como crítico** o deseleccionar **como crítico** (es decir, si el script admite esta opción).

</div>

<div>

## <a name="see-also"></a>Vea también


[Habilitar o deshabilitar una aplicación de servidor de Microsoft SIP Processing language (MSPL) en Lync Server 2013](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[Ver las aplicaciones de servidor del lenguaje de procesamiento de SIP de Microsoft (MSPL) de Lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[Administración de la topología de Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

