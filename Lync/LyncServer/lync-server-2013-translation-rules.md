---
title: 'Lync Server 2013: Reglas de traducción'
TOCTitle: Reglas de traducción
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48275632
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Reglas de traducción en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Lync Server 2013Telefonía IP empresarial requiere que todas las cadenas de marcado se normalicen al formato E.164 para realizar búsquedas inversas de números (RNL). En Microsoft Lync Server 2010, las reglas de conversión solo se admiten para los números marcados. Como novedad en Microsoft Lync Server 2013, las reglas de conversión también se admiten para los números que llaman. La *entidad del mismo nivel que el tronco* (esto es, la puerta de enlace asociada, la central de comunicación (PBX) o el tronco SIP) puede requerir que los números estén en un formato de marcado local. Para convertir números del formato E.164 a un formato de marcado local, puede definir una o más reglas de conversión para manipular el URI de solicitud antes de enrutarlo a la entidad del mismo nivel que el tronco. Por ejemplo, puede escribir una regla de conversión para quitar +44 del inicio de la cadena de marcado y sustituirlo por 0144.

Mediante la conversión de la ruta saliente del servidor, se pueden reducir los requisitos de configuración de cada entidad del mismo nivel que el tronco individual para convertir los números de teléfono en un formato de marcado local. Cuando se planea cuántas puertas de enlace y cuáles de ellas se asociarán a un clúster del Servidor de mediación específico, puede resultar de utilidad agrupar entidades del mismo nivel que el tronco con requisitos de marcado local similares. De este modo, se puede reducir el número de reglas de conversión requeridas y el tiempo necesario para escribirlas.

> [!IMPORTANT]  
> La asociación de una o más reglas de conversión a una configuración del tronco de Telefonía IP empresarial debería usarse como alternativa a la configuración de reglas de conversión en el tronco. No asocie reglas de conversión a una configuración del tronco de Telefonía IP empresarial si ha configurado reglas de conversión en el tronco, ya que ambas reglas podrían entrar en conflicto.



## Reglas de conversión de ejemplo

Los siguientes ejemplos de reglas de conversión muestran cómo se pueden desarrollar reglas en el servidor para convertir números del formato E.164 a un formato local para la entidad del mismo nivel que el tronco.

Para obtener más información acerca de cómo implementar reglas de conversión, consulte [Definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación referente a la implementación.


<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th>Descripción</th>
<th>Dígitos iniciales</th>
<th>Longitud</th>
<th>Dígitos que se van a quitar</th>
<th>Dígitos que se van a agregar</th>
<th>Patrón de comparación</th>
<th>Traducción</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Marcado convencional de larga distancia en EE.UU.</p>
<p>(quite el &quot;+&quot;)</p></td>
<td><p>+1</p></td>
<td><p>Exactamente 12</p></td>
<td><p>1</p></td>
<td><p>0</p></td>
<td><p>^\+(1\d{10})$</p></td>
<td><p>$1</p></td>
<td><p>+14255551010 se convierte en 14255551010</p></td>
</tr>
<tr class="even">
<td><p>Marcado internacional de larga distancia de EE.UU.</p>
<p>(quite el &quot;+&quot; y agregue 011)</p></td>
<td><p>+</p></td>
<td><p>11 como mínimo</p></td>
<td><p>1</p></td>
<td><p>011</p></td>
<td><p>^\+(\d{9}\d+)$</p></td>
<td><p>011$1</p></td>
<td><p>+441235551010 se convierte en 011441235551010</p></td>
</tr>
</tbody>
</table>

