---
title: 'Lync Server 2013: Resumen del certificado-Director único'
description: 'Lync Server 2013: Resumen del certificado-Director único.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Single Director
ms:assetid: 1b769a76-cbf3-46e9-a955-f6cde5faff93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204720(v=OCS.15)
ms:contentKeyID: 48183546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cf930a73d9989ec44f52f1d70ee9e0f900e4d6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572166"
---
# <a name="certificate-summary---single-director-in-lync-server-2013"></a>Resumen del certificado-Director único en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

Los requisitos de certificado para un solo Director constan de un certificado predeterminado que tiene un nombre de sujeto y nombres alternativos de sujeto para los servicios que el director puede recibir. Asimismo, existe un certificado OAuth Token para fines de autenticación de servidor a servidor.

### <a name="certificates-for-director"></a>Certificados para el director

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
<th>Nombre de sujeto (SN)</th>
<th>Nombres alternativos del sujeto (SAN)</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Predeterminado</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>dir01.contoso.net</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>lyncdiscoverinternal.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(Opcional) *.contoso.com</p></td>
<td><p>Los certificados de director se pueden solicitar desde una entidad de certificación (CA) administrada internamente o desde una CA pública.</p>
<p>El Director responde a las solicitudes del proxy inverso en el perímetro o desde el servidor perimetral. Los clientes internos no usarán el director.</p>
<p>O una entrada con comodín para las direcciones URL simples</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Sin entradas</p></td>
<td><div>

> [!IMPORTANT]  
> Tenga en cuenta que la longitud mínima de clave es 1024, pero puede recibir una advertencia de que la clave mínima recomendada es de 2048 bits.


</div>
<p>El certificado OAuthTokenIssuer es un certificado de un solo propósito para los fines de los servidores de autenticación en un entorno de gran escala, y pueden solicitarse a una CA interna o a una CA pública. Este certificado es obligatorio.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

