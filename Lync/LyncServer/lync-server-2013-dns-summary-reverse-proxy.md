---
title: 'Lync Server 2013: Resumen DNS - Proxy inverso'
TOCTitle: Resumen DNS - Proxy inverso
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48274829
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen DNS - Proxy inverso en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Puede configurar dos adaptadores de red en el proxy inverso de la siguiente forma:

## Requisitos del adaptador de red con proxy inverso

  - Ejemplo de **adaptador de red 1 (Interfaz interna)**
    
    Interfaz interna con 172.25.33.40 asignada.
    
    No se ha definido ninguna puerta de enlace predeterminada.
    
    Asegúrese de que existe una ruta desde la red que contiene la interfaz interna del proxy inverso hasta todas las redes que contienen servidores de Grupo de servidores front-end de Lync Server (por ejemplo, de 172.25.33.0 a 192.168.10.0).

  - Ejemplo de **adaptador de red 2 (Interfaz externa)**
    
    Se asigna un mínimo de una dirección IP pública a este adaptador de red.
    
    Se ha definido la puerta de enlace para señalar al enrutador o al firewall integrado de su perímetro exterior. (10.45.16.1 en los ejemplos del escenario)

### Registros DNS requeridos para proxy inverso

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ubicación/TIPO/Puerto</th>
<th>FQDN</th>
<th>Dirección IP</th>
<th>Asigna/comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/A externo</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>Escucha asignada para los recursos publicados externamente</p></td>
<td><p>Servicios web externos desde la implementación interna. Se pueden definir y crear registros adicionales para todos los grupos de servidores y servidores únicos para cualquier dominio de SIP que use este proxy inverso y tenga definidos servicios web externos.</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externo</p></td>
<td><p>webdirext.contoso.com</p></td>
<td><p>Escucha asignada para los recursos publicados externamente</p></td>
<td><p>Servicios web externos para los grupos de servidores Directores o Director de su implementación. Puede definir tantos Directores como Directores diferentes haya, de los cuales pueden estar asociados con otros dominios SIP.</p>
<div>

> [!IMPORTANT]  
> Definición de los registros DNS para y publicación del Directores no es una decisión del grupo de servidores front-end ni de Director. Debe definir y publicar los servicios web externos tanto de Director como de Grupo de servidores front-end si está usando Directores. Los tipos de tráfico específicos (para autenticación y otros usos) se enviarán primero a Director, si está definido así en la topología.


</div></td>
</tr>
<tr class="odd">
<td><p>DNS/A externo</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Escucha asignada para los recursos publicados externamente</p></td>
<td><p>Conferencias de acceso telefónico local publicadas externamente</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externo</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Escucha asignada para los recursos publicados externamente</p></td>
<td><p>Conferencias publicadas externamente</p></td>
</tr>
<tr class="odd">
<td><p>DNS/A externo</p></td>
<td><p>officewebapps01.contoso.com</p></td>
<td><p>Escucha asignada para Servidor Office Web Apps</p></td>
<td><p>Servidor Office Web Apps implementado internamente o en el perímetro y publicado para el acceso de clientes externos</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externo</p></td>
<td><p>lyncdiscover.contoso.com</p></td>
<td><p>Escucha asignada para los recursos publicados externamente</p></td>
<td><p>Registro de Lync Discover External para la autodetección publicada externamente. Incluye Mobility, Microsoft Lync Web App y una aplicación web de programación.</p></td>
</tr>
</tbody>
</table>

