﻿---
title: 'Lync Server 2013: Modos de omisión de medios'
TOCTitle: Modos de omisión de medios
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425862(v=OCS.15)
ms:contentKeyID: 48274967
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modos de omisión de medios en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-05_

Debe configurar el desvío de medios de forma global y para cada tronco RTC individual. Al habilitar el desvío de medios globalmente, tiene dos opciones: **Desviar siempre** y **Usar información de sitio y región**.

Como el propio nombre sugiere, **Desviar siempre** significa que se intentará realizar el desvío de todas las llamadas de RTC. **Desviar siempre** se usa en implementaciones en las que no hay necesidad de habilitar el control de admisión de llamadas ni de especificar información detallada de configuración con respecto a cuándo intentar el desvío de medios. Además, **Desviar siempre** se usa cuando existe plena conectividad entre clientes y puertas de enlace de RTC. En esta configuración, todas las subredes se asignan únicamente a un solo identificador de desvío, que el sistema calcula.

Con **Usar información de sitio y región**, se usa el identificador de desvío asociado a la configuración del sitio y la región para tomar la decisión de desvío. Esta configuración proporciona la flexibilidad de configurar el desvío para las topologías más comunes, ya que proporciona un control más preciso cuando se produce el desvío, además de admitir interacciones con el control de admisión de llamadas (CAC). El sistema intenta facilitarle la tarea asignando automáticamente identificadores de desvío de la manera siguiente.

  - El sistema asigna automáticamente un único identificador de desvío a cada región.

  - Cualquier sitio conectado a una región por un vínculo WAN sin restricciones de ancho de banda hereda el mismo identificador de desvío de la región.

  - A un sitio asociado a la región por un vínculo WAN con un ancho de banda restringido se le asigna un identificador de desvío distinto al de la región.

  - Las subredes asociadas a cada sitio heredan el identificador de desvío del sitio.

## Vea también

#### Conceptos

[Introducción general a la omisión de medios en Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)  
[Omisión de medios y control de admisión de llamadas en Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Requisitos técnicos para la omisión de medios en Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)

