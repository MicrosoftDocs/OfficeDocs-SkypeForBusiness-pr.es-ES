---
title: 'Lync Server 2013: Descripción de los requisitos de firewall para SQL Server'
TOCTitle: Descripción de los requisitos de firewall para SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48274850
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Descripción de los requisitos de firewall para SQL Server con Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Para una implementación de Standard Edition, se crean automáticamente excepciones de firewall durante la instalación de Lync Server 2013. Sin embargo, en implementaciones de Enterprise Edition, las excepciones de firewall se deben configurar manualmente en el servidor back-end de Microsoft SQL Server. El protocolo TCP/IP permite que un puerto determinado se use una vez para una dirección IP determinada. Esto significa que, para el servidor basado en SQL Server, puede asignar la instancia de base de datos predeterminada al puerto TCP 1433 predeterminado. Para las demás instancias deberá usar el Administrador de configuración de SQL Server para asignar puertos únicos y sin uso. En este tema se describen:

  - Requisitos de una excepción de firewall al usar la instancia predeterminada

  - Requisitos de una excepción de firewall para el servicio SQL Server Browser

  - Requisitos de puertos de escucha estáticos al usar instancias especificadas por el usuario

## Requisitos de una excepción de firewall al usar la instancia predeterminada

Si usa la instancia predeterminada de SQL Server para las bases de datos al implementar Lync Server 2013, se usan los siguientes requisitos de regla de firewall para asegurar la comunicación del grupo de servidores front-end con la instancia predeterminada de SQL Server.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocolo</th>
<th>Puerto</th>
<th>Dirección</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>1433</p></td>
<td><p>Entrante para SQL Server</p></td>
</tr>
</tbody>
</table>


## Requisitos de una excepción de firewall para el servicio SQL Server Browser

El servicio SQL Server Browser buscará las instancias de base de datos y comunicará al puerto que la instancia (especificada por el usuario o predeterminada) está configurada para su uso.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocolo</th>
<th>Puerto</th>
<th>Dirección</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UDP</p></td>
<td><p>1434</p></td>
<td><p>Entrante</p></td>
</tr>
</tbody>
</table>


## Requisitos de puertos de escucha estáticos al usar instancias especificadas por el usuario

Cuando se usan instancias especificadas por el usuario en la configuración de SQL Server para bases de datos que admitan Lync Server 2013, se configuran puertos estáticos mediante el Administrador de configuración de SQL Server. Una vez asignados los puertos estáticos a cada instancia especificada por el usuario, puede crear excepciones para cada puerto estático del firewall.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocolo</th>
<th>Puerto</th>
<th>Dirección</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>Definido estáticamente</p></td>
<td><p>Entrante</p></td>
</tr>
</tbody>
</table>


## SQL Server Documentation

La documentación de Microsoft SQL Server 2012 ofrece orientación detallada acerca de cómo configurar el acceso de firewall para bases de datos. Para obtener más información sobre Microsoft SQL Server 2012, vea “Configurar Firewall de Windows para permitir el acceso a SQL Server” en [http://go.microsoft.com/fwlink/?linkid=218031\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=218031%26clcid=0xc0a).

