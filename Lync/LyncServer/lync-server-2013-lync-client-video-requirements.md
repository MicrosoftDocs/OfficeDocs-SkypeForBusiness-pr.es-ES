---
title: 'Lync Server 2013: requisitos de vídeo del cliente de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync client video requirements
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49733731
ms.date: 01/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6d5b06123879f2f9724fbd0f49facb8336d9860
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-client-video-requirements-for-lync-server-2013"></a>Requisitos de vídeo del cliente de Lync para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-01-29_

En esta sección se describe la compatibilidad de hardware de vídeo para llamadas de vídeo de Lync 2013 y se describe cómo determinar la calidad de vídeo prevista para varias configuraciones de equipos, tabletas y dispositivos móviles.

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a>Requisitos y capacidades de vídeo de escritorio y tableta de Windows

Lync 2013 presenta aceleración de hardware para la codificación y descodificación de vídeo basada en el estándar de codificación de vídeo avanzado H. 264/MPEG-4 parte 10. Esta característica permite a los equipos con menores velocidades de reloj de CPU codificar y descodificar vídeo de mayor resolución. Los requisitos de hardware de vídeo varían en función de la configuración del equipo y de la resolución de vídeo que se desea.

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
<th>Requirement</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Descodificación H.264 acelerada por hardware mediante DirectX Video Acceleration (DXVA)</p></td>
<td><ul>
<li><p>La tarjeta gráfica debe admitir DirectX 9.0 y debe exponer el modo de decodificación DXVA2_ModeH264_VLD_NoFGT.</p></li>
<li><p>Debe estar instalado el controlador de la tarjeta gráfica más reciente.</p></li>
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
<li><p>Conjuntos de chips Intel HD Graphics 2000, 2500, 3000 y 4000 de segunda y tercera generación (o versiones posteriores) con codificadores de vídeo de hardware integrados. Es necesario instalar el controlador de gráficos Intel HD 15.28.9.2884 o el último controlador que contenga lo siguiente:</p>
<ul>
<li><p>Controlador de pantalla 9.17.10.2884 o el controlador más reciente</p></li>
<li><p>Hardware Media Foundation Transform (HMFT) versión 3.12.10.31 o la última HMFT</p></li>
</ul></li>
</ul>
<p>Se admiten las siguientes soluciones de codificación de vídeo acelerada por hardware AMD (requiere actualizaciones de CU1 para Lync Server 2013):</p>
<ul>
<li><p>Procesador AMD video codec, que está disponible en varias tarjetas gráficas independientes y en unidades de procesamiento aceleradas integradas de procesadores acelerados AMD A-Series. Debe estar instalado el controlador del motor de códecs de vídeo AMD 9.12.0.0 o superior.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Codificación H.264 acelerada por hardware: requisitos de la cámara</p></td>
<td><p>Cámaras de vídeo USB con codificador de hardware H.264 integrado que cumplan la especificación USB Video Class (UVC) versión 1.5.</p>
<div>

> [!NOTE]  
> Lync 2013 admite cámaras UVC 1,5 con Windows 8 o Windows 8,1, que incluye compatibilidad con UVC 1,5. Como Windows 7 no incluye compatibilidad para UVC 1.5, Lync 2013 trata las cámaras UVC 1.5 como cámaras normales sin compatibilidad para codificación de hardware.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>Determinación de la capacidad de codificación y descodificación de vídeo H.264

Por lo general, son cuatro los factores principales que determinan la capacidad máxima de codificación y descodificación de una configuración de equipo determinada:

  - Compatibilidad para descodificación acelerada por hardware mediante DXVA

  - Compatibilidad para codificación acelerada por hardware

  - Número de núcleos físicos

  - Evaluación de la experiencia de Windows (WEI)

La Herramienta de evaluación del sistema de Windows (WinSAT) determina la WEI. Cuando ejecuta la herramienta de WinSAT, genera un documento XML formal. Assessment en el equipo en el directorio% WINDIR%\\performance\\de\\WinSAT de WinSAT. Este archivo XML contiene las siguientes dos puntuaciones que son especialmente importantes para determinar la capacidad de codificación y descodificación:

  - VideoEncodeScore indica la capacidad de codificación de vídeo basada en software del equipo.

  - El valor de GraphicsScore indica la capacidad de codificación acelerada por hardware del equipo.

Las siguientes tres tablas explican la capacidad máxima de codificación y descodificación de diferentes tipos de PC en función de la aceleración de hardware que admitan. Para resoluciones de 640x360 y superiores, la velocidad de fotogramas máxima admitida es de 30 fotogramas por segundo (fps). Para resoluciones inferiores a 640x360, la velocidad de fotogramas máxima admitida es de 15 fps.

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
<th>Requirement</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>424x240 (640x360 a 15 fps para escenarios solo de recepción)</p></td>
<td><p>1 núcleo y VideoEncodeScore ≥ 4,0</p></td>
</tr>
<tr class="even">
<td><p>640 x 360</p></td>
<td><p>640 x 360</p></td>
<td><p>2 núcleos y VideoEncodeScore = 4,5</p></td>
</tr>
<tr class="odd">
<td><p>640 x 360</p></td>
<td><p>1280x720</p></td>
<td><p>2 núcleos y VideoEncodeScore = 4,5</p></td>
</tr>
<tr class="even">
<td><p>640 x 360</p></td>
<td><p>1920</p></td>
<td><p>4 núcleos y VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1280x720</p></td>
<td><p>4 núcleos y VideoEncodeScore ≥ 7,3</p></td>
</tr>
<tr class="even">
<td><p>1280x720</p></td>
<td><p>1920</p></td>
<td><p>4 núcleos y VideoEncodeScore ≥ 7,3</p></td>
</tr>
<tr class="odd">
<td><p>1920</p></td>
<td><p>1920</p></td>
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
<th>Requirement</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>1920</p></td>
<td><p>1 núcleo y VideoEncodeScore ≥ 3,0</p></td>
</tr>
<tr class="even">
<td><p>640 x 360</p></td>
<td><p>1920</p></td>
<td><p>2 núcleos y VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>960x540</p></td>
<td><p>1920</p></td>
<td><p>2 núcleos y VideoEncodeScore ≥ 6,0</p></td>
</tr>
<tr class="even">
<td><p>1280x720</p></td>
<td><p>1920</p></td>
<td><p>4 núcleos y VideoEncodeScore ≥ 6,7</p></td>
</tr>
<tr class="odd">
<td><p>1920</p></td>
<td><p>1920</p></td>
<td><p>4 núcleos y VideoEncodeScore ≥ 8,2</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> La puntuación de WinSAT en Windows 7 se limita a un máximo de 7,9. Por lo tanto, la capacidad de codificación de un equipo sin un codificador acelerado por hardware solo se puede lograr en Windows 8 o Windows 8,1, donde la puntuación máxima de WinSAT es de 9,9.



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
<th>Requirement</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1920</p></td>
<td><p>Todos los modelos de Intel HD Graphics de segunda y tercera generación</p></td>
</tr>
<tr class="even">
<td><p>1920</p></td>
<td><p>1920</p></td>
<td><p>Todos los modelos de Intel HD Graphics de segunda y tercera generación y GraphicsScore ≥ 5,0</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a>Capacidades de vídeo de dispositivos móviles

En la tabla siguiente se describen las capacidades de vídeo máximas para los dispositivos móviles compatibles. Para obtener más información acerca de la compatibilidad de dispositivos móviles, consulte [Planning for Mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).


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
<td><p>Resolución máxima de codificación H. 264</p></td>
<td><p>VGA</p></td>
<td><p>QVGA: iPhone 4S</p>
<p>VGA: iPhone 5</p>
<p>720p: iPhone 5S y versiones posteriores</p></td>
<td><p>VGA: iPad 2 y posterior/iPad mini 1 y posterior</p>
<p>720p: dispositivo para iPad Air/iPad mini 2/iPad Pro y posterior</p></td>
<td><p>Hasta VGA en función del modelo de dispositivo</p></td>
</tr>
<tr class="even">
<td><p>Resolución máxima de codificación H. 264</p></td>
<td><p>VGA</p></td>
<td><p>QVGA: iPhone 4S</p>
<p>VGA: iPhone 5</p>
<p>720p: iPhone 5S y versiones posteriores</p></td>
<td><p>VGA: iPad 2 y posterior/iPad mini 1 y posterior</p>
<p>720p: dispositivo para iPad Air/iPad mini 2/iPad Pro y posterior</p></td>
<td><p>Hasta VGA en función del modelo de dispositivo</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

