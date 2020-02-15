---
title: 'Lync Server 2013: eventos de UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d42dbd967f90b6e2a905b92558c88fe52ef62d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a>Eventos de UCWA en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-15_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 usa la API Web de comunicaciones unificadas (UCWA) para una serie de propósitos, desde el acceso a Microsoft Exchange para las búsquedas de contactos hasta la actualización de presencia para los clientes móviles.

UCWA escribirá los registros de comportamiento operativo como tipos de evento informativos, de advertencia y de error. En la tabla siguiente se describen los eventos que pueden escribir los componentes de UCWA.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Id. de evento</th>
<th>Tipo de evento</th>
<th>Resumen</th>
<th>Causa y solución</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>20001</p></td>
<td><p>Informativo</p></td>
<td><p>UCWA inicializado</p></td>
<td><p>N/D</p>
<p>N/D</p></td>
</tr>
<tr class="even">
<td><p>20002</p></td>
<td><p>Error</p></td>
<td><p>UCWA encontró una excepción inesperada durante la inicialización</p></td>
<td><p>Se ha producido un error inesperado durante la inicialización</p>
<p>Examine los detalles de la excepción en la entrada del registro de eventos asociada para determinar la causa posible</p></td>
</tr>
<tr class="odd">
<td><p>20003</p></td>
<td><p>Error</p></td>
<td><p>UCWA encontró una excepción no controlada.</p></td>
<td><p>Se ha producido una excepción no controlada</p>
<p>Reinicie el servidor. Si el problema continúa, póngase en contacto con el soporte técnico</p></td>
</tr>
<tr class="even">
<td><p>20004</p></td>
<td><p>Error</p></td>
<td><p>No se puede tener acceso a Exchange para fotos HD</p></td>
<td><p>La conexión con Exchange no está disponible</p>
<p>Asegurarse de que la conexión a Exchange está disponible</p></td>
</tr>
<tr class="odd">
<td><p>20005</p></td>
<td><p>Informativo</p></td>
<td><p>Se recuperó el acceso a Exchange para fotos HD</p></td>
<td><p>N/D</p></td>
</tr>
<tr class="even">
<td><p>20006</p></td>
<td><p>Error</p></td>
<td><p>No se puede obtener acceso a Exchange para la búsqueda de contactos</p></td>
<td><p>La conexión con Exchange no está disponible</p>
<p>Asegurarse de que la conexión a Exchange está disponible</p></td>
</tr>
<tr class="odd">
<td><p>20007</p></td>
<td><p>Informativo</p></td>
<td><p>Se recuperó del error de búsqueda en el contacto de Exchange</p></td>
<td><p>N/D</p></td>
</tr>
<tr class="even">
<td><p>20008</p></td>
<td><p>Advertencia</p></td>
<td><p>Intento de suscribir más de las suscripciones de presencia permitidas por aplicación</p></td>
<td><p>Intento de suscribir más de las suscripciones de presencia permitidas por aplicación</p>
<p>Comprobar si los clientes tienen suscripciones innecesarias</p></td>
</tr>
<tr class="odd">
<td><p>20009</p></td>
<td><p>Advertencia</p></td>
<td><p>Intento de suscribir más de las suscripciones de presencia permitidas por lote</p></td>
<td><p>Intento de suscribir más de las suscripciones de presencia permitidas por lote</p>
<p>Comprobar si los clientes tienen suscripciones innecesarias</p></td>
</tr>
<tr class="even">
<td><p>20010</p></td>
<td><p>Error</p></td>
<td><p>No se pueden recuperar los datos en banda</p></td>
<td><p>No se pueden recuperar los datos en banda</p>
<p>Si el problema continúa, póngase en contacto con el soporte técnico</p></td>
</tr>
<tr class="odd">
<td><p>20011</p></td>
<td><p>Error</p></td>
<td><p>No se puede suscribir la presencia</p></td>
<td><p>No se puede suscribir la presencia</p>
<p>Si el problema continúa, póngase en contacto con el soporte técnico</p></td>
</tr>
<tr class="even">
<td><p>20012</p></td>
<td><p>Error</p></td>
<td><p>No se pudo registrar el extremo</p></td>
<td><p>No se pudo registrar el extremo</p>
<p>Si el problema continúa, póngase en contacto con el soporte técnico</p></td>
</tr>
<tr class="odd">
<td><p>20013</p></td>
<td><p>Error</p></td>
<td><p>La MCU de mensajería instantánea no está disponible</p></td>
<td><p>La MCU de mensajería instantánea no está disponible</p>
<p>Ver si la MCU de mensajería instantánea se está ejecutando</p></td>
</tr>
<tr class="even">
<td><p>20014</p></td>
<td><p>Informativo</p></td>
<td><p>Se recuperó el error de conexión a la MCU de mensajería instantánea</p></td>
<td><p>N/D</p></td>
</tr>
<tr class="odd">
<td><p>20015</p></td>
<td><p>Error</p></td>
<td><p>La MCU antivirus no está disponible</p></td>
<td><p>La MCU antivirus no está disponible</p>
<p>Ver si la MCU AV está en funcionamiento</p></td>
</tr>
<tr class="even">
<td><p>20016</p></td>
<td><p>Informativo</p></td>
<td><p>Se recuperó la conexión a un MCU AV</p></td>
<td><p>N/D</p></td>
</tr>
<tr class="odd">
<td><p>20017</p></td>
<td><p>Error</p></td>
<td><p>COMO la MCU no está disponible</p></td>
<td><p>COMO la MCU no está disponible</p>
<p>Ver si se está ejecutando la MCU</p></td>
</tr>
<tr class="even">
<td><p>20018</p></td>
<td><p>Informativo</p></td>
<td><p>Se recuperó el error de conexión a como MCU</p></td>
<td><p>N/D</p></td>
</tr>
<tr class="odd">
<td><p>20019</p></td>
<td><p>Error</p></td>
<td><p>La MCU de datos no está disponible</p></td>
<td><p>La MCU de datos no está disponible</p>
<p>Ver si Data MCU se está ejecutando</p></td>
</tr>
<tr class="even">
<td><p>20020</p></td>
<td><p>Informativo</p></td>
<td><p>Se recuperó el error de conexión a la MCU de datos</p></td>
<td><p>N/D</p></td>
</tr>
<tr class="odd">
<td><p>20021</p></td>
<td><p>Error</p></td>
<td><p>No se puede unir a mi MCU</p></td>
<td><p>No se puede unir a mi MCU</p>
<p>Ver si la MCU de mensajería instantánea se está ejecutando</p></td>
</tr>
<tr class="even">
<td><p>20022</p></td>
<td><p>Error</p></td>
<td><p>No se puede unir a AV MCU</p></td>
<td><p>No se puede unir a AV MCU</p>
<p>Ver si la MCU AV está en funcionamiento</p></td>
</tr>
<tr class="odd">
<td><p>20023</p></td>
<td><p>Error</p></td>
<td><p>No se puede unir como MCU</p></td>
<td><p>No se puede unir como MCU</p>
<p>Ver si se está ejecutando la MCU</p></td>
</tr>
<tr class="even">
<td><p>20024</p></td>
<td><p>Error</p></td>
<td><p>No se puede unir datos MCU</p></td>
<td><p>No se puede unir datos MCU</p>
<p>Ver si Data MCU se está ejecutando</p></td>
</tr>
<tr class="odd">
<td><p>20025</p></td>
<td><p>Error</p></td>
<td><p>No se puede obtener acceso a Active Directory para fotos</p></td>
<td><p>La conexión a Active Directory no está disponible</p>
<p>Asegurarse de que la conexión a Active Directory está disponible</p></td>
</tr>
<tr class="even">
<td><p>20026</p></td>
<td><p>Informativo</p></td>
<td><p>Se recuperó el acceso a Active Directory para la foto</p></td>
<td><p>N/D</p></td>
</tr>
<tr class="odd">
<td><p>20027</p></td>
<td><p>Advertencia</p></td>
<td><p>No se puede deserializar</p></td>
<td><p>No se puede deserializar</p>
<p>Si el problema continúa, póngase en contacto con el soporte técnico</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

