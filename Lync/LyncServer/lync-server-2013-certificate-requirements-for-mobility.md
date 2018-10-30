---
title: 'Lync Server 2013: Requisitos de certificado para movilidad'
TOCTitle: Requisitos de certificado para movilidad
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48276483
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos de certificado para movilidad en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Si implementa la característica de movilidad y admite la detección automática para clientes móviles, debe incluir algunas entradas de nombre alternativo del sujeto en certificados para admitir conexiones seguras desde clientes móviles.

Debe incluir entradas de nombre alternativo del sujeto para la detección automática en los siguientes certificados:

  - Grupo de directores

  - Grupo de servidores front-end

  - Proxy inverso

En esta sección se describen las entradas de nombre alternativo del sujeto necesarias en los certificados para la detección automática.


> [!NOTE]
> La reemisión de certificados usando una entidad de certificación interna suele ser un proceso sencillo, pero agregar varias entradas de nombre alternativo del sujeto a certificados públicos usados por el proxy inverso puede resultar caro. Si tiene muchos dominios SIP, lo que provoca que agregar nombres alternativos del sujeto sea caro, puede configurar el proxy inverso para usar HTTP para la solicitud inicial del servicio Detección automática, en lugar de usar HTTPS (la configuración predeterminada). Para más información, vea <A href="lync-server-2013-technical-requirements-for-mobility.md">Requisitos técnicos para la movilidad en Lync Server 2013</A>.



### Requisitos de certificado de grupo de directores

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descripción</th>
<th>Entrada de nombre alternativo del sujeto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL de servicio Detección automática interna</p></td>
<td><p>SAN=lyncdiscoverinternal.&lt;dominiosip&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL externa del servicio Detección automática</p></td>
<td><p>SAN=lyncdiscover.&lt;dominiosip&gt;</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> De manera alternativa, puede usar SAN=*.&lt;dominiosip&gt;



### Requisitos de certificado de grupo de servidores front-end

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descripción</th>
<th>Entrada de nombre alternativo del sujeto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL de servicio Detección automática interna</p></td>
<td><p>SAN=lyncdiscoverinternal.&lt;dominiosip&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL externa del servicio Detección automática</p></td>
<td><p>SAN=lyncdiscover.&lt;dominiosip&gt;</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> De manera alternativa, puede usar SAN=*.&lt;dominiosip&gt;



### Requisitos de certificado (CA pública) de proxy inverso

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descripción</th>
<th>Entrada de nombre alternativo del sujeto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL externa del servicio Detección automática</p></td>
<td><p>SAN=lyncdiscover.&lt;dominiosip&gt;</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Debe asignar este SAN al certificado asignado a la escucha de SSL en el proxy inverso.




> [!NOTE]
> El servicio de escucha del proxy inverso tendrá nombres alternativos del sujeto para las direcciones URL de servicios web externos (por ejemplo, SAN=lyncwebextpool01.contoso.com y dirwebexternal.contoso.com si implementó el Director opcional).


