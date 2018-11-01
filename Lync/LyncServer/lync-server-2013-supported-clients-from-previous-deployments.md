---
title: 'Lync Server 2013: Clientes admitidos de implementaciones anteriores'
TOCTitle: Clientes admitidos de implementaciones anteriores
ms:assetid: 69d427f8-57a5-4244-b2ed-f2eb7600285e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398499(v=OCS.15)
ms:contentKeyID: 48275581
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Clientes admitidos de implementaciones anteriores en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

En un escenario de coexistencia, los clientes de Lync Server 2013 pueden interactuar con clientes de versiones anteriores de Lync Server y Office Communications Server. A diferencia de las versiones anteriores, Lync Server 2010 es compatible con el nuevo cliente de Lync 2013, lo que permite que las organizaciones que se estén actualizando desde Lync Server 2010 lancen nuevos clientes independientemente de las actualizaciones de Lync Server.

## Combinaciones de servidor y cliente compatibles

La tabla siguiente muestra las combinaciones compatibles de versiones de cliente y versiones de servidor. Lync Server 2013 es compatible con dos versiones de cliente anteriores y Lync Server 2010 es compatible con el nuevo cliente de Lync 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Cliente</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
<td><p>No se admite</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2013</p></td>
<td><p>Compatible</p></td>
<td><p>No se admite</p></td>
<td><p>No se admite</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
<td><p>No se admite</p></td>
</tr>
<tr class="even">
<td><p>Operador de Lync 2010</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
<td><p>No se admite</p></td>
</tr>
<tr class="odd">
<td><p>Chat en grupo de Lync 2010</p></td>
<td><p>No aplicable</p></td>
<td><p>Compatible1</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2010</p></td>
<td><p>No se admite</p></td>
<td><p>Compatible</p></td>
<td><p>No se admite</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Attendee</p></td>
<td><p>No se admite2</p></td>
<td><p>Compatible</p></td>
<td><p>No se admite</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable3</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
</tr>
<tr class="odd">
<td><p>Operador de Microsoft Office Communications Server 2007 R2</p></td>
<td><p>No se admite</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007</p></td>
<td><p>No se admite</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
</tr>
<tr class="odd">
<td><p>Office Live Meeting 2007</p></td>
<td><p>No se admite</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
</tr>
</tbody>
</table>


1En Microsoft Lync Server 2010, la funcionalidad de chat en grupo estaba disponible con el servidor de chat en grupo, una aplicación de confianza de terceros para Lync Server 2010. Los clientes de Lync 2013 no son compatibles con Lync Server 2010, chat en grupo.

2Lync Web App 2013 proporciona ahora una experiencia completa de reunión que incluye audio y vídeo basados en el equipo, y se lo considera el sustituto de Lync 2010 Attendee.

3Las características de mensajería instantánea y presencia de Office Communicator 2007 R2 son compatibles con Lync Server 2013, pero las características de conferencia no lo son. Durante la migración desde Office Communications Server 2007 R2, Office Communicator 2007 R2 es adecuado para la interoperabilidad de mensajería instantánea y presencia, pero los usuarios deben usar Lync Web App 2013 para unirse a reuniones de Lync Server 2013.


> [!NOTE]
> Para obtener información sobre la capacidad de los clientes de Lync Server 2013 para coexistir e interactuar con clientes de versiones anteriores de Lync Server y Office Communications Server, consulte <A href="lync-server-2013-client-interoperability-in-lync-2013.md">Interoperabilidad de clientes en Lync 2013</A> en la documentación de planeación.


