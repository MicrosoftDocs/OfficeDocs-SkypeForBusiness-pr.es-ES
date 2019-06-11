---
title: 'Lync Server 2013: requisitos de vídeo de cliente de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync client video requirements
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49733731
ms.date: 01/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56743abd386cb59b177806eed3d441aaf587ccce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-client-video-requirements-for-lync-server-2013"></a>Requisitos de vídeo de cliente de Lync para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-01-29_

Esta sección describe la compatibilidad de hardware de vídeo para las videollamadas de Lync 2013 y describe cómo determinar la calidad de video prevista para varias configuraciones de equipos, tabletas y dispositivos móviles.

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a>Requisitos y capacidades de vídeo y escritorio de Windows

Lync 2013 incluye aceleración de hardware para la codificación y descodificación de video basadas en el estándar de codificación de video de H. 264/MPEG-4, parte 10. Esta característica permite a los equipos con menores velocidades de reloj de CPU codificar y descodificar vídeo de mayor resolución. Los requisitos de hardware de vídeo varían en función de la configuración del equipo y de la resolución de vídeo que se desea.

<div>

## <a name="video-hardware-requirements"></a>Requisitos de hardware de vídeo


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Característica</th>
<th>Requisito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Descodificación H.264 acelerada por hardware mediante DirectX Video Acceleration (DXVA)</p></td>
<td><ul>
<li><p>La tarjeta gráfica necesita admitir DirectX 9.0 y necesita exponer el modo de descodificación DXVA2_ModeH264_VLD_NoFGT.</p></li>
<li><p>Necesita estar instalado el controlador de la tarjeta gráfica más reciente.</p></li>
</ul>
<div>

> [!NOTE]  
> Para obtener más información sobre los modos de <A href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</A>descodificación, consulte.


</div></td>
</tr>
<tr class="even">
<td><p>Codificación H.264 acelerada por hardware: requisitos del conjunto de chips</p></td>
<td><p>Se admiten las siguientes soluciones de codificación de vídeo acelerada por hardware Intel:</p>
<ul>
<li><p>Los chipsets Intel HD de segunda y tercera generación 2000, 2500, 3000 y 4000 (o versiones posteriores) con codificadores de vídeo de hardware integrados. Se requiere la instalación del controlador Intel HD Graphics 15.28.9.2884 o el controlador más reciente que contenga lo siguiente:</p>
<ul>
<li><p>Controlador de pantalla 9.17.10.2884 o el controlador más reciente</p></li>
<li><p>Hardware media foundation transform (HMFT) versión 3.12.10.31 o el HMFT más reciente</p></li>
</ul></li>
</ul>
<p>Se admiten las siguientes soluciones de codificación de vídeo acelerado por hardware AMD (requiere actualizaciones de CU1 para Lync Server 2013):</p>
<ul>
<li><p>AMD Video Codec Engine, que está disponible en varias tarjetas de gráficos independientes y en unidades de procesamiento acelerado integrado de procesadores acelerados de la serie AMD A. El controlador de AMD Video Codec Engine 9.12.0.0 o superior necesita estar instalado.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Codificación H.264 acelerada por hardware: requisitos de la cámara</p></td>
<td><p>Cámaras de vídeo USB con codificador de hardware H.264 integrado que cumplan la especificación USB Video Class (UVC) versión 1.5.</p>
<div>

> [!NOTE]  
> Lync 2013 admite cámaras UVC 1,5 con Windows 8 o Windows 8,1, que incluye compatibilidad con UVC 1,5. Dado que Windows 7 no incluye compatibilidad con UVC 1,5, Lync 2013 trata las cámaras de UVC 1,5 como cámaras normales sin compatibilidad con la codificación de hardware.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>Determinación de las capacidades de codificación y descodificación de video H. 264

Por lo general, son cuatro los factores principales que determinan la capacidad máxima de codificación y descodificación de una configuración de equipo determinada:

  - Compatibilidad para descodificación acelerada por hardware mediante DXVA

  - Compatibilidad para codificación acelerada por hardware

  - Número de núcleos físicos

  - Evaluación de la experiencia de Windows (WEI)

La Herramienta de evaluación del sistema de Windows (WinSAT) determina la WEI. Cuando ejecuta la herramienta WinSAT, genera un documento XML formal de evaluación en el equipo en el directorio% WINDIR%\\performance\\WinSAT\\de la tienda de almacenamiento. Este archivo XML contiene las siguientes dos puntuaciones que son especialmente importantes para determinar la capacidad de codificación y descodificación:

  - VideoEncodeScore indica la capacidad de codificación de vídeo basada en software del equipo.

  - El valor de GraphicsScore indica la capacidad de codificación acelerada por hardware del equipo.

Las siguientes tres tablas explican la capacidad máxima de codificación y descodificación de diferentes tipos de PC en función de la aceleración de hardware que admitan. Para resoluciones de 640 x 360 y superiores, la velocidad de fotogramas máxima admitida es de 30 fotogramas por segundo (fps). Para resoluciones inferiores a 640 x 360, la velocidad de fotogramas máxima admitida es de 15 fps.

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a>Equipo sin DXVA y sin codificador acelerado por hardware

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Resolución del codificador habilitado</th>
<th>Resolución del descodificador habilitado</th>
<th>Requisito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424 x 240</p></td>
<td><p>424 x 240 (640 x 360 a 15 fps para escenarios solo de recepción)</p></td>
<td><p>1 núcleo y VideoEncodeScore ≥4.0</p></td>
</tr>
<tr class="even">
<td><p>640 x 360</p></td>
<td><p>640 x 360</p></td>
<td><p>2 núcleos y VideoEncodeScore ≥4.5</p></td>
</tr>
<tr class="odd">
<td><p>640 x 360</p></td>
<td><p>1280 x 720</p></td>
<td><p>2 núcleos y VideoEncodeScore ≥4.5</p></td>
</tr>
<tr class="even">
<td><p>640 x 360</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 núcleos y VideoEncodeScore ≥4.5</p></td>
</tr>
<tr class="odd">
<td><p>1280 x 720</p></td>
<td><p>1280 x 720</p></td>
<td><p>4 núcleos y VideoEncodeScore ≥7.3</p></td>
</tr>
<tr class="even">
<td><p>1280 x 720</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 núcleos y VideoEncodeScore ≥7.3</p></td>
</tr>
<tr class="odd">
<td><p>1920 x 1080</p></td>
<td><p>1920 x 1080</p></td>
<td><p>N/D</p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a>Equipo con DXVA pero sin codificador acelerado por hardware

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Resolución del codificador habilitado</th>
<th>Resolución del descodificador habilitado</th>
<th>Requisito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424 x 240</p></td>
<td><p>1920 x 1080</p></td>
<td><p>1 núcleo y VideoEncodeScore ≥3.0</p></td>
</tr>
<tr class="even">
<td><p>640 x 360</p></td>
<td><p>1920 x 1080</p></td>
<td><p>2 núcleos y VideoEncodeScore ≥4.5</p></td>
</tr>
<tr class="odd">
<td><p>960 x 540</p></td>
<td><p>1920 x 1080</p></td>
<td><p>2 núcleos y VideoEncodeScore ≥6.0</p></td>
</tr>
<tr class="even">
<td><p>1280 x 720</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 núcleos y VideoEncodeScore ≥6.7</p></td>
</tr>
<tr class="odd">
<td><p>1920 x 1080</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 núcleos y VideoEncodeScore ≥8.2</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> La puntuación de WinSAT en Windows 7 está limitada a un máximo de 7,9. Por lo tanto, la capacidad de codificación de un equipo sin un codificador acelerado por hardware solo se puede lograr en Windows 8 o Windows 8.1, donde la puntuación máxima de WinSAT es de 9,9.



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a>Equipo con DXVA y con codificador acelerado por hardware Intel HD Graphics

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Resolución del codificador habilitado</th>
<th>Resolución del descodificador habilitado</th>
<th>Requisito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1280 x 720</p></td>
<td><p>1920 x 1080</p></td>
<td><p>Todos los modelos de Intel HD Graphics de segunda y tercera generación</p></td>
</tr>
<tr class="even">
<td><p>1920 x 1080</p></td>
<td><p>1920 x 1080</p></td>
<td><p>Todos los modelos de Intel HD Graphics de segunda y tercera generación y GraphicsScore ≥5.0</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a>Capacidades de vídeo de dispositivos móviles

En la tabla siguiente se describen las capacidades máximas de vídeo para dispositivos móviles compatibles. Para obtener más información sobre la compatibilidad de dispositivos móviles, vea [planificación de clientes móviles en Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Característica</th>
<th>Windows Phone</th>
<th>iPhone</th>
<th>iPad</th>
<th>Android</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Resolución máxima de codificación H.264</p></td>
<td><p>VGA</p></td>
<td><p>QVGA: iPhone 4S</p>
<p>VGA: iPhone 5</p>
<p>720p: iPhone 5S y versiones posteriores</p></td>
<td><p>VGA: iPad 2 y versiones posteriores/iPad mini 1 y versiones posteriores</p>
<p>720p: iPad Air/iPad mini 2/iPad Pro y versiones posteriores</p></td>
<td><p>Hasta VGA según el modelo de dispositivo</p></td>
</tr>
<tr class="even">
<td><p>Resolución máxima de descodificación H.264</p></td>
<td><p>VGA</p></td>
<td><p>QVGA: iPhone 4S</p>
<p>VGA: iPhone 5</p>
<p>720p: iPhone 5S y versiones posteriores</p></td>
<td><p>VGA: iPad 2 y versiones posteriores/iPad mini 1 y versiones posteriores</p>
<p>720p: iPad Air/iPad mini 2/iPad Pro y versiones posteriores</p></td>
<td><p>Hasta VGA según el modelo de dispositivo</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

