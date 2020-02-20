---
title: 'Lync Server 2013: configurar el control de admisión de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call admission control
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48185464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad0d297981bec3fe133e88a090a3c60a97f1ec9d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146523"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-call-admission-control-in-lync-server-2013"></a>Configurar el control de admisión de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

El control de admisión de llamadas es una solución que determina si puede establecerse una sesión en tiempo real según el ancho de banda disponible para impedir que los usuarios de redes congestionadas obtengan una calidad de audio y vídeo pobre. Esta solución controla el tráfico en tiempo real únicamente para el audio y el vídeo, y no afecta al tráfico de datos. Puede enrutar la llamada a través de una ruta de acceso de Internet, si la ruta de acceso WAN predeterminada no dispone del ancho de banda requerido. Para obtener más información, consulte [Planning for Call Admission Control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) en la documentación referente a la planeación.

En esta sección se proporciona un conjunto de procedimientos de ejemplo donde se describe cómo implementar y administrar el control de admisión de llamadas en una red.

<div>


> [!IMPORTANT]  
> Antes de implementar el CAC, debe recopilar toda la información necesaria para la topología de red de la empresa, como se describe en <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">ejemplo: reunión de los requisitos para el control de admisión de llamadas en Lync Server 2013</A> en la documentación referente a la planeación. Asegúrese también de que los componentes de CAC se hayan instalado y activado, como se describe en <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync server 2013</A> en la documentación sobre implementación.



</div>

<div>


> [!NOTE]  
> Todos los ejemplos de implementación y administración de CAC en esta sección se realizan mediante el shell de administración de Lync Server. Como alternativa, también puede usar la sección <STRONG>configuración de red</STRONG> del panel de control de Lync Server para administrar el CAC.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configurar regiones de red para CAC en Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md)

  - [Crear perfiles de directiva de ancho de banda en Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [Configurar sitios de red para CAC en Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md)

  - [Asociar subredes a sitios de red para CAC en Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [Crear vínculos de región de red en Lync Server 2013](lync-server-2013-create-network-region-links.md)

  - [Crear rutas entre regiones de red en Lync Server 2013](lync-server-2013;-create-network-interregion-routes.md)

  - [Crear directivas entre sitios de red en Lync Server 2013](lync-server-2013-create-network-intersite-policies.md)

  - [Habilitar el control de admisión de llamadas en Lync Server 2013](lync-server-2013-enable-call-admission-control.md)

  - [Lista de comprobación para la implementación del control de admisión de llamadas para Lync Server 2013](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

