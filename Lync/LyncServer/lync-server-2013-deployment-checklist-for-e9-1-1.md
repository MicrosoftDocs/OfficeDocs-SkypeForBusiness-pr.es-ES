---
title: 'Lync Server 2013: lista de comprobación de implementación para E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for E9-1-1
ms:assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398864(v=OCS.15)
ms:contentKeyID: 48185655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9a48ba3d999e55106298d7419e4590147e1e9e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835512"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a>Lista de comprobación de implementación para E9-1-1 en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

Para planificar de forma eficaz una 9-1-1 mejorada (E9-1-1), asegúrese de incluir los siguientes requisitos de implementación:

  - Requisitos previos para implementar E9-1-1.

  - Pasos necesarios para implementar el E9-1-1.

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a>Requisitos previos para implementar E9-1-1

Antes de implementar E9-1-1, ya debe haber implementado los servidores internos de Lync Server, incluido un almacén de administración central, un grupo front-end o un servidor Standard Edition, uno o varios servidores de mediación o grupos de servidores de mediación y clientes de Lync Server. Además, una implementación de E9-1-1 requiere un tronco SIP con un proveedor de servicios E9-1-1 certificado o una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) a la red telefónica conmutada (RTC). Lync Server admite el uso de proveedores de servicios de E9-1-1 únicamente en los Estados Unidos.

</div>

<div>

## <a name="deployment-process"></a>Proceso de implementación

En la tabla siguiente se proporciona información general del proceso de implementación de E9-1-1. Para obtener más información sobre los pasos de implementación, vea [configurar 9-1-1 mejorado en Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) en la documentación de implementación.


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
<li><p>Cree un registro de uso de RTC. Se trata del mismo nombre que se ha usado para el parámetro <strong>Uso de RTC</strong> en la directiva de ubicación.</p></li>
<li><p>Cree o asigne una ruta de voz con el registro de uso de RTC creado en el paso anterior y apunte el atributo de puerta de enlace al tronco SIP E9-1-1 o la puerta de enlace ELIN. </p></li>
<li><p>Para un proveedor de servicios E9-1-1 de tronco SIP, defina el tronco que va a gestionar las llamadas E9-1-1 sobre el SIP para transferir datos PIDF-LO con el cmdlet <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong>.</p></li>
<li><p>Opcionalmente, para un proveedor de servicios E9-1-1 de tronco SIP, cree o asigne una ruta RTC local para llamadas no gestionadas por el tronco SIP del proveedor de servicios E9-1-1. Esta ruta se usará si la conexión al proveedor de servicios E9-1-1 no está disponible. Si lo admite el proveedor de servicios E9-1-1, asigne una regla de configuración de tronco a la puerta de enlace que convierte la cadena de marcado 911 en el número de llamada directa a la extensión (DID) del Centro de respuesta a llamadas de emergencia nacional y/o regional.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Configurar una ruta de voz E9-1-1 en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Crear directivas de ubicación y asignarlas a usuarios y subredes</p></td>
<td><ol>
<li><p>Revise la directiva de ubicación global.</p></li>
<li><p>Cree una directiva de ubicación con un ámbito en el nivel de usuario o, si la organización tiene más de un sitio con diferentes usos de emergencia, cree una directiva de ubicación con un ámbito de nivel de red.</p></li>
<li><p>Asigne la directiva de ubicación a sitios de red.</p></li>
<li><p>Agregue las subredes apropiadas al sitio de red.</p></li>
<li><p>Asigne la directiva de ubicación a directivas de usuario (opcional).</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin (excepto para crear directivas de ubicación)</p></td>
<td><p><a href="lync-server-2013-create-location-policies.md">Crear directivas de ubicación en Lync Server 2013</a></p>
<p><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Agregar una directiva de ubicación a un sitio de red en Lync Server 2013</a></p>
<p><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Asociar subredes con sitios de red para E9-1-1 en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurar la base de datos de ubicaciones</p></td>
<td><ol>
<li><p>Rellene la base de datos con asignaciones de elementos de red a ubicaciones.</p></li>
<li><p>Para las puertas de enlace ELIN, agregue la ELINs &lt;a&gt; la columna NombreCompañía.</p></li>
<li><p>Configure la conexión con el proveedor de servicios de E9-1-1 para validar las direcciones.</p></li>
<li><p>Valide las direcciones con el proveedor de servicios E9-1-1.</p></li>
<li><p>Publique la base de datos actualizada.</p></li>
<li><p>Para las puertas de enlace ELIN, cargue los ELIN en la base de datos de identificación automática de ubicaciones (ALI) del proveedor de RTC.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin</p></td>
<td><p><a href="lync-server-2013-configure-the-location-database.md">Configure the location database in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurar características avanzadas (opcional)</p></td>
<td><ol>
<li><p>Configure la dirección URL de la aplicación SNMP.</p></li>
<li><p>Configure la dirección URL para la ubicación del servicio de información de ubicación secundaria.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-snmp-application.md">Configurar una aplicación SNMP en Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Configurar un servicio de información de ubicación secundaria en Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

