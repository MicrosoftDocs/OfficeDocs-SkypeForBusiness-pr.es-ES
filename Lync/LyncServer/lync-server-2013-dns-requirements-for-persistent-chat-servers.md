---
title: Requisitos DNS para servidores de chat persistentes
TOCTitle: Requisitos DNS para servidores de chat persistentes
ms:assetid: f7531374-d7ed-4b63-ae81-02294cb4496a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205391(v=OCS.15)
ms:contentKeyID: 48277198
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos DNS para servidores de chat persistentes

 

_**Última modificación del tema:** 2015-03-09_

En esta sección se describen los registros del sistema de nombres de dominio (DNS) necesarios para la implementación de Servidores de chat persistente.

## Registros DNS para servidores de chat persistente

En la siguiente tabla se especifican los requisitos de DNS para la implementación de Servidor de chat persistente.

### Requisitos de DNS para un servidor de chat persistente

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Escenario de implementación</th>
<th>Requisito de DNS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Un servidor de chat persistente</p></td>
<td><p>Un registro A interno que resuelve el nombre de dominio completo (FQDN) del servidor como su dirección IP.</p></td>
</tr>
<tr class="even">
<td><p>Grupo de servidores de chat persistente</p></td>
<td><p>Un registro A interno que resuelve el nombre de dominio completo (FQDN) de los servidores como su dirección IP.</p>
<p><strong>Ejemplo</strong></p>
<p>PersistentChatServer01.contoso.com     10.10.10.1</p>
<p>PersistentChatServer02.contoso.com     10.10.10.2</p>
<p>Un registro A interno que resuelve el nombre de dominio completo (FQDN) de los servidores como su dirección IP.</p>
<p><strong>Ejemplo</strong></p>
<p>PersistentChatPool.contoso.com    10.10.10.1</p>
<p>PersistentChatPool.contoso.com    10.10.10.2</p></td>
</tr>
</tbody>
</table>

