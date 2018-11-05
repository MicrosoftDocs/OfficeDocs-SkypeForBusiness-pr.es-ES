---
title: 'Lync Server 2013: Configurar el control de admisión de llamadas'
TOCTitle: Configurar el control de admisión de llamadas
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48276697
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar el control de admisión de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

El control de admisión de llamadas es una solución que determina si puede establecerse una sesión en tiempo real según el ancho de banda disponible para impedir que los usuarios de redes congestionadas obtengan una calidad de audio y vídeo pobre. Esta solución controla el tráfico en tiempo real únicamente para el audio y el vídeo, y no afecta al tráfico de datos. Puede enrutar la llamada a través de una ruta de acceso de Internet, si la ruta de acceso WAN predeterminada no dispone del ancho de banda requerido. Para más información, consulte [Planear el control de admisión de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) en la documentación sobre planeación.

En esta sección se proporciona un conjunto de procedimientos de ejemplo donde se describe cómo implementar y administrar el control de admisión de llamadas en una red.

> [!IMPORTANT]  
> Antes de iniciar la implementación del servicio de control de admisión de llamadas, debe recopilar toda la información necesaria para la topología de red de empresa, tal como se describe en <a href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Ejemplo: Recopilación de los requisitos de la organización para el servicio de control de admisión de llamadas en Lync Server 2013</a> en la documentación referente a la planeación. Asimismo, compruebe que se hayan instalado y activado todos los componentes del servicio de control de admisión de llamadas, tal como se describe en <a href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync Server 2013</a>, en la documentación sobre implementación.




> [!NOTE]
> Todos los ejemplos de administración e implementación del control de admisión de llamadas descritos en esta sección se llevan a cabo con el Shell de administración de Lync Server. También puede usar la sección <STRONG>Configuración de red</STRONG> del Panel de control de Lync Server para administrar el control de admisión de llamadas.



## En esta sección

  - [Configurar regiones de red para el control de admisión de llamadas en Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md)

  - [Crear perfiles de directivas de ancho de banda en Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [Configurar sitios de red para CAC en Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md)

  - [Asociar subredes a sitios de red para el control de admisión de llamadas en Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [Crear vínculos de regiones de red en Lync Server 2013](lync-server-2013-create-network-region-links.md)

  - [Crear rutas entre regiones de red en Lync Server 2013](lync-server-2013;-create-network-interregion-routes.md)

  - [Crear directivas entre sitios de red en Lync Server 2013](lync-server-2013-create-network-intersite-policies.md)

  - [Habilitar el control de admisión de llamadas en Lync Server 2013](lync-server-2013-enable-call-admission-control.md)

  - [Lista de comprobación para la implementación del control de admisión de llamadas en Lync Server 2013](lync-server-2013-call-admission-control-deployment-checklist.md)

