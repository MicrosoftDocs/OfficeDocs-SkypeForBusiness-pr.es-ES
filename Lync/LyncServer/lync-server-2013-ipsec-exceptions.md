﻿---
title: Excepciones de IPsec en Lync Server 2013
TOCTitle: Excepciones de IPsec en Lync Server 2013
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48274693
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Excepciones de IPsec en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

En aquellas redes empresariales donde el protocolo de seguridad de Internet o IPsec (consulte IETF RFC 4301-4309) está implementado, IPsec se debe deshabilitar en el intervalo de puertos usado para la entrega de audio, vídeo y vídeo panorámico. Esta recomendación se fundamenta en la necesidad de evitar retrasos en la asignación de los puertos de medios debido a la negociación de IPsec.

En la siguiente tabla se detalla la configuración de las excepciones de IPsec recomendadas.

### Excepciones de IPsec recomendadas

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre de regla</th>
<th>IP de origen</th>
<th>IP de destino</th>
<th>Protocolo</th>
<th>Puerto de origen</th>
<th>Puerto de destino</th>
<th>Requisito de autenticación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidor perimetral A/V interno entrante</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servidor perimetral A/V interno</p></td>
<td><p>UDP y TCP</p></td>
<td><p>Cualquiera</p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="even">
<td><p>Servidor perimetral A/V externo entrante</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servidor perimetral A/V externo</p></td>
<td><p>UDP y TCP</p></td>
<td><p>Cualquiera</p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Servidor perimetral A/V interno saliente</p></td>
<td><p>Servidor perimetral A/V interno</p></td>
<td><p>Cualquiera</p></td>
<td><p>TCP y UDP</p></td>
<td><p>Cualquiera</p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="even">
<td><p>Servidor perimetral A/V externo saliente</p></td>
<td><p>Servidor perimetral A/V externo</p></td>
<td><p>Cualquiera</p></td>
<td><p>UDP y TCP</p></td>
<td><p>Cualquiera</p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Servidor de mediación entrante</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servidores</p>
<p>de mediación</p></td>
<td><p>UDP y TCP</p></td>
<td><p>Cualquiera</p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="even">
<td><p>Servidor de mediación saliente</p></td>
<td><p>Servidores</p>
<p>de mediación</p></td>
<td><p>Cualquiera</p></td>
<td><p>UDP y TCP</p></td>
<td><p>Cualquiera</p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Operador de conferencia entrante</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servidor front-end que ejecuta operador de conferencia</p></td>
<td><p>UDP y TCP</p></td>
<td><p>Cualquiera</p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="even">
<td><p>Operador de conferencia saliente</p></td>
<td><p>Servidor front-end que ejecuta operador de conferencia</p></td>
<td><p>Cualquiera</p></td>
<td><p>UDP y TCP</p></td>
<td><p>Cualquiera</p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Servidor de conferencia A/V entrante</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servidores front-end</p></td>
<td><p>UDP y TCP</p></td>
<td><p>Cualquiera</p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="even">
<td><p>Salida de conferencia A/V</p></td>
<td><p>Servidores front-end</p></td>
<td><p>Cualquiera</p></td>
<td><p>UDP y TCP</p></td>
<td><p>Cualquiera</p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Exchange entrante</p></td>
<td><p>Cualquiera</p></td>
<td><p>Mensajería unificada de Exchange</p></td>
<td><p>UDP y TCP</p></td>
<td><p>Cualquiera</p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="even">
<td><p>Servidores de aplicaciones compartidas entrantes</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servidores de aplicaciones compartidas</p></td>
<td><p>TCP</p></td>
<td><p>Cualquiera</p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Servidor de aplicaciones compartidas saliente</p></td>
<td><p>Servidores de aplicaciones compartidas</p></td>
<td><p>Cualquiera</p></td>
<td><p>TCP</p></td>
<td><p>Cualquiera</p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="even">
<td><p>Exchange saliente</p></td>
<td><p>Mensajería unificada de Exchange</p></td>
<td><p>Cualquiera</p></td>
<td><p>UDP y TCP</p></td>
<td><p>Cualquiera</p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Clientes</p></td>
<td><p>Cualquiera</p></td>
<td><p>Cualquiera</p></td>
<td><p>UDP</p></td>
<td><p>Intervalo de puertos de medios especificado</p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
</tbody>
</table>

