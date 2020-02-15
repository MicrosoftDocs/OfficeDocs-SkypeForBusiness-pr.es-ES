---
title: 'Lync Server 2013: ubicación de los archivos de registro y datos de SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b15af558ed6082d28b7ae918d72dd7da94b1e499
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a>Ubicación de los archivos de registro y datos de SQL Server para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Durante la planeación y la implementación de Microsoft SQL Server 2012 o Microsoft SQL Server 2008 R2 SP1 para el grupo de servidores front-end de Lync Server 2013, una consideración importante es la colocación de los datos y los archivos de registro en discos duros físicos para el rendimiento. La configuración de disco recomendada es implementar un conjunto de RAID 1 + 0 con 6 ejes. Colocar todos los archivos de base de datos y registro que usan el grupo de servidores front-end y los roles y servicios asociados del servidor (es decir, el servidor de archivado y supervisión, el servicio de grupo de respuesta de Lync Server, el servicio de estacionamiento de llamadas de Lync Server) en el conjunto de unidades RAID mediante Lync Server. El Asistente para la implementación dará como resultado una configuración que se ha probado para obtener un buen rendimiento. En la siguiente tabla se detallan los archivos de base de datos y las funciones de las que son responsables.

<div>


> [!NOTE]  
> Si las directivas y las configuraciones de SQL Server requieren una instalación más especializada, los archivos de registro y de base de datos se pueden instalar en cualquier ubicación predefinida mediante el shell de administración de Lync Server. Consulte <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">instalación de bases de datos mediante el shell de administración de Lync Server en Lync server 2013</A> para obtener más información.



</div>

### <a name="data-and-log-files-for-central-management-store"></a>Archivos de registro y de datos para el almacén de administración central

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Archivos de base de datos de almacén de administración central</th>
<th>Finalidad del registro o archivo de datos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XDS. ldf</p></td>
<td><p>Archivo de registro de transacciones para el almacén de administración central</p></td>
</tr>
<tr class="even">
<td><p>XDS. MDF</p></td>
<td><p>Mantiene la configuración de la topología actual de Lync Server 2013, tal y como se ha definido y publicado por el generador de topologías.</p></td>
</tr>
<tr class="odd">
<td><p>Lis. MDF</p></td>
<td><p>Archivo de datos del servicio de información de ubicación</p></td>
</tr>
<tr class="even">
<td><p>Lis. ldf</p></td>
<td><p>Registro de transacciones para el archivo de datos del servicio de información de ubicación</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a>Archivos de registro y de datos para el usuario, las conferencias y la libreta de direcciones

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Principales archivos de base de datos de Lync Server 2013</th>
<th>Finalidad del registro o archivo de datos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTC. MDF</p></td>
<td><p>Datos de usuario persistentes (por ejemplo, listas de control de acceso (ACL), contactos, conferencias programadas)</p></td>
</tr>
<tr class="even">
<td><p>RTC. ldf</p></td>
<td><p>Registro de transacciones para datos RTC</p></td>
</tr>
<tr class="odd">
<td><p>RTCDyn. MDF</p></td>
<td><p>Mantiene datos de usuario transitorios (datos de tiempo de ejecución de presencia)</p></td>
</tr>
<tr class="even">
<td><p>RTCDyn. ldf</p></td>
<td><p>Registro de transacciones para datos de RTCDyn</p></td>
</tr>
<tr class="odd">
<td><p>Rtcab. MDF</p></td>
<td><p>La base de datos de la libreta de direcciones de las comunicaciones en tiempo real (RTC) es el repositorio de SQL Server cuando se almacena la información del servicio de libreta de direcciones</p></td>
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
<td><p>Registro de transacciones para datos de Rtcxds</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a>Archivos de registro y de datos para el estacionamiento de llamadas y el grupo de respuesta

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Base de datos de aplicación</th>
<th>Finalidad del registro o archivo de datos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cpsdyn. MDF</p></td>
<td><p>Base de datos de información dinámica para la aplicación estacionamiento de llamadas</p></td>
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
<td><p>Archivo de registro de transacciones para la configuración de la aplicación del grupo de respuesta</p></td>
</tr>
<tr class="odd">
<td><p>Rgsdyn. MDF</p></td>
<td><p>Archivo de datos del servicio de grupo de respuesta para operaciones en tiempo de ejecución</p></td>
</tr>
<tr class="even">
<td><p>Rgsdyn. ldf</p></td>
<td><p>Registro de transacciones para el archivo de datos en tiempo de ejecución del servicio de grupo de respuesta</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a>Archivos de registro y de datos para el servidor de supervisión y archivado

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Archivos de la base de datos de supervisión y archivado</th>
<th>Finalidad del registro o archivo de datos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LcsCdr. MDF</p></td>
<td><p>Almacén de datos para el proceso de registro de detalles de llamadas (CDR) del servidor de supervisión</p></td>
</tr>
<tr class="even">
<td><p>LcsCdr. ldf</p></td>
<td><p>Registro de transacciones para datos de registro de detalles de llamadas (CDR)</p></td>
</tr>
<tr class="odd">
<td><p>QoEMetrics. MDF</p></td>
<td><p>Archivo de datos de calidad de la experiencia almacenado desde el servidor de supervisión</p></td>
</tr>
<tr class="even">
<td><p>QoEMetrics. ldf</p></td>
<td><p>Registro de transacciones para datos de supervisión</p></td>
</tr>
<tr class="odd">
<td><p>Lcslog. MDF</p></td>
<td><p>Archivo de datos para la retención de los datos de mensajería instantánea y de conferencias en un servidor de archivado</p></td>
</tr>
<tr class="even">
<td><p>Lcslog. ldf</p></td>
<td><p>Registro de transacciones para datos de archivado</p></td>
</tr>
</tbody>
</table>


En este tema, se hacen referencias al disco y al conjunto de discos RAID. Tenga en cuenta que en la configuración de recursos de SQL Server, un disco hace referencia a un único dispositivo de hardware. Una unidad de disco duro con dos particiones, una que contiene archivos de registro y otra que contiene archivos de datos, no es lo mismo que dos discos, cada uno de ellos dedicados a archivos de registro o de datos.

En referencia a conjuntos de discos RAID, existen varias tecnologías RAID diferentes de varios proveedores. Y, con la proliferación de redes de área de almacenamiento (SAN), los conjuntos de discos RAID dedicados a un único sistema son cada vez menos habituales. Debe consultar a su proveedor de RAID o SAN para determinar cuál es la mejor configuración para su diseño de disco al configurar el rendimiento de SQL Server con Lync Server 2013.

Además, tenga en cuenta que no todas las unidades de disco se crean del mismo modo; unas rinden mejor que otras. Incluso las unidades del mismo fabricante pueden variar su rendimiento debido a la velocidad de rotación, el tamaño de la memoria caché en el hardware y otros factores.

</div>

<span> </span>

</div>

</div>

</div>

