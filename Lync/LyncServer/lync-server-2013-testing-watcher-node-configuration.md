---
title: 'Lync Server 2013: probar la configuración de nodo de monitor'
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
ms.openlocfilehash: a8d0fe8500bd676ef1a9a33c9197dfeac7783c10
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a>Probar la configuración de nodo de monitor en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsWatcherNodeConfiguration</strong> . Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

Si usa Microsoft System Center Operations Manager para supervisar Lync Server 2013, tiene la opción de configurar "nodos de monitor": equipos que ejecutan transacciones sintéticas de forma periódica y automática para comprobar que Lync Server funciona como esperaba. Los nodos de monitor se asignan a grupos y se administran mediante los cmdlets **CsWatcherNodeConfiguration** . Tenga en cuenta que no necesita instalar los nodos de monitor si está utilizando el System Center Operations Manager. Todavía puede supervisar el sistema sin usar nodos de monitor. La única diferencia es que las transacciones sintéticas que desee ejecutar deben invocarse manualmente en lugar de invocarse de forma automática por parte de Operations Manager.

El cmdlet **Test-CsWatcherNodeConfiguration** permite comprobar que un nodo de monitor se configuró correctamente y que se asigna a un grupo de servidores de Lync Server 2013 válido. Tenga en cuenta que el cmdlet **Test-CsWatcherNodeConfiguration** debe ejecutarse en el nodo de monitor en sí. El cmdlet no se puede ejecutar en equipos remotos.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El siguiente comando comprueba las opciones de configuración de cada nodo de monitor que se usa en la organización.

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

El siguiente resultado de ejemplo correcto muestra un sistema con cuatro servidores perimetrales.

Validación del grupo de destino atl-cs-001.litwareinc.com en la topología.

Correcto: el grupo de servidores de destino atl-cs-001.litwareinc.com existe en la topología.

Correcto: el grupo de servidores de destino atl-cs-001.litwareinc.com tiene instalado el rol de registrador.

Correcto: la versión del grupo de servidores de destino atl-cs-001.litwareinc.com es compatible.

Correcto: el número de puerto para 5061 grupo de servidores de destino atl-cs-001.litwareinc.com es correcto.

Comprobando si faltan grupos en la configuración de nodo de monitor iniciada. Si se detecta algún error, se imprimirá.

Se ha completado la comprobación de los grupos que faltan en la configuración de nodo de monitor.

Se ha iniciado la comprobación de claves del registro para el nodo de monitor creado por la instalación del nodo de monitor. Si se detecta algún error, se imprimirá.

Comprobando las claves del registro de nodo de monitor creadas por la instalación del nodo de monitor ha finalizado. El tipo de autenticación detectado es Negotiate.

La existencia del SIP de la credencial del usuario de prueba se validó correctamente: user1@ atl-cs-001.litwareinc.com en el almacén de administración de credenciales.

La existencia del SIP de la credencial del usuario de prueba se validó correctamente: user2@ atl-cs-001.litwareinc.com en el almacén de administración de credenciales.

Comprobando si faltan grupos en la configuración de nodo de monitor iniciada. Si se detecta algún error, se imprimirá.

ADVERTENCIA: el grupo de atl-cs-001.litwareinc.com tiene registrador

rol instalado, pero no hay ningún usuario de prueba configurado para él.

Se ha completado la comprobación de los grupos que faltan en la configuración de nodo de monitor.

Comprobando las claves del registro de nodo de monitor creadas por la instalación del nodo de monitor es

inicia. Si se detecta algún error, se imprimirá.

Test-CsWatcherNodeConfiguration: no se encuentra la clave del registro de mantenimiento en

Software\\de\\comunicaciones en tiempo real de Microsoft. Asegúrese de que el nodo de monitor. msi es

instalado correctamente.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que **Test-CsWatcherNodeConfiguration** podría fallar:

  - El nodo de monitor no está instalado correctamente.

  - No hay usuarios de prueba configurados.

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

