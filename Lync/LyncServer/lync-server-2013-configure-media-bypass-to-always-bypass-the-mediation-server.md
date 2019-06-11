---
title: 'Lync Server 2013: configurar la omisión de medios para omitir siempre el servidor de mediación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aca094110036692c5ac5327b166a3f81e4b769f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a>Configure media bypass in Lync Server 2013 to always bypass the Mediation Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-25_

<div>


> [!NOTE]  
> En este tema se supone que ya ha configurado la omisión de medios para cualquier conexión troncal a un interlocutor (una puerta de enlace de red de telefonía pública conmutada (RTC), un IP-PBX o un controlador de borde de sesión (SBC) en un proveedor de servicios de telefonía de Internet (ITSP)) para una determinada sitio o servicio para el que quiere que el medio eluda el servidor de mediación.<BR>No puede configurar los medios para omitir siempre el servidor de mediación y también habilitar el control de admisión de llamadas. Esta configuración es incompatible y, por lo tanto, es mutuamente excluyente en la interfaz de usuario del panel de control de Lync Server.



</div>

Además de habilitar la omisión de medios para conexiones troncales individuales asociadas con un servidor de mediación, también debe establecer la configuración global para la omisión de medios. Si usa los pasos de este tema para establecer la configuración global de omisión de elementos multimedia, se supone que tiene una buena conectividad entre los puntos de conexión de Lync y cualquier elemento del mismo nivel para el que haya configurado el bypass de medios en la conexión troncal.

Si no tiene buena conectividad entre los puntos de conexión de Lync Server y todos los elementos del servidor de media cuyas conexiones troncales se han habilitado para la omisión de medios, debe configurar la configuración de omisión de multimedia global para usar la información del sitio y de la región cuando usar la omisión de medios. Esto permite un mayor control para determinar cuándo el contenido multimedia pasa por alto el servidor de mediación. Para ello, siga los pasos de [configurar la configuración global de omisión de medios en Lync server 2013 para usar la información del sitio y de la región](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) y asociar [una subred con un sitio de red en Lync Server 2013 en](lync-server-2013-associate-a-subnet-with-a-network-site.md) su lugar.

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>Para habilitar globalmente el desvío de medios para que omita siempre el servidor de mediación

1.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Configuración de red**.

3.  Haga doble clic en la configuración **Global** de la lista.

4.  En la página **Editar configuración global**, seleccione la casilla **Habilitar omisión de medios**.

5.  Haga clic en **Omitir siempre**.

6.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Vea también


[Configurar la omisión de medios en Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Opciones de omisión de multimedia global en Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
[Omisión de medios y servidor de mediación en Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)  


[Planificar la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

