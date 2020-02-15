---
title: 'Lync Server 2013: prueba del servicio de réplicas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the replica service
ms:assetid: 4ff2cc91-0036-4c5a-9792-7bf43d8ce18d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727303(v=OCS.15)
ms:contentKeyID: 63969600
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ad585ab12d874b7689aab6442ac913a06c8792f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-replica-service-in-lync-server-2013"></a>Probar el servicio de réplicas en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsReplica</strong> . Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet **Test-CsReplica** comprueba que el servicio de réplica de 2013 de Lync Server se está ejecutando en el equipo local. El cmdlet **Test-CsReplica** realiza tareas como las siguientes:

  - comprobación del estado del agente de replicador y los servicios de agente de registro centralizados

  - comprobar que los puertos necesarios se abrieron en el Firewall de Windows

  - asegurándose de que existen los grupos de seguridad de Active Directory y de equipo local necesarios.

Tenga en cuenta que este cmdlet debe ejecutarse de forma local. Es decir, debe ejecutarse en el mismo equipo en el que se ejecuta el servicio de réplicas. No hay opciones para ejecutar el cmdlet **Test-CsReplica** en un servidor remoto.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El comando que se muestra en el ejemplo 1 prueba el servicio de réplica de Lync Server 2013 en el equipo local. En este ejemplo, se usa el parámetro verbose para garantizar que la información sobre la prueba, incluido el error eventual o el éxito de la prueba, y la ubicación del informe generado por la prueba, se muestra en la pantalla.

    Test-CsReplica -Verbose

El ejemplo 2 es una variación del comando que se muestra en el ejemplo 1. En este caso, el parámetro Report se incluye para especificar una ruta de acceso de carpeta y un nombre para el informe generado por la prueba. Si no se especifica ninguna ruta de acceso para el informe, se le asignará un nombre generado automáticamente similar al siguiente:

C:\\administrador\\de usuarios.\\litwareinc\\AppData\\local\\Temp\\1 test-CS-Replication-3db40ee0-4b5d-4f58-8d3d-b1e61253129e. html

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Inserte el cuerpo de la sección aquí.

VERBOse: creación de un nuevo archivo de registro\\"\\C\\:\\users Testing AppData local\\Temp\\test-CsReplica-3cb066b3-dd23-411A-8932-99f01c0f940c. xml".

VERBOse: creación de un nuevo archivo de registro\\"\\C\\:\\users Testing AppData local\\Temp\\test-CsReplica-3cb066b3-dd23-411A-8932-99f01c0f940c. xml".

VERBOse: el procesamiento de "test-CsReplica" se ha completado correctamente.

VERBOse: los resultados detallados se pueden encontrar en\\"\\C\\:\\users Testing AppData local\\Temp\\test-CsReplica-3cb066b3-dd23-411A-8932-99f01c0f940c. xml".

VERBOse: creación de un nuevo archivo de registro

"C:\\usuarios\\probando\\AppData\\local\\Temp\\2\\test-CsReplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083. xml ".

VERBOse: creación de un nuevo archivo de registro

"C:\\usuarios\\probando\\AppData\\local\\Temp\\2\\test-CsReplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083. html ".

ADVERTENCIA: error de test-CsReplica.

ADVERTENCIA: los resultados detallados se pueden encontrar en

"C:\\usuarios\\probando\\AppData\\local\\Temp\\2\\test-CsReplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083. html ".

Test-CsReplica: error en la ejecución del comando: el acceso al registro solicitado no es

permiso.

En la línea: 1 carácter: 1

\+Test-CsReplica-verbose

\+ ~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo: InvalidOperation: (:) \[Test-CsReplica\], seguridad

Excepción

\+FullyQualifiedErrorId: ProcessingFailed, Microsoft. RTC. Management. deploy

Comentario. TestReplicaCmdlet

PS C:\\usuarios\\probar\>

PS C:\\\\users\> Testing test-CsUcwaConference-TargetFqdn "LyncTest. SelfHost. Corp. M

icrosoft.com "

ADVERTENCIA: no se pudo leer el número de puerto del registrador para el certificado completo

nombre de dominio (FQDN). Se usará el número de puerto del registrador predeterminado. Excepción

System. InvalidOperationException: no se encontró ningún clúster que coincida en la topología.

Veamos

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Test-CsUcwaConference: no hay ningún usuario de prueba asignado para

\[LyncTest.SelfHost.Corp.Microsoft.com\]. Compruebe la configuración del usuario de prueba.

En la línea: 1 carácter: 1

\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo: ResourceUnavailable: (:) \[Test-CsUcwaConference\]

, InvalidOperationException

\+FullyQualifiedErrorId: NotFoundTestUsers, Microsoft. RTC. Management. sintetizador

eticTransactions.TestUcwaConferenceCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que **Test-CsReplica** podría fallar:

  - Es posible que haya un problema mayor con los servicios agente de duplicación y agente de registro centralizado

  - Es posible que los puertos necesarios no estén abiertos en el Firewall de Windows

  - Es posible que no existan los grupos de seguridad de Active Directory y del equipo local necesarios

</div>

</div>

<span> </span>

</div>

</div>

</div>

