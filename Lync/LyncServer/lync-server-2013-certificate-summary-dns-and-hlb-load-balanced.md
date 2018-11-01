---
title: "Lync Server 2013 : Résumé des certificats - Équilibrage de ch. DNS et mat."
TOCTitle: Resumen de certificado - Carga equilibrada DNS y HLB
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205047(v=OCS.15)
ms:contentKeyID: 48275870
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen de certificado - Carga equilibrada DNS y HLB en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Los requisitos de certificados para un Director con equilibrio de carga DNS y un equilibrador de carga de hardware utilizará un certificado predeterminado con un nombre de sujeto y nombres alternativos de sujeto para los servicios que puede recibir el Director. Se solicita un certificado para cada Director del grupo de servidores. Es importante recordar que el equilibrador de carga de hardware está equilibrando la carga solamente del tráfico del proxy inverso. Además, existe un certificado del token OAuth para fines de autenticación de servidor a servidor que se instalan en cada servidor.

### Los certificados para Director

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
<td><p>dirpool01.contoso.net</p></td>
<td><p>dirpool01.contoso.net</p>
<p>dir01.contoso.net</p>
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
<p>El certificado OAuthTokenIssuer es un certificado de propósito único para la autenticación de servidores en un entorno de gran escala y puede solicitarse desde una CA interna o desde una CA pública. El certificado es obligatorio.</p></td>
</tr>
</tbody>
</table>

