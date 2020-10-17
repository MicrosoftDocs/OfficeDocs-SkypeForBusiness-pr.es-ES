---
title: 'Lync Server 2013: agregar sitios de sucursal a la topología'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fec919491872df8dc2ab0f843be84d4d0de1c280
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521577"
---
# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a>Agregar sitios de sucursal a la topología en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-05_

Los sitios de sucursal representan las sucursales físicas que están conectadas a las oficinas principales a través de un vínculo WAN. Para agregar un sitio de sucursal a la topología de Lync, realice este procedimiento en el sitio central.

<div>

## <a name="to-add-branch-sites-to-your-topology"></a>Para agregar sitios de sucursal a la topología

1.  Haga clic sucesivamente en **Inicio**, **Todos los programas**, **Microsoft Lync Server** y **Lync Server Topology Builder**.

2.  En el árbol de la consola, expanda el sitio central, haga clic con el botón secundario en **sitios de sucursal**y, a continuación, haga clic en **nuevo sitio de sucursal**.

3.  En el cuadro de diálogo **Definir nuevo sitio de sucursal**, haga clic en **Nombre ** y escriba el nombre del sitio de sucursal.

4.  (Opcional) Haga clic en **Descripción ** y escriba una descripción significativa para el sitio de sucursal.

5.  Haga clic en **Siguiente**.

6.  (Opcional) En el siguiente cuadro de diálogo **Definir nuevo sitio de sucursal**, realice una de las siguientes acciones:
    
      - Haga clic en **Ciudad** y escriba el nombre de la ciudad en la se ubica el sitio de sucursal.
    
      - Haga clic en **Provincia o región** y escriba el nombre de la provincia o la región en la que se ubica el sitio de sucursal.
    
      - Haga clic en **código de país** y escriba el código telefónico de dos dígitos del país o la región en el que se ubica el sitio de sucursal.

7.  Haga clic en **Siguiente** y, a continuación, siga uno de estos procedimientos:
    
      - Si está usando una aplicación o un servidor de sucursal con funciones de supervivencia en este sitio, asegúrese de que la casilla **abrir el nuevo asistente superviviente cuando se cierre este asistente** esté activada, haga clic en **Finalizar**y, a continuación, siga las instrucciones del asistente que se abre. Para obtener información sobre los elementos del asistente, consulte [definir una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).
    
      - Si no usa una aplicación o un servidor de sucursal con funciones de supervivencia en este sitio, desactive la casilla **Abrir el Asistente con nuevas funciones de supervivencia cuando se cierre este asistente** y haga clic en **Finalizar**.

8.  Repita los pasos anteriores para cada sitio de sucursal que desee agregar a la topología.

**Siguiente paso:**

Para las aplicaciones o servidores de sucursal con funciones de supervivencia: [definir una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

Para la conectividad con RTC no resistente: [defina una puerta de enlace RTC para un sitio de sucursal en Lync server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Configure un tronco con omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)o [Configure un tronco sin omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

