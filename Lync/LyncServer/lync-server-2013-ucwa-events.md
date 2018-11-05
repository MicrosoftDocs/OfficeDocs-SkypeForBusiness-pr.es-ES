---
title: Eventos de UCWA
TOCTitle: Eventos de UCWA
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945621(v=OCS.15)
ms:contentKeyID: 52061612
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eventos de UCWA

 

_**Última modificación del tema:** 2015-03-09_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 usa la API web de comunicaciones unificadas (UCWA) para una gran cantidad de propósitos, desde el acceso a Microsoft Exchange para realizar búsquedas de contactos hasta la actualización del estado de presencia de los clientes móviles.

UCWA escribirá los registros del comportamiento operativo como tipos de evento informativos, de advertencia y de error. En la siguiente tabla se describen los eventos que pueden escribir los componentes de UCWA.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Id. del evento</th>
<th>Tipo de evento</th>
<th>Resumen</th>
<th>Causa y solución</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>20001</p></td>
<td><p>Informativo</p></td>
<td><p>Se inicializó UCWA</p></td>
<td><p>N/A</p>
<p>N/A</p></td>
</tr>
<tr class="even">
<td><p>20002</p></td>
<td><p>Error</p></td>
<td><p>UCWA encontró una excepción inesperada durante la inicialización</p></td>
<td><p>Se produjo un error inesperado durante la inicialización</p>
<p>Examine los detalles de la excepción en la entrada del registro de eventos asociada para determinar la posible causa</p></td>
</tr>
<tr class="odd">
<td><p>20003</p></td>
<td><p>Error</p></td>
<td><p>UCWA encontró una excepción no controlada</p></td>
<td><p>Se produjo una excepción no controlada</p>
<p>Reinicie el servidor. Si persiste el problema, póngase en contacto con el soporte técnico</p></td>
</tr>
<tr class="even">
<td><p>20004</p></td>
<td><p>Error</p></td>
<td><p>No se puede acceder a Exchange para fotos HD</p></td>
<td><p>La conexión a Exchange no está disponible</p>
<p>Asegúrese de que la conexión a Exchange esté disponible</p></td>
</tr>
<tr class="odd">
<td><p>20005</p></td>
<td><p>Informativo</p></td>
<td><p>Se recuperó el acceso a Exchange para fotos HD</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>20006</p></td>
<td><p>Error</p></td>
<td><p>No se puede acceder a Exchange para la búsqueda de contactos</p></td>
<td><p>La conexión a Exchange no está disponible</p>
<p>Asegúrese de que la conexión a Exchange esté disponible</p></td>
</tr>
<tr class="odd">
<td><p>20007</p></td>
<td><p>Informativo</p></td>
<td><p>Se recuperó el acceso a Exchange para la búsqueda de contactos</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>20008</p></td>
<td><p>Advertencia</p></td>
<td><p>Se intentó un número de suscripciones de presencia mayor que el permitido por aplicación</p></td>
<td><p>Se intentó un número de suscripciones de presencia mayor que el permitido por aplicación</p>
<p>Compruebe los clientes para determinar las suscripciones innecesarias</p></td>
</tr>
<tr class="odd">
<td><p>20009</p></td>
<td><p>Advertencia</p></td>
<td><p>Se intentó un número de suscripciones de presencia mayor que el permitido por lote</p></td>
<td><p>Se intentó un número de suscripciones de presencia mayor que el permitido por lote</p>
<p>Compruebe los clientes para determinar las suscripciones innecesarias</p></td>
</tr>
<tr class="even">
<td><p>20010</p></td>
<td><p>Error</p></td>
<td><p>No se pueden recuperar los datos en banda</p></td>
<td><p>No se pueden recuperar los datos en banda</p>
<p>Si persiste el problema, póngase en contacto con el soporte técnico</p></td>
</tr>
<tr class="odd">
<td><p>20011</p></td>
<td><p>Error</p></td>
<td><p>No se puede suscribir la presencia</p></td>
<td><p>No se puede suscribir la presencia</p>
<p>Si persiste el problema, póngase en contacto con el soporte técnico</p></td>
</tr>
<tr class="even">
<td><p>20012</p></td>
<td><p>Error</p></td>
<td><p>Error al registrar el extremo</p></td>
<td><p>Error al registrar el extremo</p>
<p>Si persiste el problema, póngase en contacto con el soporte técnico</p></td>
</tr>
<tr class="odd">
<td><p>20013</p></td>
<td><p>Error</p></td>
<td><p>La MCU de mensajería instantánea no está disponible</p></td>
<td><p>La MCU de mensajería instantánea no está disponible</p>
<p>Compruebe si la MCU de mensajería instantánea se está ejecutando</p></td>
</tr>
<tr class="even">
<td><p>20014</p></td>
<td><p>Informativo</p></td>
<td><p>Se recuperó la conexión a la MCU de mensajería instantánea</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>20015</p></td>
<td><p>Error</p></td>
<td><p>La MCU de audio y vídeo no está disponible</p></td>
<td><p>La MCU de audio y vídeo no está disponible</p>
<p>Compruebe si la MCU de audio y vídeo se está ejecutando</p></td>
</tr>
<tr class="even">
<td><p>20016</p></td>
<td><p>Informativo</p></td>
<td><p>Se recuperó la conexión a la MCU de audio y vídeo</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>20017</p></td>
<td><p>Error</p></td>
<td><p>La MCU de AS no está disponible</p></td>
<td><p>La MCU de AS no está disponible</p>
<p>Compruebe si la MCU de AS se está ejecutando</p></td>
</tr>
<tr class="even">
<td><p>20018</p></td>
<td><p>Informativo</p></td>
<td><p>Se recuperó la conexión a la MCU de AS</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>20019</p></td>
<td><p>Error</p></td>
<td><p>La MCU de datos no está disponible</p></td>
<td><p>La MCU de datos no está disponible</p>
<p>Compruebe si la MCU de datos se está ejecutando</p></td>
</tr>
<tr class="even">
<td><p>20020</p></td>
<td><p>Informativo</p></td>
<td><p>Se recuperó la conexión a la MCU de datos</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>20021</p></td>
<td><p>Error</p></td>
<td><p>No se puede conectar la MCU de mensajería instantánea</p></td>
<td><p>No se puede conectar la MCU de mensajería instantánea</p>
<p>Compruebe si la MCU de mensajería instantánea se está ejecutando</p></td>
</tr>
<tr class="even">
<td><p>20022</p></td>
<td><p>Error</p></td>
<td><p>No se puede conectar la MCU de audio y vídeo</p></td>
<td><p>No se puede conectar la MCU de audio y vídeo</p>
<p>Compruebe si la MCU de audio y vídeo se está ejecutando</p></td>
</tr>
<tr class="odd">
<td><p>20023</p></td>
<td><p>Error</p></td>
<td><p>No se puede conectar la MCU de AS</p></td>
<td><p>No se puede conectar la MCU de AS</p>
<p>Compruebe si la MCU de AS se está ejecutando</p></td>
</tr>
<tr class="even">
<td><p>20024</p></td>
<td><p>Error</p></td>
<td><p>No se puede conectar la MCU de datos</p></td>
<td><p>No se puede conectar la MCU de datos</p>
<p>Compruebe si la MCU de datos se está ejecutando</p></td>
</tr>
<tr class="odd">
<td><p>20025</p></td>
<td><p>Error</p></td>
<td><p>No se puede acceder a Active Directory para las fotos</p></td>
<td><p>La conexión a Active Directory no está disponible</p>
<p>Asegúrese de que la conexión a Active Directory esté disponible</p></td>
</tr>
<tr class="even">
<td><p>20026</p></td>
<td><p>Informativo</p></td>
<td><p>Se recuperó el acceso a Active Directory para las fotos</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>20027</p></td>
<td><p>Advertencia</p></td>
<td><p>No se puede deserializar</p></td>
<td><p>No se puede deserializar</p>
<p>Si persiste el problema, póngase en contacto con el soporte técnico</p></td>
</tr>
</tbody>
</table>

