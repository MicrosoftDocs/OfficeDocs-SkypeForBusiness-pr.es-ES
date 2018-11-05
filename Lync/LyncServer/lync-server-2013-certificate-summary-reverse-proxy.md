---
title: 'Lync Server 2013: Resumen de certificado - Proxy inverso'
TOCTitle: Resumen de certificado - Proxy inverso
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48277154
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen de certificado - Proxy inverso en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Los requisitos de certificado para el proxy inverso son mucho más simples que los de los Servidores perimetrales. El diagrama de flujo proporcionado muestra los requisitos necesarios. La tabla muestra un nombre de sujeto típico para un certificado y nombres alternativos de sujetos relacionados con los escenarios que se revisaron en las discusiones sobre el Servidor perimetral. Para obtener información detallada sobre los escenarios de Servidor perimetral, vea: [Escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**Diagrama de flujo de certificados para proxy inverso**

![Diagrama de flujo de certificados para servidor perimetral](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Diagrama de flujo de certificados para servidor perimetral")

### Proxy inverso: Interfaz externa

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente</th>
<th>Nombre de sujeto</th>
<th>Nombre alternativo del sujeto (SAN)/orden</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Proxy inverso</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>webext.contoso.com</p>
<p>webdirext.contoso.com</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>officewebapps01.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(Opcional): *.contoso.com</p></td>
<td><p>Una entidad emisora de certificados debe otorgar el certificado junto con el servidor EKU. Los servicios incluyen el servicio de Libreta de direcciones, Office Web Apps de expansión del grupo de distribución y las reglas de publicación del dispositivo IP de Lync. Los nombres alternativos del firmante incluyen:</p>
<ul>
<li><p>FQDN de servicios web externos para el Servidor front-end o el Grupo de servidores front-end</p></li>
<li><p>FQDN de servicios web externos para el Director o el Grupo de directores</p></li>
<li><p>Conferencia de acceso telefónico local</p></li>
<li><p>Regla de publicación de reunión en línea</p></li>
<li><p>Office Web Apps para conferencias</p></li>
<li><p>Lyncdiscover (Detección automática)</p></li>
</ul>
<p>El carácter comodín opcional sustituye tanto la SAN de reuniones, como de marcado</p></td>
</tr>
</tbody>
</table>

