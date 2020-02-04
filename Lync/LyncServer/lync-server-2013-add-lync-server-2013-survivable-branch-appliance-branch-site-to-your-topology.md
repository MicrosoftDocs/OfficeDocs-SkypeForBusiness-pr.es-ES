---
title: Agregar un sitio de sucursal de aplicación de sucursal con función de supervivencia de Lync Server 2013 a la topología
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
ms.openlocfilehash: b4fc2dd7426006d0c8f19b38b85ba778744fff2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a>Agregar un sitio de sucursal de aplicación de sucursal con función de supervivencia de Lync Server 2013 a la topología

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-07_

Los equipos de la sucursal de Microsoft Lync Server 2013 (SBA) no se pueden asociar a un grupo front-end de Microsoft Lync Server 2010 como registrador de copias de seguridad. SBA debe estar asociado a un grupo front end de Microsoft Lync Server 2013. En estos pasos se supone que se 2013 SBA de Microsoft Lync Server. Realice este procedimiento en el sitio central.

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a>Para agregar sitios de sucursales con Microsoft Lync Server 2013 SBA a su topología

1.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.

2.  En el árbol de consola, expanda el sitio central, expanda **sitios de sucursal**y, a continuación, haga clic en **nuevo sitio de sucursal**.

3.  En el cuadro de diálogo **definir nuevo sitio de sucursal** , haga clic en **nombre**y, a continuación, escriba un nombre para el nuevo sitio de la sucursal.

4.  Faculta Haga clic en **Descripción**y, a continuación, escriba una descripción para el sitio de la sucursal.

5.  Haga clic en **Siguiente**.

6.  Faculta En el cuadro de diálogo **definir siguiente sitio de sucursal** , realice una de las siguientes acciones:
    
      - Haga clic en **ciudad**y, a continuación, escriba el nombre de la ciudad en la que se encuentra el sitio de la sucursal.
    
      - Haga clic en **Estado o región**y, a continuación, escriba el nombre del estado o la región en la que se encuentra el sitio de la sucursal.
    
      - Haga clic en **prefijo internacional**y escriba el código de la llamada de dos dígitos para el país o la región en la que se encuentra el sitio de la sucursal.

7.  Haga clic en **siguiente**y, a continuación, siga uno de estos procedimientos:
    
      - Si está usando una aplicación de sucursal o un servidor de sucursal con la supervivencia, asegúrese de que esté activada la casilla **abrir el nuevo asistente superviviente cuando se cierre este asistente** .
    
      - Si no usa una aplicación de sucursal o un servidor de sucursal que sea revivientes en este sitio, desactive la casilla **abrir el nuevo asistente superviviente cuando se cierre este asistente** .
    
      - Haga clic en **Finalizar**y, a continuación, siga las instrucciones del asistente que se abre. Para obtener información sobre los elementos del asistente, consulte [definir un dispositivo o servidor de sucursal con la que sea reviviente en Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).

8.  Repita los pasos anteriores para cada sitio de sucursal que desee agregar a la topología.

</div>

<div>

## <a name="see-also"></a>Vea también


[Definir un servidor o aplicación de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[Definir una puerta de enlace RTC para un sitio de sucursal en Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configurar un tronco sin omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

