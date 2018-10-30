---
title: 'Lync Server 2013: Resumen de certificado - Director único'
TOCTitle: Resumen de certificado - Director único
ms:assetid: 1b769a76-cbf3-46e9-a955-f6cde5faff93
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204720(v=OCS.15)
ms:contentKeyID: 48274590
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen de certificado - Director único en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Los requisitos de certificado para un único Director consisten en un certificado predeterminado que tiene un nombre de sujeto y nombres alternativos de sujeto para servicios que el Director puede recibir. Asimismo, existe un certificado OAuth Token para fines de autenticación de servidor a servidor.

### Certificados para el director

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
<th>Nombres alternativos del firmante (SAN)</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Valor predeterminado</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>dir01.contoso.net</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>lyncdiscoverinternal.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(Opcionalmente) *.contoso.com</p></td>
<td><p>Los certificados de Director pueden solicitarse de una entidad de certificación (CA) administrada internamente o de una entidad de certificación pública.</p>
<p>El Director responde a las solicitudes del servidor proxy inverso en el perímetro o desde el Servidor perimetral. Los clientes internos no utilizarán el Director.</p>
<p>O una entrada de comodín para las direcciones URL sencillas</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Sin entrada</p></td>
<td><div>

> [!IMPORTANT]  
> Tenga en cuenta que la longitud de clave mínima es de 1.024, pero puede recibir una advertencia que la longitud de clave mínima recomendada es de 2.048 bits.


</div>
<p>El certificado OAuthTokenIssuer es un certificado de propósito único para la autenticación de servidores en un entorno de gran escala y puede solicitarse desde una CA interna o desde una CA pública. El certificado es obligatorio.</p>
<p></p></td>
</tr>
</tbody>
</table>

