---
title: Requisitos de DNS para movilidad
TOCTitle: Requisitos de DNS para movilidad
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48276935
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos de DNS para movilidad

 

_**Última modificación del tema:** 2015-03-09_

Al implementar la característica de movilidad de Lync Server 2013, use las nuevas direcciones URL que están disponibles con el servicio Detección automática de Microsoft Lync Server 2013 o use las direcciones URL de servicios web existentes. Si usa las direcciones URL, los usuarios deben introducir manualmente las direcciones URL en la configuración del dispositivo móvil. Normalmente, esta opción se usa para solucionar problemas. Cuando use las nuevas direcciones URL, los clientes móviles pueden detectar automáticamente los recursos de Lync Server 2013. Cuando admita la detección automática, debe agregar los registros del sistema de nombres de dominio (DNS) nuevos. En esta sección se describen los registros DNS necesarios para la detección automática.

Para admitir la detección automática, cree los siguientes registros DNS para cada dominio SIP:

  - Un registro DNS interno para admitir usuarios móviles que se conectan desde la red de su organización

  - Un registro DNS externo, o público, para admitir usuarios móviles que se conectan desde Internet

La URL de detección automática interna no debería ser direccionable desde fuera de su red. La URL de detección automática externa no debería ser direccionable desde dentro de su red. Sin embargo, si no cumple este requisito para la URL externa, la funcionalidad del cliente móvil no debería verse afectada.

Los registros DNS pueden ser registros CNAME o registros A (host).

**Registro DNS interno**

Cree uno de los siguientes registros DNS internos:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de registro</th>
<th>Nombre de host o definición SRV</th>
<th>Se resuelve en</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscoverinternal.<em>&lt;dominiosip&gt;</em></p></td>
<td><p>Nombre de dominio completo (FQDN) de servicios web interno para su Grupo de directores, si dispone de uno, o para su Grupo de servidores front-end si no dispone de Director</p></td>
</tr>
<tr class="even">
<td><p>Un (host)</p></td>
<td><p>lyncdiscoverinternal.<em>&lt;dominiosip&gt;</em></p></td>
<td><p>Dirección IP de servicios web interna (dirección IP virtual (VIP) si usa un equilibrador de carga) para su Grupo de directores, si dispone de uno, o para su Grupo de servidores front-end si no dispone de Director</p></td>
</tr>
</tbody>
</table>


**Registros DNS externos**

Cree uno de los siguientes registros DNS externos:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de registro</th>
<th>Nombre de host</th>
<th>Se resuelve en</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover. <em>&lt;dominiosip&gt;</em></p></td>
<td><p>FQDN de servicios web externo para su Grupo de directores, si dispone de uno, o para su Grupo de servidores front-end si no dispone de Director</p></td>
</tr>
<tr class="even">
<td><p>Un (host)</p></td>
<td><p>lyncdiscover. <em>&lt;dominiosip&gt;</em></p></td>
<td><p>Dirección IP externa o pública (dirección VIP si usa un equilibrador de carga) del proxy inverso</p></td>
</tr>
<tr class="odd">
<td><p>SRV</p></td>
<td><p>_sipfederationtls._tcp. <em>&lt;dominiosip&gt;</em></p>
<p>Se resuelve en el registro host (A o AAAA) para el Servidor perimetral de acceso</p></td>
<td><p>Para admitir Servicios de notificaciones de inserción y Servicios de notificaciones de inserción de Apple, cree un registro SRV para cada dominio SIP que tenga clientes de Microsoft Lync Mobile.</p>
<div>

> [!IMPORTANT]  
> Este requisito se aplica solo a clientes de Microsoft Lync Mobile en Apple o en Microsoft basándose en dispositivos móviles. Los dispositivos Android y Nokia Symbian no usan notificaciones de inserción.


</div></td>
</tr>
</tbody>
</table>



> [!NOTE]
> El tráfico de lyncdiscover, también denominado Detección automática, circula a través del proxy inverso. El registro&nbsp;SRV apunta a un registro que se resuelve a través del Servidor perimetral de acceso.


