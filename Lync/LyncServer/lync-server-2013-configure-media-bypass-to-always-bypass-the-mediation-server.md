---
title: 'Lync Server 2013: configurar la omisión de medios para omitir siempre el servidor de mediación'
description: 'Lync Server 2013: configurar la omisión de medios para omitir siempre el servidor de mediación.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b4981c7b12700d2f0bbf0bf05c8a51623bb8ba9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552696"
---
# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a>Configurar la omisión de medios en Lync Server 2013 para omitir siempre el servidor de mediación

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-25_

<div>


> [!NOTE]  
> En este tema se presupone que ya ha configurado el desvío de medios para las conexiones de enlace troncal con un par (una puerta de enlace de red telefónica conmutada [RTC], un sistema PBX IP o un controlador de borde de sesión [SBC] en un proveedor de servicios de telefonía por Internet [ITSP]) para un sitio o servicio específico en el que desea que los medios omitan el servidor de mediación.<BR>No puede configurar los medios para que omitan siempre el servidor de mediación al tiempo que también habilita el control de admisión de llamadas. Estas opciones son incompatibles y, por lo tanto, son configuraciones mutuamente excluyentes en la interfaz de usuario del panel de control de Lync Server.



</div>

Además de habilitar el desvío de medios para conexiones de enlace troncal individuales asociadas a un par en el servidor de mediación, debe configurar también opciones globales para el desvío de medios. Si usa los pasos de este tema para establecer la configuración global de la omisión de medios, se supone que tiene buena conectividad entre los puntos de conexión de Lync y cualquier elemento del mismo nivel para el que haya configurado el desvío de medios en la conexión troncal.

Si no tiene buena conectividad entre los puntos de conexión de Lync Server y todos los elementos del mismo nivel que el servidor de mediación cuyas conexiones de tronco respectivas están habilitadas para el desvío de medios, debe configurar la configuración de omisión de medios globales para usar la información de sitio y región cuando emplee la omisión de medios. Con esto se permite un control más preciso para determinar cuándo los medios omiten el servidor de mediación. Para ello, siga los pasos descritos en [configurar la configuración global de omisión de medios en Lync server 2013 para usar la información de sitio y región](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) y [asociar una subred a un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) en su lugar.

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>Para habilitar globalmente el desvío de medios para que omita siempre el servidor de mediación

1.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Configuración de red**.

3.  Haga doble clic en la configuración **Global** de la lista.

4.  En la página **Editar configuración global**, seleccione la casilla **Habilitar desvío de medios**.

5.  Haga clic en **Desviar siempre**.

6.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Configurar la omisión de medios en Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Opciones de omisión de medios globales en Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
[Omisión de medios y servidor de mediación en Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)  


[Planeación de la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

