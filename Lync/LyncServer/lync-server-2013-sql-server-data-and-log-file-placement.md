---
title: 'Lync Server 2013: SQL Ubicación de datos y de archivos de registro de SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a528ba7a348ebb5c8f865a795f8b1f1c1bc30cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a>Ubicación de datos y de archivos de registro de SQL Server para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Durante la planeación y la implementación de Microsoft SQL Server 2012 o Microsoft SQL Server 2008 R2 SP1 para su grupo front-end de Lync Server 2013, una consideración importante es la colocación de los datos y los archivos de registro en discos duros físicos para el rendimiento. La configuración de disco recomendada es implementar un conjunto de RAID 1 + 0 con 6 ejes. Colocar todos los archivos de base de datos y de registro usados por el grupo de servidores front-end y los roles y servicios de servidor asociados (es decir, servidor de archivado y supervisión, servicio de grupo de respuesta de Lync Server, servicio de estacionamiento de llamadas de Lync Server) en el conjunto de unidades RAID con el servidor de Lync. El Asistente para la implementación generará una configuración que se ha probado para un buen rendimiento. Los archivos de base de datos y su responsabilidad se detallan en la tabla siguiente.

<div>


> [!NOTE]  
> Si las directivas y la configuración de SQL Server requieren una instalación más especializada, la base de datos y los archivos de registro se pueden instalar en cualquier ubicación predefinida mediante el shell de administración de Lync Server. Para obtener más información, vea <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">instalación de bases de datos con el shell de administración de Lync Server en Lync server 2013</A> .



</div>

### <a name="data-and-log-files-for-central-management-store"></a>Archivos de datos y de registro para el almacén de administración central

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Archivos de base de datos de almacenamiento de administración central</th>
<th>Archivo de datos o propósito de registro</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XDS. ldf</p></td>
<td><p>Archivo de registro de transacciones para el almacén de administración central</p></td>
</tr>
<tr class="even">
<td><p>XDS. MDF</p></td>
<td><p>Mantiene la configuración de la topología actual de Lync Server 2013, definida y publicada por el generador de topologías</p></td>
</tr>
<tr class="odd">
<td><p>Lis. MDF</p></td>
<td><p>Archivo de datos del servicio de información de ubicación</p></td>
</tr>
<tr class="even">
<td><p>Lis. ldf</p></td>
<td><p>Registro de transacciones del archivo de datos del servicio de información de ubicación</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a>Archivos de datos y de registro para usuarios, conferencias y libretas de direcciones

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Archivos de base de datos básicos de Lync Server 2013</th>
<th>Archivo de datos o propósito de registro</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTC. MDF</p></td>
<td><p>Datos de usuario persistentes (por ejemplo, listas de control de acceso (ACL), contactos, conferencias programadas)</p></td>
</tr>
<tr class="even">
<td><p>RTC. ldf</p></td>
<td><p>Registro de transacciones de datos de RTC</p></td>
</tr>
<tr class="odd">
<td><p>RTCDyn. MDF</p></td>
<td><p>Mantiene datos de usuario transitorios (datos de presencia en tiempo de ejecución)</p></td>
</tr>
<tr class="even">
<td><p>RTCDyn. ldf</p></td>
<td><p>Registro de transacciones de datos de RTCDyn</p></td>
</tr>
<tr class="odd">
<td><p>Rtcab. MDF</p></td>
<td><p>La base de datos de la libreta de direcciones de las comunicaciones en tiempo real (RTC) es el repositorio de SQL Server donde se almacena la información del servicio de libreta de direcciones</p></td>
</tr>
<tr class="even">
<td><p>Rtcab. ldf</p></td>
<td><p>Registro de transacciones para el servicio de libreta de direcciones</p></td>
</tr>
<tr class="odd">
<td><p>Rtclocal. mdb</p></td>
<td><p>Hospeda el directorio de conferencia</p></td>
</tr>
<tr class="even">
<td><p>Rtcxds. MDF</p></td>
<td><p>Mantiene la copia de seguridad de los datos de usuario</p></td>
</tr>
<tr class="odd">
<td><p>Rtcxds. ldf</p></td>
<td><p>Registro de transacciones de datos de Rtcxds</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a>Archivos de datos y registro para el deestacionamiento de llamada y el grupo de respuesta

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Base de datos de la aplicación</th>
<th>Archivo de datos o propósito de registro</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cpsdyn. MDF</p></td>
<td><p>Base de datos de información dinámica para la aplicación de estacionamiento de llamadas</p></td>
</tr>
<tr class="even">
<td><p>Cpsdyn. ldf</p></td>
<td><p>Registro de transacciones para el archivo de datos de aplicación de estacionamiento de llamadas</p></td>
</tr>
<tr class="odd">
<td><p>Rgsconfig. MDF</p></td>
<td><p>Archivo de datos del servicio de grupo de respuesta de Lync Server para la configuración de los servicios</p></td>
</tr>
<tr class="even">
<td><p>Rgsconfig. ldf</p></td>
<td><p>Archivo de registro de transacciones para la configuración de la aplicación de grupo de respuesta</p></td>
</tr>
<tr class="odd">
<td><p>Rgsdyn. MDF</p></td>
<td><p>Archivo de datos de servicio de grupo de respuesta para operaciones en tiempo de ejecución</p></td>
</tr>
<tr class="even">
<td><p>Rgsdyn. ldf</p></td>
<td><p>Registro de transacciones para el archivo de datos de tiempo de ejecución del servicio de grupo de respuesta</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a>Archivos de datos y registro para el servidor de archivado y supervisión

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Archivar y supervisar archivos de base de datos</th>
<th>Archivo de datos o propósito de registro</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LcsCdr. MDF</p></td>
<td><p>Almacén de datos para el proceso de grabación de detalles de llamadas (CDR) del servidor de supervisión</p></td>
</tr>
<tr class="even">
<td><p>LcsCdr. ldf</p></td>
<td><p>Registro de transacciones para datos de grabación de detalles de llamadas (CDR)</p></td>
</tr>
<tr class="odd">
<td><p>QoEMetrics. MDF</p></td>
<td><p>Calidad de la experiencia archivo de datos almacenado desde el servidor de supervisión</p></td>
</tr>
<tr class="even">
<td><p>QoEMetrics. ldf</p></td>
<td><p>Registro de transacciones para supervisar datos</p></td>
</tr>
<tr class="odd">
<td><p>Lcslog. MDF</p></td>
<td><p>Archivo de datos para la retención de mensajes instantáneos y de conferencia en un servidor de archivado</p></td>
</tr>
<tr class="even">
<td><p>Lcslog. ldf</p></td>
<td><p>Registro de transacciones para archivar datos</p></td>
</tr>
</tbody>
</table>


En este tema, se hacen referencias al disco y al conjunto de RAID. Tenga en cuenta que en la configuración de los recursos de SQL Server, hacer referencia a un disco significa un único dispositivo de hardware. Una unidad de disco duro con dos particiones, una con archivos de registro y otra partición que contiene archivos de datos, no es la misma que dos discos, cada uno dedicado a archivos de datos o de registro.

En referencia a los conjuntos de RAID, hay varias tecnologías de RAID distintas de diferentes proveedores. Además, con la proliferación de redes de área de almacenamiento (SAN), los conjuntos RAID dedicados a un solo sistema son más separables. Debe consultar a su proveedor de RAID o SAN para determinar cuál es la mejor configuración para su diseño de disco al configurar el rendimiento de SQL Server con Lync Server 2013.

Tenga en cuenta también que no todas las unidades de disco se crean por igual; Algunos tienen mejor rendimiento que otros. Incluso las unidades del mismo fabricante pueden variar en rendimiento debido a la velocidad de giro, el tamaño de la caché de hardware y otros factores.

</div>

<span> </span>

</div>

</div>

</div>

