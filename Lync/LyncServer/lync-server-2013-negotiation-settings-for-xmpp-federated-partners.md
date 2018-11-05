---
title: 'Lync Server 2013: Configuración de la negociación para socios federados XMPP'
TOCTitle: Configuración de la negociación para socios federados XMPP
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ552456(v=OCS.15)
ms:contentKeyID: 49129323
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de la negociación para socios federados XMPP en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Las opciones de configuración de los tipos de negociación en la configuración de un socio XMPP se pueden combinar de una infinidad de formas. Aunque no todas las combinaciones son válidas. En la tabla incluida en este tema se define cuáles son válidas y cuáles no. En la primera tabla se presentan las configuraciones comunes y en la segunda, todas las combinaciones posibles. Observe que no se puede tener la *Capa de autenticación y seguridad simple* (SASL) **a menos que también esté disponible la***Seguridad de capa de transporte* (TLS). La SASL se envía en formato no cifrado (legible) y no debe enviarse a menos que se proteja por otro medio, como puede ser TLS.

### Métodos de negociación de federación de XMPP

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
<th>Seguridad de capa de transporte (TLS)</th>
<th>Capa de autenticación y seguridad simple (SASL)</th>
<th>Autenticación por devolución de llamada</th>
<th>Método(s) de autenticación esperado(s)</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Obligatorio</p></td>
<td><p>Obligatorio</p></td>
<td><p>Falso</p></td>
<td><p>SASL por TLS</p></td>
<td><p>Se requiere el uso de TLS y SASL para garantizar que la transmisión de mensajes SASL es segura. La devolución de llamadas no se encuentra disponible y no se puede utilizar como método de conmutación por recuperación si el socio federado de XMPP no ha definido el uso de TLS como obligatorio u opcional.</p></td>
</tr>
<tr class="even">
<td><p>Obligatorio</p></td>
<td><p>Opcional</p></td>
<td><p>Verdadero</p></td>
<td><p>SASL por TLS, Devolución de llamada TLS, Devolución de llamada TCP</p></td>
<td><p>Al requerir el uso de TLS, si el socio federado de XMPP ha definido el uso de SASL como opcional u obligatorio, se utilizará. Si la SASL no se encuentra disponible, se utilizará la Devolución de llamada TLS.</p></td>
</tr>
<tr class="odd">
<td><p>Opcional</p></td>
<td><p>Opcional</p></td>
<td><p>Verdadero</p></td>
<td><p>SASL por TLS, Devolución de llamada TLS, Devolución de llamada TCP</p></td>
<td><p>A pesar de ser muy flexibles en cuanto a los métodos de negociación ofrecidos, estas opciones dependen de la configuración del socio de federación XMPP. Si el socio tiene el uso de TLS como opcional u obligatorio, pero no es compatible con la SASL, se tendrá disponible la Devolución de llamada TLS. Si el socio ha definido TLS y SASL como opcionales u obligatorio, se usará la opción óptima, es decir, TLS por SASL.</p></td>
</tr>
<tr class="even">
<td><p>No se admite</p></td>
<td><p>No se admite</p></td>
<td><p>Verdadero</p></td>
<td><p>Devolución de llamada TCP</p></td>
<td><p>En muchos casos, la Devolución de llamada TCP es la única solución posible. Aunque es menos recomendable que otras opciones, ofrece cierto nivel de confianza.</p></td>
</tr>
</tbody>
</table>


### Matriz de métodos de negociación de federación XMPP completa

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
<th>Seguridad de capa de transporte (TLS)</th>
<th>Capa de autenticación y seguridad simple (SASL)</th>
<th>Autenticación por devolución de llamada</th>
<th>Método de autenticación esperado</th>
<th>Notas, advertencias o errores en caso de configuraciones no válidas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Obligatorio</p></td>
<td><p>Obligatorio</p></td>
<td><p>Verdadero</p></td>
<td><p>SASL por TLS</p></td>
<td><div>

> [!WARNING]  
> La devolución de llamada no funcionará si SASL y TLS son obligatorios.


</div></td>
</tr>
<tr class="even">
<td><p>Obligatorio</p></td>
<td><p>Obligatorio</p></td>
<td><p>Falso</p></td>
<td><p>SASL por TLS</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Opcional</p></td>
<td><p>Obligatorio</p></td>
<td><p>Verdadero</p></td>
<td><p>SASL por TLS, Devolución de llamada TLS, Devolución de llamada TCP</p></td>
<td><div>

> [!WARNING]  
> SASL requiere TLS. Si se permite que TLS sea opcional, las negociaciones de sesión pueden fracasar.


</div></td>
</tr>
<tr class="even">
<td><p>Opcional</p></td>
<td><p>Obligatorio</p></td>
<td><p>Falso</p></td>
<td><p>SASL por TLS</p></td>
<td><div>

> [!WARNING]  
> SASL requiere TLS. Si se permite que TLS sea opcional, las negociaciones de sesión pueden fracasar.


</div></td>
</tr>
<tr class="odd">
<td><p>No se admite</p></td>
<td><p>Obligatorio</p></td>
<td><p>Verdadero</p></td>
<td><p>Devolución de llamada TCP</p></td>
<td><div>

> [!WARNING]  
> SASL requiere TLS. Si se permite que TLS sea opcional, las negociaciones de sesión pueden fracasar.


</div></td>
</tr>
<tr class="even">
<td><p>No se admite</p></td>
<td><p>Obligatorio</p></td>
<td><p>Falso</p></td>
<td><div>

> [!WARNING]  
> La configuración no es válida


</div></td>
<td><div>

> [!WARNING]  
> Como SASL requiere TLS y TLS no está disponible, la combinación SASL/TLS no es viable. La Devolución de llamada TCP se ha definido en False y, por tanto, no se puede utilizar.


</div></td>
</tr>
<tr class="odd">
<td><p>Obligatorio</p></td>
<td><p>Opcional</p></td>
<td><p>Verdadero</p></td>
<td><p>SASL por TLS, Devolución de llamada TLS</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Obligatorio</p></td>
<td><p>Opcional</p></td>
<td><p>Falso</p></td>
<td><p>SASL por TLS</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Opcional</p></td>
<td><p>Opcional</p></td>
<td><p>Verdadero</p></td>
<td><p>SASL por TLS, Devolución de llamada TLS, Devolución de llamada TCP</p></td>
<td><div>

> [!WARNING]  
> SASL requiere TLS. Si se permite que TLS sea opcional, las negociaciones de sesión pueden fracasar.


</div></td>
</tr>
<tr class="even">
<td><p>Opcional</p></td>
<td><p>Opcional</p></td>
<td><p>Falso</p></td>
<td><p>SASL por TLS</p></td>
<td><div>

> [!WARNING]  
> SASL requiere TLS. Si se permite que TLS sea opcional, las negociaciones de sesión pueden fracasar.


</div></td>
</tr>
<tr class="odd">
<td><p>No se admite</p></td>
<td><p>Opcional</p></td>
<td><p>Verdadero</p></td>
<td><p>Devolución de llamada TCP</p></td>
<td><div>

> [!WARNING]  
> SASL requiere TLS. Si se permite que TLS sea opcional, las negociaciones de sesión pueden fracasar.


</div></td>
</tr>
<tr class="even">
<td><p>No se admite</p></td>
<td><p>Opcional</p></td>
<td><p>Falso</p></td>
<td><div>

> [!WARNING]  
> La configuración no es válida


</div></td>
<td><div>

> [!WARNING]  
> SASL requiere TLS. Si se permite que TLS sea opcional, las negociaciones de sesión pueden fracasar.


</div></td>
</tr>
<tr class="odd">
<td><p>Obligatorio</p></td>
<td><p>No se admite</p></td>
<td><p>Verdadero</p></td>
<td><p>Devolución de llamada TLS</p></td>
<td><p>La configuración permite la Devolución de llamada TLS.</p></td>
</tr>
<tr class="even">
<td><p>Obligatorio</p></td>
<td><p>No se admite</p></td>
<td><p>Falso</p></td>
<td><p>La configuración no es válida</p></td>
<td><div>

> [!WARNING]  
> Es necesario activar SASL o la devolución de llamada.


</div></td>
</tr>
<tr class="odd">
<td><p>Opcional</p></td>
<td><p>No se admite</p></td>
<td><p>Verdadero</p></td>
<td><p>Devolución de llamada TLS, Devolución de llamada TCP</p></td>
<td><p>La Devolución de llamada TCP o TLS se aceptarán o no en función de las opciones de negociación del otro extremo.</p></td>
</tr>
<tr class="even">
<td><p>Opcional</p></td>
<td><p>No se admite</p></td>
<td><p>Falso</p></td>
<td><p>La configuración no es válida</p></td>
<td><div>

> [!WARNING]  
> Es necesario activar SASL o la devolución de llamada.


</div></td>
</tr>
<tr class="odd">
<td><p>No se admite</p></td>
<td><p>No se admite</p></td>
<td><p>Verdadero</p></td>
<td><p>Devolución de llamada TCP</p></td>
<td><p>La Devolución de llamada TCP es el único método de negociación disponible</p></td>
</tr>
<tr class="even">
<td><p>No se admite</p></td>
<td><p>No se admite</p></td>
<td><p>Falso</p></td>
<td><p>La configuración no es válida</p></td>
<td><div>

> [!WARNING]  
> Es necesario activar SASL o la devolución de llamada.


</div></td>
</tr>
</tbody>
</table>

