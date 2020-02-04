---
title: 'Lync Server 2013: probar las conferencias de audio de terceros'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a90aab3b0aec4fce46b311baccd0f28f2e7101b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745450"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a>Prueba de conferencias de audio de terceros en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-11-01_


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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsAudioConferencingProvider. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

Estos proveedores son organizaciones de terceros que suministran servicios de audioconferencia a organizaciones. Entre otras cosas, los proveedores de audioconferencia permiten a los usuarios que no se encuentran en la oficina, y que no están conectados a la red corporativa o Internet, participar en la parte de audio de una conferencia o una reunión. Los proveedores de servicios de audioconferencia suelen ofrecer servicios de alta calidad, como la traducción en vivo, la transcripción y la asistencia del operador Live por Conferencia.

El cmdlet **Test-CsAudioConferencingProvider** se usa para comprobar que un usuario puede establecer una conexión con su proveedor de servicios de audioconferencia. Tenga en cuenta que este cmdlet puede ejecutarse de una de dos maneras. Muchos administradores usarán los cmdlets de CsHealthMonitoringConfiguration para configurar los usuarios de prueba para cada uno de sus grupos de registradores. Estos usuarios de prueba representan un par de cuentas de usuario preconfiguradas para su uso con transacciones sintéticas. (Normalmente, son cuentas de prueba y no cuentas que pertenecen a usuarios reales). Si los usuarios de prueba están configurados para un grupo, los administradores pueden ejecutar el cmdlet **Test-CsAudioConferencingProvider** en ese grupo sin tener que especificar la identidad de (y proporcionar las credenciales para) la cuenta de usuario implicada en la prueba.

Como alternativa, los administradores pueden ejecutar el cmdlet **Test-CsAudioConferencingProvider** con una cuenta de usuario real. Si decide realizar la prueba usando una cuenta de usuario real, tendrá que proporcionar el nombre de inicio de sesión y la contraseña de la cuenta.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El ejemplo 1 comprueba si un usuario de prueba definido para el grupo atl-cs-001.litwareinc.com puede conectarse a su proveedor de servicios de audioconferencia. Este comando requiere que se defina al menos un usuario de prueba para el grupo. Si no se han definido usuarios de prueba para atl-cs-001.litwareinc.com, el comando fallará; Esto se debe a que el cmdlet **Test-CsAudioConferencingProvider** no sabrá qué usuario debe emplear en la prueba. Si no ha definido usuarios de prueba para un grupo, debe incluir el parámetro UserSipAddress y las credenciales de la cuenta de usuario que debe usar el comando al comprobar la conexión con un proveedor de servicios de audioconferencia.

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

Los comandos que se muestran en el ejemplo 2 prueban la capacidad de un\\usuario específico (litwareinc kenmyer) para conectarse a su proveedor de servicios de audioconferencia. Para ello, el primer comando del ejemplo usa el cmdlet Get-Credential para crear un objeto de credenciales de la interfaz de línea de comandos de Windows PowerShell que contiene el nombre y la contraseña del usuario Ken Myer. (Dado que el nombre de\\inicio de sesión litwareinc kenmyer se ha incluido como parámetro, el cuadro de diálogo solicitud de credenciales de Windows PowerShell solo requiere que el administrador escriba la contraseña de la cuenta de Ken Myer). El objeto de credenciales resultante se almacena en una variable denominada $credential.

El segundo comando comprueba entonces si este usuario puede conectarse a su proveedor de servicios de audioconferencia. Para llevar a cabo esta tarea, se llama al cmdlet test-CsAudioConferencingProvider, junto con tres parámetros: TargetFqdn (el FQDN del grupo de servidores de registrar); UserCredential (el objeto de Windows PowerShell que contiene las credenciales de usuario de Ken Myer); y UserSipAddress (la dirección SIP correspondiente a las credenciales de usuario suministradas).

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si el proveedor de servicios de audioconferencia está configurado correctamente, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta:**

FQDN de destino: atl-sql-001.litwareinc.com

Resultado: éxito

Latencia: 00:00:00

Mensaje de error:

Diagnóstico

Si el usuario especificado no puede iniciar sesión o cerrar sesión, el resultado se mostrará como un **error**y se registrará información adicional en las propiedades de diagnóstico y errores:

FQDN de destino: atl-sql-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

Mensaje de error: 10060, error al intentar la conexión porque la persona conectada

no respondió correctamente después de un período de tiempo, o

error en la conexión establecida porque el host conectado tiene

Error al responder \[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944\]: 5061

Excepción interna: error en el intento de conexión porque el

la parte conectada no respondió correctamente después de un período de

hora o error de conexión establecida porque el host conectado

Error al responder

\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944\]: 5061

Diagnóstico

Por ejemplo, la salida anterior incluye la nota "la persona conectada no respondió correctamente" que normalmente indica que hay un problema con el servidor perimetral.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que **Test-CsAudioConferencingProvider** podría fallar:

  - Se proporcionó un valor de parámetro incorrecto. Tal y como se muestra en el ejemplo anterior, los parámetros opcionales deben estar configurados correctamente o no se puede realizar la prueba. Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.

  - Observe que la prueba se producirá un error si el usuario empleado por el cmdlet **Test-CsAudioConferencingProvider** no ha sido asignado a un proveedor de servicios de audioconferencia.

  - Este comando fallará si el servidor perimetral está mal configurado o aún no se ha implementado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

