---
title: 'Lync Server 2013: ver una lista de aplicaciones de confianza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View a list of trusted applications
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182604(v=OCS.15)
ms:contentKeyID: 48185844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 866286215389b0e446392bffe3e33f56a767f2e6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a>Ver una lista de aplicaciones de confianza en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Puede usar el panel de control de Lync Server 2013 para ver una lista de las aplicaciones de confianza que ha implementado en su entorno de Lync Server 2013. Una aplicación de confianza es una aplicación basada en el SDK de Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK en el que se confía en Lync Server 2013. Esta relación de confianza se resume en la lista siguiente:

  - Las aplicaciones de confianza no son desafiadas para la autenticación por parte de Lync Server.

  - Lync Server no limita las aplicaciones de confianza para las transacciones SIP, las conexiones o las llamadas salientes del Protocolo de voz sobre Internet (VoIP).

  - Las aplicaciones de confianza pueden suplantar a cualquier usuario y pueden unirse a conferencias sin que aparezcan en las listas.

  - Las aplicaciones de confianza tienen alta disponibilidad y resistencia.

En el panel de control de Lync Server, puede ver el nombre de las aplicaciones, el grupo de servidores donde se ejecutan y el puerto que usan.

<div>

## <a name="to-view-a-list-of-trusted-applications"></a>Para ver una lista de aplicaciones de confianza

1.  Desde una cuenta de usuario asignada al rol CsServerAdministrator, CsAdministrator, CsHelpDesk, o CsViewOnlyAdministrator , inicie sesión en cualquier equipo de su implementación interna. Para obtener más información sobre los roles administrativos predefinidos disponibles en Lync Server 2013, vea [planeación del control de acceso basado en roles en Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **topología** y en **aplicación de confianza**.

4.  En la página **aplicación de confianza** , haga clic en un encabezado de columna para ordenar las aplicaciones, si es necesario.

</div>

<div>

## <a name="see-also"></a>Vea también


[Administración de la topología de Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

