---
title: 'Lync Server 2013: Configuración de la negociación para socios federados XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 995ee34d0a2dcf28ca6aa4f8158d0e08d1533191
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a>Configuración de la negociación para socios federados XMPP en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-21_

La configuración de los tipos de negociación en la configuración de un socio XMPP tiene una amplia variedad de combinaciones posibles. No todas estas combinaciones son válidas. La tabla que se describe en este tema definirá la configuración válida y no válida. Las configuraciones comunes se presentan en la primera tabla, en la segunda tabla, en la que se detallan todas las combinaciones posibles. Tenga en cuenta que no puede tener *nivel de autenticación y seguridad simple* (SASL) **a menos que** la seguridad de la *capa de transporte* (TLS) también esté disponible. SASL se envía en un formato no cifrado (legible) y nunca debe transmitirse a menos que esté protegido por otro medio, como TLS.

### <a name="common-xmpp-federation-negotiation-methods"></a>Métodos comunes de negociación de Federación de XMPP

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Seguridad de la capa de transporte (TLS)</th>
<th>Capa de seguridad y autenticación simple (SASL)</th>
<th>Autenticación Dialback</th>
<th>Métodos de autenticación esperados</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Requerido </p></td>
<td><p>Obligatorio</p></td>
<td><p>Falso</p></td>
<td><p>SASL sobre TLS</p></td>
<td><p>TLS y SASL requeridos ayudan a garantizar que la secuencia de mensajes SASL sea segura. Dialback no está disponible y no se puede usar para un método de reserva si el socio de XMPP federado no ha establecido TLS en requerido u opcional.</p></td>
</tr>
<tr class="even">
<td><p>Obligatorio</p></td>
<td><p>Opcional</p></td>
<td><p>Verdadero</p></td>
<td><p>SASL sobre TLS, TLS Dialback, TCP Dialback</p></td>
<td><p>Al requerir TLS, si el socio XMPP federado ha establecido SASL a la opción SASL opcional o requerida. Si SASL no está disponible, se usará Dialback a través de TLS.</p></td>
</tr>
<tr class="odd">
<td><p>Opcional </p></td>
<td><p>Opcional</p></td>
<td><p>Verdadero</p></td>
<td><p>SASL sobre TLS, TLS Dialback, TCP Dialback</p></td>
<td><p>Aunque es muy flexible en los métodos de negociación ofrecidos, esta configuración depende de la configuración del socio de Federación de XMPP. Si el socio tiene TLS opcional o obligatorio, pero no se admite SASL, la Dialback de TLS estará disponible. Si el asociado tiene TLS y SASL establecido en opcional o en obligatorio, se usa la selección óptima de TLS por SASL.</p></td>
</tr>
<tr class="even">
<td><p>No compatible</p></td>
<td><p>No compatible</p></td>
<td><p>Verdadero</p></td>
<td><p>Dialback TCP</p></td>
<td><p>En muchos casos, TCP Dialback es la única solución posible. Menos conveniente que otras opciones, proporciona un cierto nivel de confianza.</p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a>Matriz de métodos de negociación de Federación XMPP-completada

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Seguridad de la capa de transporte (TLS)</th>
<th>Capa de seguridad y autenticación simple (SASL)</th>
<th>Autenticación Dialback</th>
<th>Método de autenticación esperado</th>
<th>Notas, ADVERTENCIA o error para una configuración no válida</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Requerido </p></td>
<td><p>Obligatorio</p></td>
<td><p>Verdadero</p></td>
<td><p>SASL sobre TLS</p></td>
<td><div>

> [!WARNING]  
> Dialback no funcionará si se necesitan SASL y TLS.


</div></td>
</tr>
<tr class="even">
<td><p>Requerido </p></td>
<td><p>Obligatorio</p></td>
<td><p>Falso</p></td>
<td><p>SASL sobre TLS</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Opcional</p></td>
<td><p>Obligatorio</p></td>
<td><p>Verdadero</p></td>
<td><p>SASL sobre TLS, TLS Dialback, TCP Dialback</p></td>
<td><div>

> [!WARNING]  
> SASL requiere TLS. Permitir que TLS sea opcional puede provocar errores en las negociaciones de la sesión.


</div></td>
</tr>
<tr class="even">
<td><p>Opcional</p></td>
<td><p>Obligatorio</p></td>
<td><p>Falso</p></td>
<td><p>SASL sobre TLS</p></td>
<td><div>

> [!WARNING]  
> SASL requiere TLS. Permitir que TLS sea opcional puede provocar errores en las negociaciones de la sesión.


</div></td>
</tr>
<tr class="odd">
<td><p>No compatible</p></td>
<td><p>Obligatorio</p></td>
<td><p>Verdadero</p></td>
<td><p>Dialback TCP</p></td>
<td><div>

> [!WARNING]  
> SASL requiere TLS. Permitir que TLS sea opcional puede provocar errores en las negociaciones de la sesión.


</div></td>
</tr>
<tr class="even">
<td><p>No compatible</p></td>
<td><p>Obligatorio</p></td>
<td><p>Falso</p></td>
<td><div>

> [!WARNING]  
> Configuración no válida


</div></td>
<td><div>

> [!WARNING]  
> Como SASL requiere TLS, y TLS no está disponible, SASL/TLS no se pueden realizar correctamente. TCP Dialback se establece en false y no se puede usar.


</div></td>
</tr>
<tr class="odd">
<td><p>Obligatorio</p></td>
<td><p>Opcional</p></td>
<td><p>Verdadero</p></td>
<td><p>SASL sobre TLS, TLS Dialback</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Obligatorio</p></td>
<td><p>Opcional</p></td>
<td><p>Falso</p></td>
<td><p>SASL sobre TLS</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Opcional </p></td>
<td><p>Opcional</p></td>
<td><p>Verdadero</p></td>
<td><p>SASL sobre TLS, TLS Dialback, TCP Dialback</p></td>
<td><div>

> [!WARNING]  
> SASL requiere TLS. Permitir que TLS sea opcional puede provocar errores en las negociaciones de la sesión.


</div></td>
</tr>
<tr class="even">
<td><p>Opcional </p></td>
<td><p>Opcional</p></td>
<td><p>Falso</p></td>
<td><p>SASL sobre TLS</p></td>
<td><div>

> [!WARNING]  
> SASL requiere TLS. Permitir que TLS sea opcional puede provocar errores en las negociaciones de la sesión.


</div></td>
</tr>
<tr class="odd">
<td><p>No compatible</p></td>
<td><p>Opcional</p></td>
<td><p>Verdadero</p></td>
<td><p>Dialback TCP</p></td>
<td><div>

> [!WARNING]  
> SASL requiere TLS. Permitir que TLS sea opcional puede provocar errores en las negociaciones de la sesión.


</div></td>
</tr>
<tr class="even">
<td><p>No compatible</p></td>
<td><p>Opcional</p></td>
<td><p>Falso</p></td>
<td><div>

> [!WARNING]  
> Configuración no válida


</div></td>
<td><div>

> [!WARNING]  
> SASL requiere TLS. Permitir que TLS sea opcional puede provocar errores en las negociaciones de la sesión.


</div></td>
</tr>
<tr class="odd">
<td><p>Obligatorio</p></td>
<td><p>No compatible</p></td>
<td><p>Verdadero</p></td>
<td><p>TLS Dialback</p></td>
<td><p>La configuración permite Dialback TLS.</p></td>
</tr>
<tr class="even">
<td><p>Obligatorio</p></td>
<td><p>No compatible</p></td>
<td><p>Falso</p></td>
<td><p>Configuración no válida</p></td>
<td><div>

> [!WARNING]  
> SASL o Dialback deben estar habilitados.


</div></td>
</tr>
<tr class="odd">
<td><p>Opcional</p></td>
<td><p>No compatible</p></td>
<td><p>Verdadero</p></td>
<td><p>TLS Dialback, TCP Dialback</p></td>
<td><p>Según las opciones de negociación del otro punto final, se aceptarán TCP o TLS Dialback.</p></td>
</tr>
<tr class="even">
<td><p>Opcional</p></td>
<td><p>No compatible</p></td>
<td><p>Falso</p></td>
<td><p>Configuración no válida</p></td>
<td><div>

> [!WARNING]  
> SASL o Dialback deben estar habilitados.


</div></td>
</tr>
<tr class="odd">
<td><p>No compatible</p></td>
<td><p>No compatible</p></td>
<td><p>Verdadero</p></td>
<td><p>Dialback TCP</p></td>
<td><p>TCP Dialback es el único método de negociación disponible</p></td>
</tr>
<tr class="even">
<td><p>No compatible</p></td>
<td><p>No compatible</p></td>
<td><p>Falso</p></td>
<td><p>Configuración no válida</p></td>
<td><div>

> [!WARNING]  
> SASL o Dialback deben estar habilitados.


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

