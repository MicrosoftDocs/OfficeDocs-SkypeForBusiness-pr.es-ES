---
title: Configurar clientes para la migración
TOCTitle: Configurar clientes para la migración
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49889377
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar clientes para la migración

 

_**Última modificación del tema:** 2016-12-08_

En este tema se enumeran los pasos de implementación de cliente recomendados que se deben seguir antes de migrar a Lync Server 2013. Estos cambios de configuración se deben realizar en Office Communications Server 2007 R2. Es muy importante que estos pasos se lleven a cabo antes de la migración. Para obtener información detallada, consulte [Planeación de clientes y dispositivos en Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).

## Para configurar clientes antes de la migración

1.  Implemente las actualizaciones (revisiones) de servidor, cliente y dispositivo más recientes para Office Communications Server 2007 R2:
    
      - [Aplicar actualizaciones de Office Communications Server 2007 R2](apply-office-communications-server-2007-r2-updates.md)
    
      - [Descripción de la actualización acumulativa para Communicator 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [Obtener actualizaciones de software para dispositivos](http://go.microsoft.com/fwlink/?linkid=335809)

2.  En Office Communications Server 2007 R2, use el filtrado de versión de cliente para que solo puedan iniciar sesión los clientes de Office Communications Server 2007 R2 que tengan instaladas las actualizaciones más recientes.

3.  En Office Communications Server 2007 R2, use el filtrado de versión de cliente para impedir que los clientes de Lync Server 2013 inicien sesión. Siga los pasos que se describen en **Configuración del filtrado de versión de cliente** en [http://go.microsoft.com/fwlink/?linkid=202488\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=202488%26clcid=0xc0a) para agregar los filtros de versión que figuran en la siguiente tabla. Asigne la acción **Bloquear** en cada filtro de versión.
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Cliente</th>
    <th>Encabezado de agente de usuario</th>
    <th>Versión</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Lync 2013</p></td>
    <td><p>OC</p></td>
    <td><p>15.*.*.*</p></td>
    </tr>
    <tr class="even">
    <td><p>Lync Web App</p></td>
    <td><p>CWA</p></td>
    <td><p>5.*.*.*</p></td>
    </tr>
    <tr class="odd">
    <td><p>Lync Phone Edition</p></td>
    <td><p>OCPhone</p></td>
    <td><p>4.*.*.*</p></td>
    </tr>
    </tbody>
    </table>

