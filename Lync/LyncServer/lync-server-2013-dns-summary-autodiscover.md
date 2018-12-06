---
title: 'Resumen de DNS: detección automática en Lync Server 2013'
TOCTitle: 'Resumen de DNS: detección automática en Lync Server 2013'
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945644(v=OCS.15)
ms:contentKeyID: 52061755
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen de DNS: detección automática en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Detección automática es un servicio flexible en el que se aceptan comunicaciones mediante HTTP o HTTPS. Para hacer esto posible, el sistema de nombres de dominio (DNS) y los certificados que usan los servidores donde se hospeda el servicio Detección automática deben estar correctamente configurados. En [Resumen del certificado: detección automática](lync-server-2013-certificate-summary-autodiscover.md) se detallan los requisitos relativos a los certificados.

> [!IMPORTANT]  
> La lógica de las búsquedas DNS en los clientes de Lync Server usa un orden de resolución concreto. Siempre hay que incluir tanto lyncdiscoverinternal.&lt;dominio&gt; como lyncdiscover.&lt;dominio&gt; en el DNS. Si el registro de lyncdiscoverinternal.&lt;dominio&gt; se excluye, los clientes internos no podrán conectarse a los servicios que corresponda o recibirán una respuesta de Detección automática incorrecta.



### Registros DNS internos

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de registro</th>
<th>Nombre de host</th>
<th>Se resuelve en</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>Lyncdiscoverinternal.<em>&lt;nombre de dominio interno&gt;</em></p></td>
<td><p>FQDN de servicios web interno del Grupo de directores, si dispone de uno, o del Grupo de servidores front-end, si no dispone de un Director.</p></td>
</tr>
<tr class="even">
<td><p>A (host, si es IPv6, AAAA)</p></td>
<td><p>lyncdiscoverinternal.<em>&lt;nombre de dominio interno&gt;</em></p></td>
<td><p>Dirección IP de servicios web interna (dirección IP virtual [VIP], si usa un equilibrador de carga) del Grupo de directores, si dispone de uno, o del Grupo de servidores front-end, si no dispone de un Director</p></td>
</tr>
</tbody>
</table>


Cree uno de los siguientes registros DNS externos:

### Registros DNS externos

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de registro</th>
<th>Nombre de host</th>
<th>Se resuelve en</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>llyncdiscover. <em>&lt;dominiosip&gt;</em></p></td>
<td><p>FQDN de servicios web externo del Grupo de directores, si dispone de uno, o del Grupo de servidores front-end, si no dispone de un Director.</p></td>
</tr>
<tr class="even">
<td><p>A (host, si es IPv6, AAAA)</p></td>
<td><p>llyncdiscover. <em>&lt;dominiosip&gt;</em></p></td>
<td><p>Dirección IP externa o pública del proxy inverso.</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> El tráfico externo circula a través del proxy inverso.




> [!NOTE]
> Los clientes de dispositivos móviles no admiten varios certificados de capa de sockets seguros (SSL) de distintos dominios. Por lo tanto, la redirección de CNAME a distintos dominios no se admite a través de HTTPS. Por ejemplo, un registro CNAME de DNS para lyncdiscover.contoso.com que se redirige a una dirección de director.contoso.net no es posible a través de HTTPS. En una topología así, un cliente de dispositivo móvil necesita usar HTTP para la primera solicitud, de modo que la redirección de CNAME se resuelva a través de HTTP. A continuación, las solicitudes posteriores usan HTTPS. Para dar cabida a este escenario, debe configurar el proxy inverso con una regla de publicación web para el puerto 80 (HTTP). Para más información, vea "Para crear una regla de publicación web para el puerto 80" en <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuración del proxy inverso para movilidad en Lync Server 2013</A>. La redirección de CNAME al mismo dominio se admite a través de HTTPS. En este caso, el certificado del dominio de destino cubre el dominio original.



## Vea también

#### Tareas

[Configuración del proxy inverso para movilidad en Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  

#### Conceptos

[Resumen del certificado: detección automática](lync-server-2013-certificate-summary-autodiscover.md)

