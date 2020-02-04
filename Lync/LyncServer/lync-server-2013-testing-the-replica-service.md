---
title: 'Lync Server 2013: probar el servicio de réplicas'
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
ms.openlocfilehash: c955da727a4213098a5b6af4f6fbb348bb60dd21
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsReplica</strong> . Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet **Test-CsReplica** verifica que el servicio de réplica de Lync Server 2013 se esté ejecutando en el equipo local. El cmdlet **Test-CsReplica** realiza estas tareas como:

  - comprobar el estado del agente de replicación y los servicios de agente de registro centralizados

  - comprobando que los puertos necesarios se abrieron en el Firewall de Windows

  - asegurándose de que existen los grupos de seguridad de Active Directory y de equipo local necesarios.

Ten en cuenta que este cmdlet debe ejecutarse de forma local. Es decir, debe ejecutarse en el mismo equipo en el que se ejecuta el servicio de réplicas. No hay opciones para ejecutar el cmdlet **Test-CsReplica** en un servidor remoto.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El comando que se muestra en el ejemplo 1 prueba el servicio de réplica de 2013 de Lync Server en el equipo local. En este ejemplo, el parámetro verbose se usa para garantizar que se muestra en pantalla la información sobre la prueba, incluido el error eventual o el éxito de la prueba y la ubicación del informe generado por la prueba.

    Test-CsReplica -Verbose

El ejemplo 2 es una variación del comando que se muestra en el ejemplo 1. En este caso, el parámetro de informe se incluye para especificar una ruta de acceso y un nombre de carpeta para el informe generado por la prueba. Si no especifica una ruta de acceso al informe, se le proporcionará un nombre generado automáticamente de la siguiente manera:

C:\\administrador\\de usuarios.\\litwareinc\\AppData\\local\\temporal\\1 prueba-CS-réplica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e. html

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Inserte el cuerpo de la sección aquí.

VERBOse: crear un nuevo archivo de registro "\\C\\:\\usuarios\\prueba\\AppData\\prueba de tiempo local-CsReplica-3cb066b3-dd23-411A-8932-99f01c0f940c. xml".

VERBOse: crear un nuevo archivo de registro "\\C\\:\\usuarios\\prueba\\AppData\\prueba de tiempo local-CsReplica-3cb066b3-dd23-411A-8932-99f01c0f940c. xml".

VERBOse: el procesamiento de "prueba-CsReplica" se completó correctamente.

VERBOse puede encontrar los resultados detallados en "C\\:\\usuarios\\prueba\\AppData\\prueba\\local temporal-CsReplica-3cb066b3-dd23-411A-8932-99f01c0f940c. xml".

VERBOse: crear un nuevo archivo de registro

"C:\\usuarios\\prueba\\AppData\\local\\temporal\\2\\prueba-CsReplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083. xml ".

VERBOse: crear un nuevo archivo de registro

"C:\\usuarios\\prueba\\AppData\\local\\temporal\\2\\prueba-CsReplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083. html ".

ADVERTENCIA: error de test-CsReplica.

ADVERTENCIA: puede encontrar resultados detallados en

"C:\\usuarios\\prueba\\AppData\\local\\temporal\\2\\prueba-CsReplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083. html ".

Prueba-CsReplica: error al ejecutar el comando: el acceso al registro solicitado no es

tienen.

En la línea: 1 carácter: 1

\+Prueba-CsReplica-verbose

\+ ~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo: InvalidOperation: (:) \[Prueba-CsReplica\], seguridad

Excepción

\+FullyQualifiedErrorId: ProcessingFailed, Microsoft. RTC. Management. deploy

asignaciones. TestReplicaCmdlet

Prueba de PS\\C\\: usuarios\>

PS C:\\usuarios\\probando\> prueba-CsUcwaConference-TargetFqdn "LyncTest. SelfHost. Corp. M

icrosoft.com "

ADVERTENCIA: no se pudo leer el número de puerto del registrador para el nombre completo

nombre de dominio (FQDN). Usando el número de puerto predeterminado del registrador. Excepción

System. InvalidOperationException: no se encontró ningún clúster coincidente en la topología.

en

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Prueba-CsUcwaConference: no hay ningún usuario de prueba asignado para

\[LyncTest.SelfHost.Corp.Microsoft.com\]. Comprobar la configuración del usuario de prueba.

En la línea: 1 carácter: 1

\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo: ResourceUnavailable: (:) \[Prueba-CsUcwaConference\]

, InvalidOperationException

\+FullyQualifiedErrorId: NotFoundTestUsers, Microsoft. RTC. Management. sintetizador

eticTransactions.TestUcwaConferenceCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que **Test-CsReplica** podría fallar:

  - Es posible que haya un problema mayor con el agente de replicación y los servicios de agente de registro centralizados

  - Es posible que los puertos necesarios no estén abiertos en el Firewall de Windows

  - Es posible que los grupos de seguridad de Active Directory y equipos locales necesarios no existan

</div>

</div>

<span> </span>

</div>

</div>

</div>

