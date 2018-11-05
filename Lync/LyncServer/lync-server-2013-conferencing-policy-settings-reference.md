---
title: Referencia de configuración de directivas de conferencias en Lync Server 2013
TOCTitle: Referencia de configuración de directivas de conferencias en Lync Server 2013
ms:assetid: ec8125f7-ef78-4a2b-8db0-4dd3cf5a4065
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg429724(v=OCS.15)
ms:contentKeyID: 48277076
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Referencia de configuración de directivas de conferencias en Lync Server 2013

 

_**Última modificación del tema:** 2014-04-22_

En las tablas de este tema se enumeran todas las configuraciones de directivas de conferencias que puede especificar mediante Panel de control de Lync Server 2013.

## Configuración de la directiva de organizador

En la siguiente tabla se indican todas las configuraciones de directivas de conferencias que puede aplicar a los organizadores de conferencias. Si desea una lista actualizada de las directivas de conferencias, consulte el tema del cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy).

### Configuración de la directiva de organizador

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Configuración</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tamaño máximo de la reunión</p></td>
<td><p>Define el número máximo de participantes que se permite en una reunión.</p></td>
</tr>
<tr class="even">
<td><p>Permitir a los participantes invitar a usuarios anónimos</p></td>
<td><p>Permite a los organizadores de reuniones invitar a las reuniones a usuarios sin autenticar.</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar grabación</p></td>
<td><p>Permite a los moderadores o asistentes grabar la reunión.</p></td>
</tr>
<tr class="even">
<td><p>Permitir que graben los participantes federados y anónimos</p></td>
<td><p>Permite grabar la reunión a los participantes externos y sin autenticar.</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar audio IP</p></td>
<td><p>Permite el uso de audio en una reunión.</p></td>
</tr>
<tr class="even">
<td><p>Habilitar audio/vídeo IP</p></td>
<td><p>Permite el uso de audio y vídeo en una reunión.</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar conferencia de acceso telefónico local por RTC</p></td>
<td><p>Permite al usuario asistir a una reunión marcando el número desde la red telefónica conmutada (RTC).</p></td>
</tr>
<tr class="even">
<td><p>Permitir que los usuarios anónimos realicen llamadas salientes</p></td>
<td><p>Permite a los usuarios sin autenticar participar en una reunión realizando una llamada de salida. Mediante las llamadas de salida, el servidor de conferencia llama al usuario y este contesta el teléfono para participar en la reunión.</p></td>
</tr>
<tr class="odd">
<td><p>Resolución de vídeo máxima permitida para conferencias</p></td>
<td><p>Define la resolución máxima de las conferencias de vídeo. Los valores válidos son <strong>640*480(VGA)</strong> y <strong>352*288(CIF)</strong>.</p></td>
</tr>
<tr class="even">
<td><p>Habilitar colaboración de datos</p></td>
<td><p>Permite las conferencias web o conferencias con colaboración de datos.</p></td>
</tr>
<tr class="odd">
<td><p>Permitir que los usuarios federados y anónimos descarguen contenido</p></td>
<td><p>Permite que los participantes externos y sin autenticar descarguen contenido de la reunión.</p></td>
</tr>
<tr class="even">
<td><p>Permitir que los participantes transfieran archivos</p></td>
<td><p>Permite a los participantes de la reunión transferir archivos durante una reunión.</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar anotaciones</p></td>
<td><p>Permite a los participantes de la reunión crear anotaciones en el contenido.</p></td>
</tr>
<tr class="even">
<td><p>Habilitar sondeos</p></td>
<td><p>Permite a los participantes de la reunión realizar un sondeo durante una reunión.</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar el uso compartido de aplicaciones</p></td>
<td><p>Permite que los usuarios programen reuniones que admitan el uso compartido de aplicaciones.</p></td>
</tr>
<tr class="even">
<td><p>Permitir que los participantes tengan control</p></td>
<td><p>Permite a los participantes controlar la aplicación compartida de otro usuario.</p></td>
</tr>
<tr class="odd">
<td><p>Permitir que los participantes federados y anónimos tengan control</p></td>
<td><p>Permite a los participantes externos y anónimos controlar la aplicación compartida de otro usuario.</p>
<div>

> [!NOTE]
> Si se elige el valor True en esta opción y el valor False en <STRONG>Permitir que los participantes tengan control</STRONG>, no se tendrá en cuenta esta opción.


</div></td>
</tr>
</tbody>
</table>


## Configuración de directivas de participantes

La siguiente tabla indica todas las configuraciones de directivas de conferencias que puede aplicar a los participantes de conferencias.

### Configuración de directivas de participantes

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Configuración</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Habilitar el uso compartido de aplicaciones</p></td>
<td><p>Permite que los usuarios programen reuniones que admitan el uso compartido de aplicaciones.</p></td>
</tr>
<tr class="even">
<td><p>Habilitar uso compartido de aplicaciones y escritorios</p></td>
<td><p>Permite a los usuarios participar en reuniones que ofrecen la posibilidad de compartir aplicaciones y escritorios. En una conferencia, el valor de esta opción aplicado al organizador de la conferencia, se aplicará a todos los extremos anónimos que también participen.</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar transferencia de archivos punto a punto</p></td>
<td><p>Permite a los participantes realizar transferencias de archivos punto a punto durante una reunión. Las transferencias de archivos punto a punto no implican a todos los participantes de la reunión.</p></td>
</tr>
<tr class="even">
<td><p>Habilitar grabación punto a punto</p></td>
<td><p>Permite a los participantes grabar sesiones de conferencias punto a punto.</p></td>
</tr>
</tbody>
</table>

