---
title: 'Lync Server 2013: póster: indicadores de estado clave'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6b67c4843cc0c1039bee48aa6b7c4620b77ce08
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006998"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a>Indicadores de estado clave en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-10_

Este artículo es un complemento para el póster [key Health Indicators: la base para mantener un póster de los servidores de Lync en buen estado](http://go.microsoft.com/fwlink/?linkid=391838) , que puede descargar desde el centro de descarga.

![Póster que describe cómo solucionar problemas con datos de KHI](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Póster que describe cómo solucionar problemas con datos de KHI")

Puede usar este póster para obtener información sobre los indicadores de estado clave (KHIs), los contadores de rendimiento con umbrales destinados a revelar los problemas de la experiencia del usuario. La recopilación de datos de KHI suele ser el primer paso para implementar la metodología de calidad de llamadas (CQM), que se centra en garantizar una experiencia de audio de calidad para los usuarios de Lync.

Si tiene preguntas sobre cómo usar CQM, puede enviar sus preguntas a cqmfeedback@microsoft.com.

En el póster se explican las siguientes áreas:

  - ¿Qué son los indicadores de estado clave?

  - Para recopilar datos de KHI

  - Flujo de corrección para todos los roles de servidor

  - Glosario

  - Servidores front-end

  - Servidores SQL back-end

  - Servidores de mediación

  - Servidores perimetrales

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a>¿Qué son los indicadores de estado clave?

Los indicadores de estado clave son contadores de rendimiento con umbrales destinados a revelar los problemas de la experiencia del usuario. La recopilación de datos de KHI suele ser el primer paso para implementar la metodología de calidad de llamadas (CQM), que se centra en garantizar una experiencia de audio de calidad para los usuarios de Lync.

KHIs se usan junto con las soluciones de supervisión de Lync estándar (por ejemplo, System Center Operations Manager, transacciones sintéticas, servidor de supervisión) y no en lugar de esas soluciones.

Recopilar los contadores de rendimiento de KHI y rellenar la hoja de cálculo KHI que acompaña a la guía de redes para crear un cuadro de mandos que le ayudarán a determinar el estado del servidor de una implementación de Lync. Una vez rellenado, le guía en la reparación del entorno y ofrece información adicional a otras partes interesadas. Evalúe los KHIs cada mes e incorpórelo a los procesos operativos en curso de la implementación.

Descargue la [Guía de redes de Lync Server](http://go.microsoft.com/fwlink/p/?linkid=390677) para ver la lista completa de KHIs y para obtener las hojas de cálculo relacionadas.

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a>Para recopilar datos de KHI

1.  Ejecute el script KHI incluido con la guía de red de Lync Server en cada Lync Server. Se creará un recopilador de datos dentro del monitor de rendimiento y se le asignará el nombre KHI. De forma predeterminada, los datos se sondearán cada 15 segundos.

2.  Antes de iniciar el día hábil de la compañía, vaya a cada Lync Server e inicie el recopilador de datos de KHI.

3.  Al final de ese día, detenga el recopilador de datos de KHI y copie los datos en una ubicación central.

4.  Después de usar el monitor de rendimiento para rellenar la hoja de cálculo KHI que se incluye con la guía de redes de Lync Server, compare los resultados con los objetivos recomendados.

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a>Flujo de corrección para todos los roles de servidor

Para cada servidor de la implementación de Lync, primero Compruebe que el estado del componente y el rendimiento del sistema del servidor se encuentra en el nivel deseado o por encima de él. Solo después de eso, debería mirar los indicadores relacionados con el rol del servidor en la implementación general de Lync.

Empiece por recopilar datos de rendimiento de KHI para todos los servidores. Para cada uno de los roles del sistema (los detalles que se describen más adelante en este documento) determinan si los componentes básicos del sistema cumplen con los objetivos recomendados. Si no es así, corrija el rendimiento del sistema y vuelva a recopilar datos de KHI y garantice el estado del sistema antes de ver las métricas específicas del rol del servidor en la implementación de Lync. El estado del componente para todos los roles se define como:

  - Uso de \< la CPU 80%

  - Promedio de escrituras \< en disco 10 ms

  - Promedio de lectura \< de disco 10 ms

  - Memoria \>disponible 20% total de MB de sistema

  - Longitud \< 2 de cola de red

  - Paquetes descartados (in/out) = 0

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a>Glosario

En este póster se usan los siguientes términos y acrónimos:

COMO MCU = unidad de control de varios puntos de uso compartido de aplicaciones

MCU AV = MCU de audio y vídeo

La MCU de mensajería instantánea

UCWA = API Web de comunicaciones unificadas

Perimetral AV = recorrido de audio y vídeo a través de la periferia

Autenticación AV = autenticación de audio y vídeo

La pila SIP = contiene la implementación SIP principal de Lync

Proxy de datos = usado para las conferencias perimetrales

LySS = servicio de almacenamiento de Lync

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a>Servidores front-end

Los siguientes destinos KHI recomendados son específicos de los servidores front-end, además del estado básico del componente:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Área funcional</th>
<th>Métricas de destino</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>MCU AS/AV/IM</p></td>
<td><p>Estado &lt;de mantenimiento de MCU 2</p></td>
</tr>
<tr class="even">
<td><p>Componentes Web</p></td>
<td><p>Tiempo de espera de AD de &lt;expansión de lista de distribución 0</p>
<p>Errores de ABWQ = 0</p>
<p>Errores de LIS = 0</p>
<p>Errores &lt; de autenticación 1/seg.</p>
<p>Solicitudes ASP.NET V4 rechazadas = 0</p></td>
</tr>
<tr class="odd">
<td><p>Pila SIP</p></td>
<td><p>Promedio de procesamiento &lt; de mensajes entrantes 1 seg.</p>
<p>Respuestas entrantes &lt; descartadas 1/s &lt; solicitudes entrantes descartadas 1/seg</p>
<p>Latencia &lt; de cola 100 ms</p>
<p>Latencia &lt; de SPROC 100 ms</p>
<p>Solicitudes limitadas = 0</p>
<p>Errores &lt; de autenticación 1/seg.</p>
<p>Se agotó el tiempo de &lt; espera de los mensajes entrantes 2</p>
<p>Tiempo medio de espera &lt; de mensajes entrantes 1 seg.</p>
<p>Conexiones &lt; controladas por flujo 2</p>
<p>Retraso &lt; de la cola de salida promedio 2 segundos</p></td>
</tr>
<tr class="even">
<td><p>LySS</p></td>
<td><p>% de espacio usado por la base &lt; de datos del servicio de almacenamiento 80</p>
<p>#de errores de replicación de réplica = 0</p>
<p>#de eventos de pérdida de datos = 0</p></td>
</tr>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>Esperanza &gt; de vida de la página 300 seg.</p>
<p>Solicitudes de lote por &lt; segundo 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a>Servidores SQL back-end

Los siguientes destinos KHI recomendados son específicos de los servidores SQL Server, además del estado básico del componente:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Área funcional</th>
<th>Métricas de destino</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>Esperanza &gt; de vida de la página 300 seg.</p>
<p>Solicitudes de lote por &lt; segundo 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a>Servidores de mediación

Los siguientes destinos KHI recomendados son específicos de los servidores de mediación, además del estado básico del componente:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Área funcional</th>
<th>Métricas de destino</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servicio de servidor de mediación</p></td>
<td><p>Índice de error de llamada de carga = 0</p>
<p>Llamadas con error debido al &lt;proxy 10</p>
<p>Llamadas con error debido a &lt;la puerta de enlace 10</p>
<p>Llamadas (in o out) rechazadas = 0</p>
<p>Candidatos con medios ausentes = 0</p>
<p>Errores de comprobación de conectividad de medios = 0</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a>Servidores perimetrales

Los siguientes destinos KHI recomendados son específicos de los servidores perimetrales, además del estado básico del componente:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Área funcional</th>
<th>Métricas de destino</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autenticación de antivirus</p></td>
<td><p>Solicitudes &lt; incorrectas 20/seg</p></td>
</tr>
<tr class="even">
<td><p>Borde AV</p></td>
<td><p>Errores &lt;de auth. 20/seg</p>
<p>Errores &lt;de asignación de 20/seg.</p>
<p>Paquetes descartados &lt;300/seg</p></td>
</tr>
<tr class="odd">
<td><p>Proxy de datos</p></td>
<td><p>Conexiones &lt; de servidor limitadas 3</p>
<p>El sistema se está &lt;limitando a 1</p></td>
</tr>
<tr class="even">
<td><p>Pila SIP</p></td>
<td><p>Conexiones superadas por &lt; límite descartadas 1</p>
<p>Envíos agotados &lt;10</p>
<p>Conexiones &lt;controladas por flujo 100</p>
<p>Solicitudes entrantes &lt; descartadas 1/seg.</p>
<p>Promedio de procesamiento &lt; de mensajes 3 seg.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Vea también


[Guía de redes de Lync Server](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[Indicadores de estado clave: la base para mantener servidores de Lync en buen estado](http://go.microsoft.com/fwlink/?linkid=391838)  
[Metodología de calidad de llamadas de Lync](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

