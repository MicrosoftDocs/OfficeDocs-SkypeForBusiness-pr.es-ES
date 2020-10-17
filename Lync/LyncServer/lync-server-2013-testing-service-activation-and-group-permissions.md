---
title: 'Lync Server 2013: probar la activación del servicio y los permisos de grupo'
description: 'Lync Server 2013: probar la activación del servicio y los permisos de grupo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing service activation and group permissions
ms:assetid: 2c59e603-ba85-40ba-91a7-51c6fd39472e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743833(v=OCS.15)
ms:contentKeyID: 63969594
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 116cf939f3110616ce395eb14c7945890bdb89b7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556266"
---
# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a>Probar la activación del servicio y los permisos de grupo en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsTopology. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet Test-CsTopology permite comprobar que Lync Server 2013 funciona correctamente en un ámbito global. De forma predeterminada, el cmdlet comprueba toda la infraestructura de Lync Server, comprobando que los servicios necesarios se están ejecutando y que se han establecido los permisos adecuados para estos servicios y para los grupos de seguridad universal que se crean al instalar Lync Server.

Además de comprobar la validez de la instalación de Lync Server, Test-CsTopology también le permite comprobar la validez de un servicio específico. Por ejemplo, este comando comprueba el estado del servidor de conferencia A/V en el grupo atl-cs-001.litwareinc.com:

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

De forma predeterminada, Test-CsTopology muestra muy poco resultados en pantalla. En su lugar, la información devuelta por el cmdlet se escribe en un archivo HTML. El parámetro Report permite especificar una ruta de acceso de archivo y un nombre de archivo para el archivo HTML generado por test-CsTopology. Si no incluye el parámetro de informe, el archivo HTML se guardará automáticamente en la carpeta de usuarios y se le asignará un nombre similar al siguiente: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.

El siguiente comando de ejemplo ejecuta Test-CsTopology y guarda el resultado en un archivo denominado C: \\ Logs \\ComputerTest.html:

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

A diferencia de la mayoría de los cmdlets test, Test-CsTopology informa de que la operación se ha realizado correctamente o con errores. En parte, esto es debido a la gran cantidad de comprobaciones de comprobación que el cmdlet debe realizar cada vez que se ejecuta. En su lugar, los datos se guardan en un informe HTML que, a continuación, se puede ver con Internet Explorer.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que Test-CsTopology podría producir un error:

  - Es posible que la replicación no esté actualizada en el equipo de prueba. Puede comprobar el estado de replicación actual de un equipo ejecutando el cmdlet Get-CsManagementStoreReplicationStatus:
    
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

