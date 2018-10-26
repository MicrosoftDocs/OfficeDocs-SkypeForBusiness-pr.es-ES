---
title: 'Lync Server 2013: Planear el control de admisión de llamadas'
TOCTitle: Planear el control de admisión de llamadas (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48276659
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planear el control de admisión de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

Para las aplicaciones de comunicaciones unificadas (UC) basadas en IP, como la telefonía, el vídeo y el uso compartido de aplicaciones, el ancho de banda disponible de las redes de empresa no se considera normalmente un factor limitante dentro de los entornos de LAN; sin embargo, en los vínculos WAN que conectan sitios entre sí, el ancho de banda de red puede restringirse. Cuando una entrada de tráfico de red produce una suscripción excesiva en un vínculo WAN, los mecanismos actuales como la puesta en cola, el almacenamiento en búfer y la pérdida de paquetes se usan para solucionar la congestión. El tráfico adicional normalmente se retrasa hasta que la congestión de la red mejora o, si es necesario, se elimina el tráfico. Para el tráfico de datos convencional en estas situaciones, el cliente receptor puede recuperar. Para el tráfico en tiempo real como las comunicaciones unificadas, la congestión de la red no se puede solucionar de este modo porque el tráfico de las comunicaciones unificadas es sensible a la latencia y a la pérdida de paquetes. La congestión en la WAN puede ocasionar una baja Calidad de la experiencia (QoE) para los usuarios finales. Para el tráfico en tiempo real en condiciones de congestión, es mejor denegar llamadas que permitir conexiones de baja calidad.

El servicio de control de admisión de llamadas (CAC) determina si hay suficiente ancho de banda de red para establecer una sesión en tiempo real con una calidad aceptable. En Lync Server 2013, CAC controla el tráfico en tiempo real únicamente para el audio y el vídeo, pero no afecta al tráfico de datos. Si la ruta de acceso WAN predeterminada no tiene el ancho de banda necesario, CAC puede intentar enrutar la llamada a través de una ruta de acceso de Internet o de la RTC. CAC solo está disponible en Lync Server.

En esta sección se describen las funciones de control de admisión de llamadas y explica cómo planear para CAC.


> [!NOTE]
> Lync Server tiene tres características de Telefonía IP empresarial avanzadas: control de admisión de llamadas, servicios de emergencia (E9-1-1) y desvío de medios. Para ver información general acerca de los datos de planeación comunes a las tres características, consulte <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Configuración de red para las características avanzadas de telefonía IP empresarial en Lync Server 2013</A>.



## En esta sección

  - [Información general sobre el control de admisión de llamadas en Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md)

  - [Definición de los requisitos de la organización para el servicio de control de admisión de llamadas en Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [Ejemplo: Recopilación de los requisitos de la organización para el servicio de control de admisión de llamadas en Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [Componentes y topologías para CAC en Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md)

  - [Procedimientos recomendados para el servicio de control de admisión de llamadas en Lync Server 2013](lync-server-2013-best-practices-for-call-admission-control.md)

  - [Lista de comprobación para la implementación del control de admisión de llamadas en Lync Server 2013](lync-server-2013-deployment-checklist-for-call-admission-control.md)

