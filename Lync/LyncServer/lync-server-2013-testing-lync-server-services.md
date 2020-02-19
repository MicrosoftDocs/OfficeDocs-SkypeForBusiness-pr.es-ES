---
title: 'Lync Server 2013: comprobación de los servicios de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 609275678edcadda11c0210c22efab1acececd43
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-lync-server-services-in-lync-server-2013"></a>Probar los servicios de Lync Server en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Programación de comprobación</p></td>
<td><p>Diario</p></td>
</tr>
<tr class="even">
<td><p>Herramienta de prueba</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permisos necesarios</p></td>
<td><p>Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</p>
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsComputer. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

Test-CsComputer comprueba el estado de todos los servicios de Lync Server 2013 que se ejecutan en el equipo local. (Test-CsComputer solo se puede ejecutar de forma local, no se puede ejecutar desde una instancia remota de Windows PowerShell). El cmdlet también comprueba si los puertos de Firewall adecuados están abiertos en el equipo y determina si los grupos de Active Directory que se crearon al instalar Lync Server 2013 se agregaron a los grupos locales correspondientes. Por ejemplo, test-CsComputer comprobará que el grupo de Active Directory RTCUniversalUserAdmins se agregó al grupo administradores.

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet test-CsComputer solo se puede ejecutar en el equipo local, pero no puede llamar a test-CsComputer desde una instancia remota de Windows PowerShell. De forma predeterminada, test-CsComputer muestra muy poco resultados en pantalla, en lugar de que la información devuelta por el cmdlet se escriba en un archivo HTML. Por ello, se recomienda incluir el parámetro verbose y el parámetro Report en cualquier momento que se ejecute test-CsComputer. El parámetro verbose proporcionará un resultado ligeramente más detallado en pantalla mientras se ejecuta el cmdlet. El parámetro Report permite especificar una ruta de acceso de archivo y un nombre de archivo para el archivo HTML generado por test-CsComputer. Si no incluye el parámetro de informe, el archivo HTML se guardará automáticamente en la carpeta de usuarios y se le asignará un nombre similar al siguiente: ce84964a-c4da-4622-Ad34-c54ff3ed361f. html.

El siguiente comando de ejemplo ejecuta test-CsComputer y guarda el resultado en un archivo denominado C:\\logs\\ComputerTest. html:

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Debido al número de comprobaciones de comprobación que realiza, test-CsComputer no informa de una simple **sí, la prueba se ha realizado correctamente** o **no se ha producido un error en la prueba**. En su lugar, tiene que ver el archivo HTML generado con Internet Explorer para determinar si cada prueba se ha realizado correctamente o no.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que test-CsComputer podría fallar:

  - Es posible que el equipo de prueba no esté habilitado para su uso con Lync Server. Esto puede ocurrir si los servicios o los roles de servidor de Lync Server en el equipo han cambiado y no se ejecutó el cmdlet enable-CsComputer. Para solucionar este problema, ejecute el siguiente comando:
    
        Enable-CsComputer

  - Es posible que la replicación no esté actualizada en el equipo de prueba. Puede comprobar el estado de replicación actual de un equipo mediante la ejecución del cmdlet Get-CsManagementStoreReplicationStatus:
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    Si el estado de replicación no está actualizado, puede forzar la replicación manualmente mediante un comando similar al siguiente:
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - Es posible que la topología tenga que estar habilitada. Si cambia la topología de Lync Server (cambios que pueden afectar al equipo local), debe habilitar la nueva topología. Puede habilitar la topología en cualquier momento si ejecuta este comando:
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

