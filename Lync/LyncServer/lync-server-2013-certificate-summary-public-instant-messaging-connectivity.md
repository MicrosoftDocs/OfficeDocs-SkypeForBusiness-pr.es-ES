---
title: Resumen de certificado - Conectividad de mensajería instantánea pública
TOCTitle: Resumen de certificado - Conectividad de mensajería instantánea pública
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49115276
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen de certificado - Conectividad de mensajería instantánea pública

 

_**Última modificación del tema:** 2015-03-09_

Para configurar certificados para conectividad de mensajería instantánea pública, primero debe comprender que no hay diferencia con otros tipos de federación SIP o incluso certificados de Servidor perimetral estándar, excepto que America Online (AOL) requiere una configuración de certificado única. Además del uso mejorado de clave (EKU) normal del servidor, America Online requiere que el certificado o los certificados (en el caso de un Grupo de servidores perimetrales) también incluyan el EKU del cliente. El EKU del cliente es un agregado del certificado y forma parte del certificado público externo asignado a su Servidor perimetral.

## Resumen del certificado: conectividad de mensajería instantánea pública


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
<th>Nombres alternativos de sujeto (SAN)/orden</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Externo/perimetral de acceso</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>El certificado debe provenir de una entidad de certificación pública y debe tener el EKU del servidor y el EKU del cliente si se implementará la conectividad de mensajería instantánea pública con AOL. El certificado se asigna a las interfaces externas de Servidor perimetral para:</p>
<ul>
<li><p>Servidor perimetral de acceso</p></li>
<li><p>Servicio perimetral de conferencia web</p></li>
<li><p>Servicio perimetral A/V</p></li>
</ul>
<p>Tenga en cuenta que los SAN se agregan automáticamente al certificado en función de sus definiciones del Generador de topologías. Puede agregar entradas de SAN a medida que lo necesite para otros dominios SIP y otras entradas que deba admitir. El nombre de sujeto se replica en el SAN y debe estar presente para un correcto funcionamiento.</p></td>
</tr>
</tbody>
</table>


## Vea también

#### Conceptos

[Escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)

