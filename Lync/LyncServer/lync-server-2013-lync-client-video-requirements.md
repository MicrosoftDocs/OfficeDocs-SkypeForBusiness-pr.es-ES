---
title: "Skype Entreprise Server 2015 : conf. req. pr vidéo du client Skype Entreprise"
TOCTitle: Requisitos de vídeo del cliente de Lync
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49889379
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos de vídeo del cliente de Lync para Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Esta sección describe la compatibilidad de hardware de vídeo para videollamadas de Lync 2013 y describe cómo determinar la calidad de vídeo que se espera para las diferentes configuraciones del equipo, tableta o dispositivo móvil.

## Requisitos y capacidades de vídeo de escritorio de Windows y tabletas

Lync 2013 incorpora aceleración de hardware para la codificación y descodificación de vídeo basada en el estándar de codificación de vídeo avanzada H.264/MPEG-4, parte 10. Esta característica permite a los equipos con menores velocidades de reloj de CPU codificar y descodificar vídeo de mayor resolución. Los requisitos de hardware de vídeo varían en función de la configuración del equipo y de la resolución de vídeo que se desea.

## Requisitos de hardware de vídeo


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
<li><p>La tarjeta gráfica debe admitir DirectX 9.0 y debe exponer el modo de descodificación DXVA2_ModeH264_VLD_NoFGT.</p></li>
<li><p>Debe estar instalado el controlador de la tarjeta gráfica más reciente.</p></li>
</ul>
<div>

> [!NOTE]
> Para obtener información sobre los modos de descodificación, vea <A href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</A>.


</div></td>
</tr>
<tr class="even">
<td><p>Codificación H.264 acelerada por hardware: requisitos del conjunto de chips</p></td>
<td><p>Se admiten las siguientes soluciones de codificación de vídeo acelerada por hardware Intel:</p>
<ul>
<li><p>Conjuntos de chips Intel HD Graphics 2000, 2500, 3000 y 4000 de segunda y tercera generación (o versiones posteriores) con codificadores de vídeo de hardware integrados. Se requiere la instalación del controlador Intel HD Graphics 15.28.9.2884 o el controlador más reciente que contiene lo siguiente:</p>
<ul>
<li><p>Controlador de pantalla 9.17.10.2884 o el controlador más reciente</p></li>
<li><p>Hardware media foundation transform (HMFT) versión 3.12.10.31 o el HMFT más reciente</p></li>
</ul></li>
</ul>
<p>Se admiten las siguientes soluciones de codificación de vídeo acelerada por hardware AMD (se requieren actualizaciones CU1 para Lync Server 2013):</p>
<ul>
<li><p>AMD Video Codec Engine, que está disponible en varias tarjetas de gráficos independientes y en unidades de procesamiento acelerado integrado de procesadores acelerados de la serie AMD A. El controlador de AMD Video Codec Engine 9.12.0.0 o superior debe estar instalado.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Codificación H.264 acelerada por hardware: requisitos de la cámara</p></td>
<td><p>Cámaras de vídeo USB con codificador de hardware H.264 integrado que cumplan la especificación USB Video Class (UVC) versión 1.5.</p>
<div>

> [!NOTE]
> Lync 2013 admite cámaras UVC 1.5 con Windows 8 o Windows 8.1, que incluye compatibilidad para UVC 1.5. Como Windows 7 no incluye compatibilidad para UVC 1.5, Lync 2013 trata las cámaras UVC 1.5 como cámaras normales sin compatibilidad para codificación de hardware.


</div></td>
</tr>
<tr class="even">
<td><p>Descodificación H.264 acelerada por hardware mediante DirectX Video Acceleration (DXVA)</p></td>
<td><ul>
<li><p>La tarjeta gráfica debe admitir DirectX 9.0 y debe exponer el modo de descodificación DXVA2_ModeH264_VLD_NoFGT.</p></li>
<li><p>Debe estar instalado el controlador de la tarjeta gráfica más reciente.</p></li>
</ul>
<div>

> [!NOTE]
> Para obtener información sobre los modos de descodificación, vea <A href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</A>.


</div></td>
</tr>
<tr class="odd">
<td><p>Codificación H.264 acelerada por hardware: requisitos del conjunto de chips</p></td>
<td><p>Se admiten las siguientes soluciones de codificación de vídeo acelerada por hardware Intel:</p>
<ul>
<li><p>Conjuntos de chips Intel HD Graphics 2000, 2500, 3000 y 4000 de segunda y tercera generación (o versiones posteriores) con codificadores de vídeo de hardware integrados. Se requiere la instalación del controlador Intel HD Graphics 15.28.9.2884 o el controlador más reciente que contiene lo siguiente:</p>
<ul>
<li><p>Controlador de pantalla 9.17.10.2884 o el controlador más reciente</p></li>
<li><p>Hardware media foundation transform (HMFT) versión 3.12.10.31 o el HMFT más reciente</p></li>
</ul></li>
</ul>
<p>Se admiten las siguientes soluciones de codificación de vídeo acelerada por hardware AMD (se requieren actualizaciones CU1 para Lync Server 2013):</p>
<ul>
<li><p>AMD Video Codec Engine, que está disponible en varias tarjetas de gráficos independientes y en unidades de procesamiento acelerado integrado de procesadores acelerados de la serie AMD A. El controlador de AMD Video Codec Engine 9.12.0.0 o superior debe estar instalado.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Codificación H.264 acelerada por hardware: requisitos de la cámara</p></td>
<td><p>Cámaras de vídeo USB con codificador de hardware H.264 integrado que cumplan la especificación USB Video Class (UVC) versión 1.5.</p>
<div>

> [!NOTE]
> Lync 2013 admite cámaras UVC 1.5 con Windows 8 o Windows 8.1, que incluye compatibilidad para UVC 1.5. Como Windows 7 no incluye compatibilidad para UVC 1.5, Lync 2013 trata las cámaras UVC 1.5 como cámaras normales sin compatibilidad para codificación de hardware.


</div></td>
</tr>
</tbody>
</table>


## Determinación de la capacidad de codificación y descodificación de vídeo H.264

Por lo general, son cuatro los factores principales que determinan la capacidad máxima de codificación y descodificación de una configuración de equipo determinada:

  - Compatibilidad para descodificación acelerada por hardware mediante DXVA

  - Compatibilidad para codificación acelerada por hardware

  - Número de núcleos físicos

  - Evaluación de la experiencia de Windows (WEI)

La Herramienta de evaluación del sistema de Windows (WinSAT) determina la WEI. Cuando se ejecuta la herramienta WinSAT, genera un documento XML Formal.Assessment en el equipo, en el directorio %windir%\\Performance\\WinSAT\\DataStore. Este archivo XML contiene las siguientes dos puntuaciones que son especialmente importantes para determinar la capacidad de codificación y descodificación:

  - VideoEncodeScore indica la capacidad de codificación de vídeo basada en software del equipo.

  - El valor de GraphicsScore indica la capacidad de codificación acelerada por hardware del equipo.

Las siguientes tres tablas explican la capacidad máxima de codificación y descodificación de diferentes tipos de PC en función de la aceleración de hardware que admitan. Para resoluciones de 640x360 y superiores, la velocidad de fotogramas máxima admitida es de 30 fotogramas por segundo (fps). Para resoluciones inferiores a 640x360, la velocidad de fotogramas máxima admitida es de 15 fps.

### Equipo sin DXVA y sin codificador acelerado por hardware

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
<td><p>424x240 (640x360 a 15 fps para escenarios solo de recepción)</p></td>
<td><p>1 núcleo y VideoEncodeScore ≥ 4,0</p></td>
</tr>
<tr class="even">
<td><p>640 x 360</p></td>
<td><p>640 x 360</p></td>
<td><p>2 núcleos y VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>640 x 360</p></td>
<td><p>1280 x 720</p></td>
<td><p>2 núcleos y VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="even">
<td><p>640 x 360</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 núcleos y VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>1280 x 720</p></td>
<td><p>1280 x 720</p></td>
<td><p>4 núcleos y VideoEncodeScore ≥ 7,3</p></td>
</tr>
<tr class="even">
<td><p>1280 x 720</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 núcleos y VideoEncodeScore ≥ 7,3</p></td>
</tr>
<tr class="odd">
<td><p>1920 x 1080</p></td>
<td><p>1920 x 1080</p></td>
<td><p>N/D</p></td>
</tr>
<tr class="even">
<td><p>424 x 240</p></td>
<td><p>424x240 (640x360 a 15 fps para escenarios solo de recepción)</p></td>
<td><p>1 núcleo y VideoEncodeScore ≥ 4,0</p></td>
</tr>
<tr class="odd">
<td><p>640 x 360</p></td>
<td><p>640 x 360</p></td>
<td><p>2 núcleos y VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="even">
<td><p>640 x 360</p></td>
<td><p>1280 x 720</p></td>
<td><p>2 núcleos y VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>640 x 360</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 núcleos y VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="even">
<td><p>1280 x 720</p></td>
<td><p>1280 x 720</p></td>
<td><p>4 núcleos y VideoEncodeScore ≥ 7,3</p></td>
</tr>
<tr class="odd">
<td><p>1280 x 720</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 núcleos y VideoEncodeScore ≥ 7,3</p></td>
</tr>
<tr class="even">
<td><p>1920 x 1080</p></td>
<td><p>1920 x 1080</p></td>
<td><p>N/D</p></td>
</tr>
</tbody>
</table>


### Equipo con DXVA pero sin codificador acelerado por hardware

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
<td><p>1 núcleo y VideoEncodeScore ≥ 3,0</p></td>
</tr>
<tr class="even">
<td><p>640 x 360</p></td>
<td><p>1920 x 1080</p></td>
<td><p>2 núcleos y VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>960 x 540</p></td>
<td><p>1920 x 1080</p></td>
<td><p>2 núcleos y VideoEncodeScore ≥ 6,0</p></td>
</tr>
<tr class="even">
<td><p>1280 x 720</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 núcleos y VideoEncodeScore ≥ 6,7</p></td>
</tr>
<tr class="odd">
<td><p>1920 x 1080</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 núcleos y VideoEncodeScore ≥ 8,2</p></td>
</tr>
<tr class="even">
<td><p>424 x 240</p></td>
<td><p>1920 x 1080</p></td>
<td><p>1 núcleo y VideoEncodeScore ≥ 3,0</p></td>
</tr>
<tr class="odd">
<td><p>640 x 360</p></td>
<td><p>1920 x 1080</p></td>
<td><p>2 núcleos y VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="even">
<td><p>960 x 540</p></td>
<td><p>1920 x 1080</p></td>
<td><p>2 núcleos y VideoEncodeScore ≥ 6,0</p></td>
</tr>
<tr class="odd">
<td><p>1280 x 720</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 núcleos y VideoEncodeScore ≥ 6,7</p></td>
</tr>
<tr class="even">
<td><p>1920 x 1080</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 núcleos y VideoEncodeScore ≥ 8,2</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> La puntuación de WinSAT en Windows 7 está limitada a un máximo de 7,9. Por lo tanto, la capacidad de codificación de un equipo sin un codificador acelerado por hardware solo se puede lograr en Windows 8 o Windows 8.1, donde la puntuación máxima de WinSAT es de 9,9.



### Equipo con DXVA y con codificador acelerado por hardware Intel HD Graphics

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
<td><p>Todos los modelos de Intel HD Graphics de segunda y tercera generación y GraphicsScore ≥ 5,0</p></td>
</tr>
<tr class="odd">
<td><p>1280 x 720</p></td>
<td><p>1920 x 1080</p></td>
<td><p>Todos los modelos de Intel HD Graphics de segunda y tercera generación</p></td>
</tr>
<tr class="even">
<td><p>1920 x 1080</p></td>
<td><p>1920 x 1080</p></td>
<td><p>Todos los modelos de Intel HD Graphics de segunda y tercera generación y GraphicsScore ≥ 5,0</p></td>
</tr>
</tbody>
</table>


## Capacidades de vídeo de dispositivos móviles

La siguiente tabla describe las capacidades máximas de vídeo para los dispositivos móviles compatibles. Para obtener más información sobre la compatibilidad con dispositivos móviles, vea [Planeación de clientes móviles](lync-server-2013-planning-for-mobile-clients.md).


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Característica</th>
<th>Windows Phone</th>
<th>iPhone y iPad</th>
<th>Android</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Resolución máxima de codificación H.264</p></td>
<td><p>640 x 480</p></td>
<td><p>iPhone 4: 192 x 144</p>
<p>iPad y los demás modelos de iPhone admitidos: 352 x 288</p></td>
<td><p>320 x 2401</p></td>
</tr>
<tr class="even">
<td><p>Resolución máxima de descodificación H.264</p></td>
<td><p>640 x 480</p></td>
<td><p>iPhone y iPad: 352 x 288</p></td>
<td><p>320 x 2401</p></td>
</tr>
<tr class="odd">
<td><p>Resolución máxima de codificación H.264</p></td>
<td><p>640 x 480</p></td>
<td><p>iPhone 4: 192 x 144</p>
<p>iPad y los demás modelos de iPhone admitidos: 352 x 288</p></td>
<td><p>320 x 2401</p></td>
</tr>
<tr class="even">
<td><p>Resolución máxima de descodificación H.264</p></td>
<td><p>640 x 480</p></td>
<td><p>iPhone y iPad: 352 x 288</p></td>
<td><p>320 x 2401</p></td>
</tr>
</tbody>
</table>


1Para dispositivos Android con un procesador Qualcomm Snapdragon S3 o S4 y un conjunto de chips 8x60 se admite el envío y recepción con resolución 640 x 480.

