---
title: Agregar un sitio de sucursal de aplicación de sucursal con funciones de supervivencia de Lync Server 2013 a la topología
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e57a7b062cd95012102ba30a527c99c2fba71d6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a>Agregar un sitio de sucursal de aplicación de sucursal con funciones de supervivencia de Lync Server 2013 a la topología

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-07_

Microsoft Lync Server 2013 las aplicaciones de sucursal con funciones de supervivencia (SBA) no se pueden asociar a un grupo de servidores front-end de Microsoft Lync Server 2010 como registrador de reserva. SBA debe estar asociado a un grupo de servidores front-end 2013 de Microsoft Lync Server. En estos pasos se presupone que es un servidor de Microsoft Lync Server 2013 SBA. Realice este procedimiento en el sitio central.

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a>Para agregar sitios de sucursal con SBA de Microsoft Lync Server 2013 a su topología

1.  Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.

2.  En el árbol de consola, expanda sucesivamente el sitio central y los **Sitios de sucursal** y luego haga clic en **Nuevo sitio de sucursal**.

3.  En el cuadro de diálogo **Definir nuevo sitio de sucursal**, haga clic en **Nombre** y escriba un nombre para el sitio de sucursal nuevo.

4.  (Opcional) Haga clic en **Descripción** y escriba una descripción significativa para el sitio de sucursal.

5.  Haga clic en **Siguiente**.

6.  (Opcional) En el siguiente cuadro de diálogo **Definir nuevo sitio de sucursal**, realice una de las siguientes acciones:
    
      - Haga clic en **Ciudad** y escriba el nombre de la ciudad en la se ubica el sitio de sucursal.
    
      - Haga clic en **Provincia o región** y escriba el nombre de la provincia o la región en la que se ubica el sitio de sucursal.
    
      - Haga clic en **código de país** y escriba el código telefónico de dos dígitos del país o la región en el que se ubica el sitio de sucursal.

7.  Haga clic en **Siguiente** y, a continuación, siga uno de estos procedimientos:
    
      - Si está usando una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia en este sitio, asegúrese de que esté activada la casilla **abrir el nuevo asistente superviviente cuando se cierre este asistente** .
    
      - Si no está usando una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia en este sitio, desactive la casilla **abrir el nuevo asistente superviviente cuando se cierre este asistente** .
    
      - Haga clic en **Finalizar** y siga las instrucciones del asistente que se abre. Para obtener información sobre los elementos del asistente, consulte [definir una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).

8.  Repita los pasos anteriores para cada sitio de sucursal que desee agregar a la topología.

</div>

<div>

## <a name="see-also"></a>Vea también


[Definir una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[Definir una puerta de enlace RTC para un sitio de sucursal en Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[Configurar un tronco con la omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configurar un tronco sin omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

