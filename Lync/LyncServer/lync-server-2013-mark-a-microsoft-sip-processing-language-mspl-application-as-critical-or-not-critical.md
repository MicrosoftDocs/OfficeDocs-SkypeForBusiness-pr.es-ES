---
title: 'Lync Server 2013: marcar una aplicación de lenguaje de procesamiento de SIP de Microsoft (MSPL) como crítica o no crítica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a50dea89feb7e72c5076e58a38136d24b1b34499
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045422"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a>Marcar una aplicación de lenguaje de procesamiento de SIP de Microsoft (MSPL) como crítica o no crítica en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Las aplicaciones de servidor de lenguaje de procesamiento de SIP de Microsoft (MSPL) son aplicaciones de solo script que usan el lenguaje de scripting MSPL en lugar de la API 2010 de Microsoft Lync. Algunas aplicaciones de servidor MSPL se especifican como críticas. Si un script es crítico, el script debe iniciarse durante el inicio del sistema para poder iniciar Lync Server 2013. Si se produce un error en el script mientras Lync Server se está ejecutando, el servidor no se apaga, pero deja de enviar tráfico al script y escribe errores en el registro de eventos.

Puede usar el panel de control de Lync Server para marcar las aplicaciones de servidor del lenguaje de procesamiento de SIP de Microsoft (MSPL) como críticas o desmarcarlas.

No todos los scripts admiten esta opción. Por ejemplo, el script DefaultRouting está marcado como crítico y esta opción no se puede cambiar para DefaultRouting.

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a>Para marcar o desmarcar una aplicación de servidor de MSPL como crítica

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Topología** y, a continuación, en **Aplicación de servidor**.

4.  En la página **Aplicación de servidor**, haga clic en un encabezado de columna para ordenar las aplicaciones, si fuera necesario, y, a continuación, haga clic en la aplicación de servidor que desee modificar.

5.  Haga clic en **Acción**.

6.  Haga clic en **marcar como crítico** o **anular selección como crítico** (es decir, si el script admite esta opción).

</div>

<div>

## <a name="see-also"></a>Vea también


[Habilitar o deshabilitar una aplicación de servidor de lenguaje de procesamiento de SIP de Microsoft (MSPL) en Lync Server 2013](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[Ver aplicaciones de servidor del lenguaje de procesamiento de SIP de Microsoft (MSPL) en Lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[Administración de la topología de Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

