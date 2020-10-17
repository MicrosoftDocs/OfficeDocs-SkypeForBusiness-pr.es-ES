---
title: 'Lync Server 2013: probar la audioconferencia de terceros'
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
ms.openlocfilehash: 51f728bfb5617185bdd9a1ef3b5f21b3e12ca61f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503937"
---
# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a>Prueba de conferencias de audio de terceros en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsAudioConferencingProvider. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

Un proveedor de audioconferencia es una compañía de terceros que proporciona servicios de conferencia a las organizaciones. Entre otras cosas, los proveedores de servicios de audioconferencia permiten que los usuarios puedan participar en la parte de audio de una conferencia o reunión sin estar en la oficina y sin estar conectados a la red corporativa ni a Internet. Los proveedores de servicios de audioconferencia suelen proporcionar servicios de gama alta, como traducción en directo, transcripción y servicio de operador por conferencia en directo.

El cmdlet **Test-CsAudioConferencingProvider** se usa para comprobar que un usuario puede establecer una conexión con su proveedor de servicios de audioconferencia. Tenga en cuenta que puede ejecutar este cmdlet de dos maneras distintas. Muchos administradores usarán los cmdlets CsHealthMonitoringConfiguration para configurar usuarios de prueba para cada grupo de registradores. Los usuarios de prueba representan un par de cuentas de usuario que se han preconfigurado para su uso con las transacciones sintéticas. (Normalmente, son cuentas de prueba y no cuentas que pertenecen a usuarios reales). Si los usuarios de prueba están configurados para un grupo de servidores, los administradores pueden ejecutar el cmdlet **Test-CsAudioConferencingProvider** con ese grupo sin tener que especificar la identidad (y proporcionar las credenciales para) la cuenta de usuario que participa en la prueba.

Como alternativa, los administradores pueden ejecutar el cmdlet **Test-CsAudioConferencingProvider** con una cuenta de usuario real. Para llevar a cabo la prueba con una cuenta de usuario real, deberá especificar los nombres de usuario y las contraseñas de cada usuario.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

En el ejemplo 1, se comprueba si un usuario de prueba definido para el grupo atl-cs-001.litwareinc.com puede conectar con el proveedor de servicios de audioconferencia. Este comando necesita que se defina al menos un usuario de prueba para el grupo. Si no se ha definido ningún usuario de prueba para atl-cs-001.litwareinc.com, se producirá un error en el comando; Esto se debe a que el cmdlet **Test-CsAudioConferencingProvider** no sabrá qué usuario debe emplear en la prueba. Si no definió ningún usuario de prueba para el grupo, incluya el parámetro UserSipAddress y las credenciales de la cuenta de usuario que deberá utilizar el comando para comprobar la conexión con el proveedor de servicios de audioconferencia.

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

Los comandos que se muestran en el ejemplo 2 prueban la capacidad de un usuario específico (litwareinc \\ kenmyer) para conectarse a su proveedor de servicios de audioconferencia. Para ello, el primer comando del ejemplo usa el cmdlet Get-Credential para crear un objeto de credenciales de interfaz de línea de comandos de Windows PowerShell que contiene el nombre y la contraseña del usuario Ken Myer. (Dado que el nombre de inicio de sesión litwareinc \\ kenmyer se incluyó como un parámetro, el cuadro de diálogo solicitud de credenciales de Windows PowerShell solo requiere que el administrador escriba la contraseña de la cuenta de Ken Myer). El objeto Credentials resultante se almacena en una variable denominada $credential.

Luego, el segundo comando comprueba si este usuario puede conectar con el proveedor de servicios de audioconferencia. Para llevar a cabo esta tarea, se llama al cmdlet Test-CsAudioConferencingProvider, junto con tres parámetros: TargetFqdn (el FQDN del grupo de registrador); UserCredential (el objeto de Windows PowerShell que contiene las credenciales de usuario de Ken Myer); y UserSipAddress (la dirección SIP correspondiente a las credenciales de usuario suministradas).

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si el proveedor de servicios de audioconferencia está configurado correctamente, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta:**

FQDN de destino: atl-sql-001.litwareinc.com

Resultado: correcto

Latencia: 00:00:00

Mensaje de error:

Diagnóstico

Si el usuario especificado no puede iniciar o cerrar sesión, el resultado se mostrará como un **error**y se registrará información adicional en las propiedades error y diagnóstico:

FQDN de destino: atl-sql-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

Mensaje de error: 10060, se ha producido un error en el intento de conexión porque la entidad conectada

no respondió correctamente después de un período de tiempo o

error en la conexión establecida porque el host conectado tiene

no se pudo responder \[ 2001:4898: E8: f39e: 5c9a: ad83:81b3:9944 \] : 5061

Excepción interna: error en el intento de conexión porque el

la parte conectada no respondió correctamente después de un período de

tiempo o error de conexión establecida debido a que el host conectado

no respondió

\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944 \] : 5061

Diagnóstico

Por ejemplo, la salida anterior incluye la nota "la persona conectada no respondió correctamente" que normalmente indica un problema con el servidor perimetral.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que **Test-CsAudioConferencingProvider** podría fallar:

  - Se ha suministrado un valor de parámetro incorrecto. Como se muestra en el ejemplo anterior, los parámetros opcionales deben configurarse correctamente o se producirá un error en la prueba. Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.

  - Tenga en cuenta que se producirá un error en la prueba si no se ha asignado un proveedor de servicios de audioconferencia al usuario empleado por el cmdlet **Test-CsAudioConferencingProvider** .

  - Este comando producirá un error si el servidor perimetral está mal configurado o no se ha implementado todavía.

</div>

</div>

<span> </span>

</div>

</div>

</div>

