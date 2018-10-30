﻿---
title: 'Lync Server 2013: Lista de comprobaciones para la implementación de E9-1-1'
TOCTitle: Lista de comprobaciones para la implementación de E9-1-1
ms:assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398864(v=OCS.15)
ms:contentKeyID: 48276682
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lista de comprobaciones para la implementación de E9-1-1 en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Para planificar eficazmente 9-1-1 mejorado (E9-1-1), no olvide incluir los siguientes requisitos en la implementación:

  - Requisitos previos para implementar E9-1-1

  - Pasos necesarios para implementar E9-1-1

## Requisitos previos para implementar E9-1-1

Antes de implementar E9-1-1, debe haber implementado los servidores internos de Lync Server, como Almacén de administración central, Grupo de servidores front-end, un servidor Standard Edition, uno o varios Servidores de mediación o Grupos de servidores de mediación y clientes Lync Server. Además, una implementación de E9-1-1 requiere un tronco SIP con un proveedor de servicios de E9-1-1 certificado una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) para la Red telefónica conmutada (RTC). Lync Server solo admite el uso de proveedores de servicios de E9-1-1 ubicados en los Estados Unidos.

## Proceso de implementación

En la tabla siguiente se proporciona información general del proceso de implementación de E9-1-1. Para obtener información detallada sobre los pasos de la implementación, vea [Configurar 9-1-1 mejorado en Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) en la documentación de implementación.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Pasos</th>
<th>Roles</th>
<th>Documentación de implementación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Realizar configuraciones de tronco, rutas y usos de voz</p></td>
<td><ol>
<li><p>Cree un registro de uso de RTC. Se trata del mismo nombre que se ha usado para el parámetro <strong>Uso de RTC</strong> en la directiva de ubicación.</p></li>
<li><p>Cree o asigne una ruta de voz con el registro de uso de RTC creado en el paso anterior y apunte el atributo de puerta de enlace al tronco SIP E9-1-1 o la puerta de enlace ELIN.</p></li>
<li><p>Para un proveedor de servicios E9-1-1 de tronco SIP, defina el tronco que va a gestionar las llamadas E9-1-1 sobre el SIP para transferir datos PIDF-LO con el cmdlet <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong>.</p></li>
<li><p>Opcionalmente, para un proveedor de servicios E9-1-1 de tronco SIP, cree o asigne una ruta RTC local para llamadas no gestionadas por el tronco SIP del proveedor de servicios E9-1-1. Esta ruta se usará si la conexión al proveedor de servicios E9-1-1 no está disponible. Si lo admite el proveedor de servicios E9-1-1, asigne una regla de configuración de tronco a la puerta de enlace que convierte la cadena de marcado 911 en el número de llamada directa a la extensión (DID) del Centro de respuesta a llamadas de emergencia nacional y/o regional.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Configurar una ruta de voz de E9-1-1 en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Crear directivas de ubicación y asignarlas a usuarios y subredes</p></td>
<td><ol>
<li><p>Revise la directiva de ubicación global.</p></li>
<li><p>Cree una directiva de ubicación con un ámbito en el nivel de usuario o si la organización tiene más de un sitio con diferentes usos de emergencia, cree una directiva de ubicación con un ámbito de nivel de red.</p></li>
<li><p>Asigne la directiva de ubicación a sitios de red.</p></li>
<li><p>Agregue las subredes apropiadas al sitio de red.</p></li>
<li><p>Asigne la directiva de ubicación a directivas de usuario (opcional).</p></li>
</ol>
<p></p></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin (excepto para crear directivas de ubicación)</p></td>
<td><p><a href="lync-server-2013-create-location-policies.md">Crear directivas de ubicación en Lync Server 2013</a></p>
<p><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Agregar una directiva de ubicación a un sitio de red en Lync Server 2013</a></p>
<p><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Asociar subredes a sitios de red para E9-1-1 en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurar la base de datos de ubicaciones</p></td>
<td><ol>
<li><p>Rellene la base de datos con asignaciones de elementos de red a ubicaciones.</p></li>
<li><p>Para las puertas de enlace ELIN, agregue los ELIN a la columna &lt;NombreEmpresa&gt;.</p></li>
<li><p>Configure la conexión con el proveedor de servicios de E9-1-1 para validar las direcciones.</p></li>
<li><p>Valide las direcciones con el proveedor de servicios E9-1-1.</p></li>
<li><p>Publique la base de datos actualizada.</p></li>
<li><p>Para las puertas de enlace ELIN, cargue los ELIN en la base de datos de identificación automática de ubicaciones (ALI) del proveedor de RTC.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin</p></td>
<td><p><a href="lync-server-2013-configure-the-location-database.md">Configurar la base de datos de ubicaciones en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurar características avanzadas (opcional)</p></td>
<td><ol>
<li><p>Configure la dirección URL de la aplicación SNMP.</p></li>
<li><p>Configure la dirección URL para la ubicación de Servicio de información de ubicaciones secundario.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-snmp-application.md">Configuración de una aplicación SNMP en Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Configurar un servicio de información de ubicación secundario en Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>

