---
title: 'Lync Server 2013: comprobar los servicios de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b193473ad5941c647c572fae1b7cb5e7ece7f95d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

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
<td><p>Programación de verificación</p></td>
<td><p>Cada día</p></td>
</tr>
<tr class="even">
<td><p>Herramienta de prueba</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permisos necesarios</p></td>
<td><p>Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</p>
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsComputer. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

Prueba-CsComputer verifica el estado de todos los servicios de Lync Server 2013 que se están ejecutando en el equipo local. (Test-CsComputer solo se puede ejecutar de forma local, no se puede ejecutar desde una instancia remota de Windows PowerShell). El cmdlet también comprueba si los puertos de Firewall adecuados están abiertos en el equipo y determina si los grupos de Active Directory que se crearon cuando instaló Lync Server 2013 se agregaron a los grupos locales correspondientes. Por ejemplo, test-CsComputer comprobará que el grupo de Active Directory RTCUniversalUserAdmins se agregó al grupo de administradores.

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet test-CsComputer solo se puede ejecutar en el equipo local, pero no puede llamar a test-CsComputer desde una instancia remota de Windows PowerShell. De forma predeterminada, prueba-CsComputer muestra muy poco el resultado en pantalla, en su lugar la información devuelta por el cmdlet se escribe en un archivo HTML. Por eso, le recomendamos que incluya el parámetro verbose y el parámetro de informe en cualquier momento que ejecute test-CsComputer. El parámetro verbose proporcionará una salida ligeramente más detallada en pantalla mientras se ejecuta el cmdlet. El parámetro de informe le permite especificar una ruta de acceso y un nombre de archivo para el archivo HTML generado por test-CsComputer. Si no incluye el parámetro de informe, el archivo HTML se guardará automáticamente en la carpeta usuarios y recibirá un nombre similar a este: ce84964a-c4da-4622-Ad34-c54ff3ed361f. html.

El siguiente comando de ejemplo ejecuta test-CsComputer y guarda el resultado en un archivo denominado C:\\logs\\ComputerTest. html:

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Debido al número de comprobaciones de comprobación que realiza, test-CsComputer no devuelve un informe **sí, la prueba se realizó correctamente** o **no se produjo un error en la prueba**. En su lugar, tiene que ver el archivo HTML generado usando Internet Explorer para determinar el éxito o el fracaso de cada prueba.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que test-CsComputer podría fallar:

  - Es posible que el equipo de prueba no esté habilitado para su uso con Lync Server. Esto puede ocurrir si los roles de servidor o los servicios de Lync Server en el equipo han cambiado y no se ejecutó el cmdlet enable-CsComputer. Para resolver este problema, ejecute el siguiente comando:
    
        Enable-CsComputer

  - Es posible que la replicación no esté actualizada en el equipo de prueba. Para comprobar el estado de replicación actual de un equipo, ejecute el cmdlet Get-CsManagementStoreReplicationStatus:
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    Si el estado de replicación no está actualizado, puede forzar la replicación de forma manual con un comando similar a este:
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - Es posible que se deba habilitar la topología. Si cambia la topología de Lync Server (cambios que pueden afectar al equipo local), debe habilitar la nueva topología. Puede habilitar la topología en cualquier momento ejecutando este comando:
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

