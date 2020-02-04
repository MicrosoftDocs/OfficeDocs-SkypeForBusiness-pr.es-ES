---
title: 'Lync Server 2013: póster: indicadores clave de estado'
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
ms.openlocfilehash: 812ce68c84f86250fd25cc646bbcd5faddf0e566
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747450"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a>Indicadores clave de estado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-10_

Este artículo es un complemento de los [indicadores clave de estado: la base para mantener el póster de los servidores de Lync en buen estado](http://go.microsoft.com/fwlink/?linkid=391838) , que puede descargar desde el centro de descarga.

![Póster que describe la solución de problemas con datos de KHI](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Póster que describe la solución de problemas con datos de KHI")

Puede usar este póster para obtener información sobre los indicadores clave de estado (KHIs), los contadores de rendimiento con umbrales destinados a revelar problemas de experiencia del usuario. La recopilación de datos de KHI suele ser el primer paso para implementar la metodología de calidad de las llamadas (CQM), que se centra en garantizar una experiencia de audio de calidad para los usuarios de Lync.

Si tienes preguntas sobre cómo usar CQM, puedes enviar tus preguntas a cqmfeedback@microsoft.com.

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

Los indicadores de estado de clave son contadores de rendimiento con umbrales destinados a revelar problemas de experiencia del usuario. La recopilación de datos de KHI suele ser el primer paso para implementar la metodología de calidad de las llamadas (CQM), que se centra en garantizar una experiencia de audio de calidad para los usuarios de Lync.

KHIs se usan además de las soluciones de supervisión estándar de Lync (por ejemplo, System Center Operations Manager, transacciones sintéticas, servidor de supervisión) y no en lugar de esas soluciones.

Recopilar los contadores de rendimiento de KHI y rellenar la hoja de cálculo KHI que acompaña a la guía de redes para crear un cuadro de mandos que le ayudará a determinar el estado del servidor de una implementación de Lync. Una vez que se haya rellenado, le guiará para reparar el entorno y le dará información adicional a otros participantes. Evalúe KHIs cada mes e incorpórelo a cualquier proceso operativo en curso de implementación.

Descargue la [Guía de redes de Lync Server](http://go.microsoft.com/fwlink/p/?linkid=390677) para ver la lista completa de KHIs y para obtener las hojas de cálculo relacionadas.

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a>Para recopilar datos de KHI

1.  Ejecute el script KHI que se incluye con la guía de redes de Lync Server en cada servidor de Lync. Esto creará un recopilador de datos dentro del monitor de rendimiento y le dará el nombre KHI. De forma predeterminada, los datos se sondearán cada 15 segundos.

2.  Antes de iniciar el día hábil de la empresa, vaya a cada servidor de Lync e inicie el recopilador de datos de KHI.

3.  Al final de ese día, detenga el recopilador de datos de KHI y copie los datos en una ubicación central.

4.  Después de usar Monitor de rendimiento para rellenar la hoja de cálculo KHI incluida en la descarga de la guía de redes de Lync Server, compare los resultados con los destinos recomendados.

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a>Flujo de corrección para todos los roles de servidor

Para cada servidor de la implementación de Lync, primero Compruebe que el estado del componente y el rendimiento del sistema del servidor están en el nivel deseado o por encima de él. Solo después de eso debería consultar los indicadores relacionados con el rol del servidor en la implementación general de Lync.

Comienza con la recopilación de datos de rendimiento de KHI para todos los servidores. Para cada uno de los roles del sistema (los detalles tratados más adelante en este documento) determine si los componentes básicos del sistema cumplen los objetivos recomendados. Si no es así, corrija el rendimiento del sistema y vuelva a recopilar datos de KHI y asegúrese de que el estado del sistema antes de ver las métricas específicas de la función del servidor en la implementación de Lync. El estado del componente para todos los roles se define como sigue:

  - Uso de \< la CPU 80%

  - Promedio de escrituras \< en disco: 10 ms

  - Disco de lectura \< promedio: 10 ms

  - Memoria \>disponible 20% de sistema total MB

  - Longitud \< de cola de red 2

  - Paquetes descartados (o fuera) = 0

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a>Glosario

Los siguientes términos y acrónimos se usan en este póster:

Como la unidad de control de varios puntos de la MCU = uso compartido de aplicaciones

CABLE MCU = audio/video MCU

MI MCU = mensajería instantánea MCU

UCWA = API Web de comunicaciones unificadas

Borde AV = recorrido de audio o vídeo vía borde

Autenticación AV = autenticación de audio y vídeo

SIP Stack = contiene la implementación de SIP principal de Lync

Proxy de datos = usado para conferencias perimetrales

LySS = servicio de almacenamiento de Lync

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a>Servidores front-end

Los siguientes destinos KHI recomendados son específicos de los servidores front-end, además del estado básico de los componentes:


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
<td><p>AS/AV/MENSAJERÍA INSTANTÁNEA MCU</p></td>
<td><p>Estado &lt;de mantenimiento MCU 2</p></td>
</tr>
<tr class="even">
<td><p>Componentes Web</p></td>
<td><p>Tiempo de espera de anuncio de &lt;expansión de lista de distribución 0</p>
<p>Errores de ABWQ = 0</p>
<p>Errores de LIS = 0</p>
<p>Errores &lt; de autenticación 1/s</p>
<p>Solicitudes ASP.NET V4 rechazadas = 0</p></td>
</tr>
<tr class="odd">
<td><p>Pila SIP</p></td>
<td><p>Promedio de procesamiento &lt; de mensajes entrantes de 1 s</p>
<p>Respuestas entrantes &lt; quitadas 1/s solicitudes &lt; entrantes descartadas 1/s</p>
<p>Latencia &lt; de cola 100 ms</p>
<p>Latencia &lt; del procedimiento almacenado 100 ms</p>
<p>Solicitudes limitadas = 0</p>
<p>Errores &lt; de autenticación 1/s</p>
<p>Se agotó el tiempo de &lt; espera de los mensajes entrantes 2</p>
<p>Promedio de mensajes entrantes &lt; en espera 1 s</p>
<p>Conexiones &lt; controladas por flujo 2</p>
<p>Retraso &lt; de cola de salida promedio 2 s</p></td>
</tr>
<tr class="even">
<td><p>LySS</p></td>
<td><p>% de espacio usado por la base de &lt; BD de servicio de almacenamiento 80</p>
<p>#de errores de replicación de réplica = 0</p>
<p>#eventos de pérdida de datos = 0</p></td>
</tr>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>Esperanza &gt; de vida de la página 300 s</p>
<p>Solicitudes de lotes/ &lt; s 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a>Servidores SQL back-end

Los siguientes destinos KHI recomendados son específicos de los servidores SQL Server además del estado básico de los componentes:


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
<td><p>Esperanza &gt; de vida de la página 300 s</p>
<p>Solicitudes de lotes/ &lt; s 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a>Servidores de mediación

Los siguientes destinos KHI recomendados son específicos de los servidores de mediación, además del estado básico de los componentes:


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
<td><p>Servicio servidor de mediación</p></td>
<td><p>Índice de error de llamada de carga = 0</p>
<p>Llamadas fallidas debido al &lt;proxy 10</p>
<p>Llamadas fallidas debido a &lt;la puerta de enlace 10</p>
<p>Llamadas (dentro o salida) rechazadas = 0</p>
<p>Candidatos a medios ausentes = 0</p>
<p>Errores de comprobación de conectividad de medios = 0</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a>Servidores perimetrales

Los siguientes destinos KHI recomendados son específicos de los servidores perimetrales además del estado básico de los componentes:


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
<td><p>Autenticación de AV</p></td>
<td><p>Solicitudes &lt; erróneas 20/s</p></td>
</tr>
<tr class="even">
<td><p>Borde AV</p></td>
<td><p>Errores &lt;de auth. 20/s</p>
<p>Errores &lt;de asignación de 20/s</p>
<p>Paquetes descartados &lt;300/s</p></td>
</tr>
<tr class="odd">
<td><p>Proxy de datos</p></td>
<td><p>Conexiones &lt; de servidor limitado 3</p>
<p>El sistema está limitando &lt;1</p></td>
</tr>
<tr class="even">
<td><p>Pila SIP</p></td>
<td><p>Descartar &lt; conexiones por límite 1</p>
<p>Se agotó el tiempo &lt;de espera de envíos 10</p>
<p>Conexiones &lt;controladas por flujo 100</p>
<p>Solicitudes entrantes &lt; descartadas 1/s</p>
<p>Promedio de procesamiento &lt; de mensajes 3 por segundo</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Vea también


[Guía de redes de Lync Server](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[Indicadores clave de estado: la base para mantener los servidores de Lync en buen estado](http://go.microsoft.com/fwlink/?linkid=391838)  
[Metodología de calidad de llamadas de Lync](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

