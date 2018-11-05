---
title: 'Lync Server 2013: Ubicación de datos y de archivos de registro de SQL Server'
TOCTitle: Ubicación de datos y de archivos de registro de SQL Server
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48275510
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ubicación de datos y de archivos de registro de SQL Server para Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Durante la planeación e implementación de Microsoft SQL Server 2012 o Microsoft SQL Server 2008 R2 SP1 para Lync Server 2013  Grupo de servidores front-end, para lograr un buen rendimiento es importante tener en cuenta la selección de ubicación de los datos y archivos de registro en los discos duros físicos. La configuración de disco recomendada es implementar un conjunto de discos RAID 1+0 que use 6 cilindros. Si coloca todos los archivos de registro y de base de datos usados por el Grupo de servidores front-end y los servicios y roles de servidor asociados (es decir, Servidor de archivado y supervisión, Servicio de grupo de respuesta de Lync Server, Servicio de estacionamiento de llamadas de Lync Server) en el conjunto de discos RAID mediante la Asistente para la implementación de Lync Server, obtendrá una configuración cuyo buen rendimiento ya se ha probado. En la siguiente tabla se detallan los archivos de base de datos y sus correspondientes funciones.


> [!NOTE]
> Si sus directivas y configuraciones de SQL Server requieren una instalación más especializada, los archivos de registro y de base de datos se pueden instalar en cualquier ubicación predefinida mediante el Shell de administración de Lync Server. Consulte <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Instalación de la base de datos con el Shell de administración de Lync Server en Lync Server 2013</A> para obtener más detalles.



### Archivos de registro y de datos para el almacén de administración central

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Archivos de base de datos del Almacén de administración central</th>
<th>Finalidad del registro o archivo de datos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Xds.ldf</p></td>
<td><p>Archivo de registro de transacciones para el Almacén de administración central</p></td>
</tr>
<tr class="even">
<td><p>Xds.mdf</p></td>
<td><p>Mantiene la configuración de la topología Lync Server 2013 actual, según la define y publica Generador de topologías</p></td>
</tr>
<tr class="odd">
<td><p>Lis.mdf</p></td>
<td><p>Archivo de datos Servicio de información de ubicaciones</p></td>
</tr>
<tr class="even">
<td><p>Lis.ldf</p></td>
<td><p>Registro de transacciones para el archivo de datos de Servicio de información de ubicaciones</p></td>
</tr>
</tbody>
</table>


### Archivos de registro y de datos para el usuario, las conferencias y la libreta de direcciones

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Archivos de base de datos principales de Lync Server 2013</th>
<th>Finalidad del registro o archivo de datos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Rtc.mdf</p></td>
<td><p>Datos de usuario persistentes (por ejemplo, listas de control de acceso (ACL), contactos, conferencias programadas)</p></td>
</tr>
<tr class="even">
<td><p>Rtc.ldf</p></td>
<td><p>Registro de transacciones para datos Rtc</p></td>
</tr>
<tr class="odd">
<td><p>Rtcdyn.mdf</p></td>
<td><p>Mantiene datos de usuarios transitorios (datos de tiempo de ejecución de presencia)</p></td>
</tr>
<tr class="even">
<td><p>Rtcdyn.ldf</p></td>
<td><p>Registro de transacciones para datos Rtcdyn</p></td>
</tr>
<tr class="odd">
<td><p>Rtcab.mdf</p></td>
<td><p>La base de datos de la libreta de direcciones de las comunicaciones en tiempo real (RTC) es el repositorio de SQL Server cuando se almacena la información del servicio de libreta de direcciones</p></td>
</tr>
<tr class="even">
<td><p>Rtcab.ldf</p></td>
<td><p>Registro de transacciones para el servicio de libreta de direcciones</p></td>
</tr>
<tr class="odd">
<td><p>Rtclocal.mdb</p></td>
<td><p>Hospeda el directorio de conferencia</p></td>
</tr>
<tr class="even">
<td><p>Rtcxds.mdf</p></td>
<td><p>Mantiene la copia de seguridad de los datos de usuario</p></td>
</tr>
<tr class="odd">
<td><p>Rtcxds.ldf</p></td>
<td><p>Registro de transacciones para datos Rtcxds</p></td>
</tr>
</tbody>
</table>


### Archivos de registro y de datos para el estacionamiento de llamadas y el grupo de respuesta

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Base de datos de la aplicación</th>
<th>Finalidad del registro o archivo de datos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cpsdyn.mdf</p></td>
<td><p>Base de datos de información dinámica para la Aplicación de estacionamiento de llamadas</p></td>
</tr>
<tr class="even">
<td><p>Cpsdyn.ldf</p></td>
<td><p>Registro de transacciones para el archivo de datos de la Aplicación de estacionamiento de llamadas</p></td>
</tr>
<tr class="odd">
<td><p>Rgsconfig.mdf</p></td>
<td><p>Archivo de datos del servicio de grupo de respuesta de Lync Server para la configuración de los servicios</p></td>
</tr>
<tr class="even">
<td><p>Rgsconfig.ldf</p></td>
<td><p>Archivo de registro de transacciones para la configuración de la Aplicación de grupo de respuesta</p></td>
</tr>
<tr class="odd">
<td><p>Rgsdyn.mdf</p></td>
<td><p>Archivo de datos del servicio de grupo de respuesta para operaciones en tiempo de ejecución</p></td>
</tr>
<tr class="even">
<td><p>Rgsdyn.ldf</p></td>
<td><p>Registro de transacciones para el archivo de datos en tiempo de ejecución del servicio de grupo de respuesta</p></td>
</tr>
</tbody>
</table>


### Archivos de registro y de datos para el servidor de supervisión y archivado

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
<td><p>LcsCdr.mdf</p></td>
<td><p>Almacén de datos para el proceso de registro de detalles de llamadas (CDR) del Servidor de supervisión</p></td>
</tr>
<tr class="even">
<td><p>LcsCdr.ldf</p></td>
<td><p>Registro de transacciones para datos de registro de detalles de llamadas (CDR)</p></td>
</tr>
<tr class="odd">
<td><p>QoEMetrics.mdf</p></td>
<td><p>Archivo de datos de calidad de la experiencia almacenado desde el Servidor de supervisión</p></td>
</tr>
<tr class="even">
<td><p>QoEMetrics.ldf</p></td>
<td><p>Registro de transacciones para datos de supervisión</p></td>
</tr>
<tr class="odd">
<td><p>Lcslog.mdf</p></td>
<td><p>Archivo de datos para la conservación de los datos de mensajería instantánea y de conferencias en un Servidor de archivado</p></td>
</tr>
<tr class="even">
<td><p>Lcslog.ldf</p></td>
<td><p>Registro de transacciones para datos de archivado</p></td>
</tr>
</tbody>
</table>


En este tema, se hacen referencias al disco y al conjunto de discos RAID. Tenga en cuenta que en la configuración de recursos de SQL Server, un disco hace referencia a un único dispositivo de hardware. Una unidad de disco duro con dos particiones, una que contiene archivos de registro y otra que contiene archivos de datos, no es lo mismo que dos discos, cada uno de ellos dedicados a archivos de registro o de datos.

En referencia a conjuntos de discos RAID, existen varias tecnologías RAID diferentes de varios proveedores. Y, con la proliferación de redes de área de almacenamiento (SAN), los conjuntos de discos RAID dedicados a un único sistema son cada vez menos habituales. Deberá consultar a su proveedor de RAID o SAN para determinar cuál es la mejor configuración para su diseño de discos al configurar el rendimiento de SQL Server con Lync Server 2013.

Además, tenga en cuenta que no todas las unidades de disco se crean del mismo modo; algunas tienen mejor rendimiento que otras. Incluso las unidades del mismo fabricante pueden variar su rendimiento debido a la velocidad de rotación, el tamaño de la memoria caché en el hardware y otros factores.

