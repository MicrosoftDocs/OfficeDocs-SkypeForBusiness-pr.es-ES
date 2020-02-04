---
title: 'Lync Server 2013: probar la configuración del nodo de monitor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing watcher node configuration
ms:assetid: f9ecd85c-0ae9-4906-b786-6b002b5a77c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn751537(v=OCS.15)
ms:contentKeyID: 63969667
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 920fc39d3800f83a2d40a613c391b2f0c93e4dac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a>Probar la configuración del nodo de monitor en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-11-03_


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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsWatcherNodeConfiguration</strong> . Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

Si usa Microsoft System Center Operations Manager para supervisar Lync Server 2013, tendrá la opción de configurar "nodos de monitor": equipos que ejecutan de forma periódica y automática transacciones sintéticas para comprobar que Lync Server funciona como esperado. Los nodos de monitor se asignan a grupos y se administran mediante los cmdlets de **CsWatcherNodeConfiguration** . Tenga en cuenta que no necesita instalar nodos de monitor si está usando System Center Operations Manager. Aún puede supervisar el sistema sin usar nodos de monitor. La única diferencia es que cualquier transacción sintética que desee ejecutar debe invocarse manualmente en lugar de invocarse de forma automática por parte de Operations Manager.

El cmdlet **Test-CsWatcherNodeConfiguration** le permite comprobar que un nodo de monitor se ha configurado correctamente y se asigna a un grupo de servidores de Lync Server 2013 válido. Tenga en cuenta que el cmdlet **Test-CsWatcherNodeConfiguration** debe ejecutarse en el nodo de monitor en sí. El cmdlet no se puede ejecutar en equipos remotos.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El siguiente comando comprueba la configuración de cada nodo de monitor que se usa en la organización.

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

La siguiente salida de ejemplo correcta muestra un sistema con cuatro servidores perimetrales.

Validando la atl-cs-001.litwareinc.com del grupo de destino en topología.

Correcto: la atl-cs-001.litwareinc.com del grupo de destino existe en la topología.

Correcto: el atl-cs-001.litwareinc.com del grupo de destino tiene el rol de registrador instalado.

Correcto: la versión del grupo de atl-cs-001.litwareinc.com es compatible.

Éxito: el número de puerto para la atl-cs-001.litwareinc.com del grupo de destino 5061 es correcto.

Se ha iniciado la búsqueda de grupos que faltan en la configuración del nodo de monitor. Si se detecta cualquier error, se imprimirá.

Se ha finalizado la búsqueda de grupos que faltan en la configuración del nodo de monitor.

Se ha iniciado la comprobación de las claves del registro del nodo de monitor creadas por la instalación del nodo de monitor. Si se detecta cualquier error, se imprimirá.

La comprobación de las claves del registro del nodo de monitor creadas por la instalación del nodo de monitor ha finalizado. El tipo de autenticación detectada es Negotiate.

La existencia del SIP de credenciales del usuario de prueba se validó correctamente: user1@ atl-cs-001.litwareinc.com en el almacén de administración de credenciales.

La existencia del SIP de credenciales del usuario de prueba se validó correctamente: user2@ atl-cs-001.litwareinc.com en el almacén de administración de credenciales.

Se ha iniciado la búsqueda de grupos que faltan en la configuración del nodo de monitor. Si se detecta cualquier error, se imprimirá.

ADVERTENCIA: el atl-cs-001.litwareinc.com de grupo tiene registrador

rol instalado, pero no hay ningún usuario de prueba configurado para él.

Se ha finalizado la búsqueda de grupos que faltan en la configuración del nodo de monitor.

La comprobación de las claves del registro del nodo de monitor creadas por la instalación del nodo de monitor es

Comience. Si se detecta cualquier error, se imprimirá.

Prueba-CsWatcherNodeConfiguration: no se puede encontrar la clave del registro de estado en

Software\\comunicaciones\\en tiempo real de Microsoft. Asegúrese de que el nodo Monitor. msi está

instalado correctamente.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que **Test-CsWatcherNodeConfiguration** podría fallar:

  - El nodo de monitor no está correctamente instalado.

  - No hay ningún usuario de prueba configurado.

</div>

<div>

## <a name="see-also"></a>Vea también


[Get-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[New-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[Remove-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[Set-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

