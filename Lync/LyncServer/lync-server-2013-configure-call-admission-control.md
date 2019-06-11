---
title: 'Lync Server 2013: configurar el control de admisión de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure call admission control
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48185464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86961c9f282e1a486bf7cf94eda494d37c415cf6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-admission-control-in-lync-server-2013"></a>Configurar el control de admisión de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

El control de admisión de llamadas (CAC) es una solución que determina si puede establecerse una sesión en tiempo real según el ancho de banda disponible para impedir que los usuarios de redes congestionadas obtengan una calidad de audio y vídeo pobre. CAC controla el tráfico en tiempo real solo para audio y vídeo, y no afecta al tráfico de datos. CAC puede enrutar la llamada a través de una ruta de Internet cuando la ruta de acceso WAN predeterminada no tiene el ancho de banda requerido. Para obtener más información, consulte [planificación de control de admisión de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) en la documentación de planeación.

Esta sección proporciona un conjunto de procedimientos de ejemplo que muestran cómo implementar y administrar CAC en su red.

<div>


> [!IMPORTANT]  
> Antes de implementar CAC, debe reunir toda la información necesaria para la topología de red de su empresa, como se describe en <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">ejemplo: recopilación de los requisitos para el control de admisión de llamadas en Lync Server 2013</A> en la documentación de planeación. Además, asegúrese de que los componentes de CAC se han instalado y activado, tal y como se describe en <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync server 2013</A> en la documentación de implementación.



</div>

<div>


> [!NOTE]  
> Todos los ejemplos de implementación y administración de CAC en esta sección se realizan mediante el shell de administración de Lync Server. Como alternativa, también puede usar la sección <STRONG>configuración de red</STRONG> del panel de control de Lync Server para administrar CAC.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configurar regiones de red para CAC en Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md)

  - [Crear perfiles de directiva de ancho de banda en Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [Configurar sitios de red para CAC en Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md)

  - [Asociar subredes con sitios de red para CAC en Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [Crear vínculos de región de red en Lync Server 2013](lync-server-2013-create-network-region-links.md)

  - [Crear rutas interregional de red en Lync Server 2013](lync-server-2013;-create-network-interregion-routes.md)

  - [Crear directivas de intersitios de red en Lync Server 2013](lync-server-2013-create-network-intersite-policies.md)

  - [Habilitar el control de admisión de llamadas en Lync Server 2013](lync-server-2013-enable-call-admission-control.md)

  - [Lista de comprobación de la implementación de control de admisión para Lync Server 2013](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

