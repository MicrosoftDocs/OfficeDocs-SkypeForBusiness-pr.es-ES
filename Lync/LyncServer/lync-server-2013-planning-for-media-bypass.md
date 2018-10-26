---
title: 'Lync Server 2013: Planificar la omisión de medios'
TOCTitle: Planificar la omisión de medios
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48275956
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planificar la omisión de medios en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

El desvío de medios consiste en quitar el servidor de mediación de la ruta de acceso a medios siempre que sea posible, en las llamadas cuya señalización atraviese el servidor de mediación.

El desvío de medios puede mejorar la calidad de la voz al reducir la latencia, la traducción innecesaria, la posibilidad de pérdida de paquetes y el número de puntos de errores potenciales. Se puede mejorar la escalabilidad, ya que, al eliminar el procesamiento de medios de las llamadas desviadas, se reduce la carga del servidor de mediación. Esta reducción en la carga complementa a la capacidad del Servidor de mediación para controlar varias puertas de enlace.

En los lugares donde una sucursal sin Servidor de mediación está conectada a un sitio central mediante uno o más vínculos WAN con ancho de banda restringido, el desvío de medios disminuye la necesidad de ancho de banda, al permitir que los medios de un cliente en una sucursal fluyan directamente hasta su puerta de enlace local, sin tener que pasar primero por el vínculo WAN hasta un Servidor de mediación del sitio central y volver.

Al evitar el procesamiento de medios al Servidor de mediación, el desvío de medios puede reducir también la cantidad de Servidores de mediación que necesita una infraestructura de Telefonía IP empresarial.

La siguiente ilustración muestra las rutas de señalización y los medios básicos en las topologías con desvío de medios y sin él.

**Rutas de señalización y medios con desvío de medios y sin él**

![Aplicación de la conexión de desvío de medios del control de admisión de llamadas de voz](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Aplicación de la conexión de desvío de medios del control de admisión de llamadas de voz")

Por regla general, se recomienda habilitar el desvío de medios siempre que sea posible.

## En esta sección

  - [Introducción general a la omisión de medios en Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)

  - [Modos de omisión de medios en Lync Server 2013](lync-server-2013-media-bypass-modes.md)

  - [Omisión de medios y control de admisión de llamadas en Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [Requisitos técnicos para la omisión de medios en Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)

## Secciones relacionadas

[Implementación de características avanzadas de telefonía IP empresarial en Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

## Vea también

#### Tareas

[Configurar un tronco con omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  

#### Conceptos

[Opciones globales de desvío de medios en Lync Server 2013](lync-server-2013-global-media-bypass-options.md)

