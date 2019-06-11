---
title: 'Lync Server 2013: Agregar sitios de sucursal a la topología'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 029627060ff03b804d0d2f76f40fdd4052f0d1c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a>Agregar sitios de sucursal a la topología en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-05_

Los sitios de sucursales representan sucursales físicas que están conectadas a sus oficinas principales a través de un vínculo WAN. Para agregar un sitio de sucursal a su topología de Lync, realice este procedimiento en el sitio central.

<div>

## <a name="to-add-branch-sites-to-your-topology"></a>Para agregar sitios de sucursales a su topología

1.  Haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server**y, a continuación, haga clic en **generador de topología de Lync Server**.

2.  En el árbol de consola, expanda el sitio central, haga clic con el botón secundario en **sitios de sucursales**y, a continuación, haga clic en **nuevo sitio de sucursal**.

3.  En el cuadro de diálogo **definir nuevo sitio de sucursal** , haga clic en **nombre**y, a continuación, escriba el nombre del sitio de la sucursal.

4.  Faculta Haga clic en **Descripción**y, a continuación, escriba una descripción para el sitio de la sucursal.

5.  Haga clic en **Siguiente**.

6.  Faculta En el cuadro de diálogo **definir siguiente sitio de sucursal** , realice una de las siguientes acciones:
    
      - Haga clic en **ciudad**y, a continuación, escriba el nombre de la ciudad en la que se encuentra el sitio de la sucursal.
    
      - Haga clic en **Estado o región**y, a continuación, escriba el nombre del estado o la región en la que se encuentra el sitio de la sucursal.
    
      - Haga clic en **prefijo internacional**y escriba el código de la llamada de dos dígitos para el país o la región en la que se encuentra el sitio de la sucursal.

7.  Haga clic en **siguiente**y, a continuación, siga uno de estos procedimientos:
    
      - Si está usando un equipo o servidor de sucursal con la supervivencia en este sitio, asegúrese de que la casilla **abrir el nuevo asistente superviviente cuando se cierre este asistente** esté activada, haga clic en **Finalizar**y, a continuación, siga las instrucciones del asistente que se abre. Para obtener información sobre los elementos del asistente, consulte [definir un dispositivo o servidor de sucursal con la que sea reviviente en Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).
    
      - Si no usa un equipo o servidor de sucursal con la supervivencia en este sitio, desactive la casilla **abrir el nuevo asistente superviviente cuando se cierre este asistente** y, a continuación, haga clic en **Finalizar**.

8.  Repita los pasos anteriores para cada sitio de sucursal que desee agregar a la topología.

**Siguiente paso:**

Para equipos o servidores de sucursales que sean revivientes: [defina un servidor o un dispositivo de sucursal que sea reviviente en Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

Para conectividad RTC no resistente: [defina una puerta de enlace RTC para un sitio de sucursal en Lync server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Configure un tronco con un bypass de multimedia en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md), o [Configure un tronco sin omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

