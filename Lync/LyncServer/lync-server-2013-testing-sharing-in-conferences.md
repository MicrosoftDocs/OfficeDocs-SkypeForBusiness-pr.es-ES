---
title: 'Lync Server 2013: pruebas de uso compartido en conferencias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce4cd1a45d1eddf8875d85ff28886b0c04c29cfe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850327"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a>Pruebas de uso compartido en conferencias en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsDataConference</strong> . Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

En Lync Server 2013, una conferencia de datos es cualquier conferencia en la que se usen actividades de colaboración, como pizarras o anotaciones. El cmdlet **Test-CsDataConference** le permite comprobar que un par de usuarios pueden participar en una conferencia de datos.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El comando que se muestra en el ejemplo 1 comprueba que una conferencia de datos se puede llevar a cabo en el grupo atl-cs-001.litwareinc.com. Este comando supone que ha configurado un par de usuarios de prueba para el grupo especificado. Si no existen esos usuarios de prueba, el comando fallará.

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

Los comandos que se muestran en el ejemplo 2 prueban la capacidad de un par\\de usuarios (\\litwareinc Pilar y litwareinc kenmyer) para iniciar sesión en Lync Server 2013 y, a continuación, realizar una conferencia de datos. Para ello, el primer comando del ejemplo usa el cmdlet **Get-Credential** para crear un objeto de credencial de interfaz de línea de comandos de Windows PowerShell que contiene el nombre y la contraseña del usuario Pilar Ackerman. (Como el nombre de inicio de\\sesión, litwareinc pilar, se ha incluido como parámetro, el cuadro de diálogo solicitud de credenciales de Windows PowerShell solo requiere que el administrador escriba la contraseña de la cuenta de Pilar Ackerman). El objeto de credencial resultante se almacena en una variable llamada $cred 1. El segundo comando hace lo mismo, pero esta vez devuelve un objeto de credenciales para la cuenta Ken Myer.

Con los objetos de credenciales a mano, el tercer comando determina si estos dos usuarios pueden iniciar sesión en Lync Server 2013 y realizar una conferencia de datos. Para llevar a cabo esta tarea, se llama al cmdlet **Test-CsDataConference** , junto con los siguientes parámetros: TargetFqdn (el FQDN del grupo de servidores de registrar); SenderSipAddress (dirección SIP del primer usuario de prueba); SenderCredential (el objeto de Windows PowerShell que contiene las credenciales para este mismo usuario); ReceiverSipAddress (la dirección SIP del otro usuario de prueba); y ReceiverCredential (el objeto de Windows PowerShell que contiene las credenciales del otro usuario de prueba).

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si la Conferencia de datos se ha configurado correctamente, recibirá un resultado similar a este, con la propiedad result marcada como **correcta:**

FQDN de destino: atl-cs-001.litwareinc.com

Resultado: éxito

Latencia: 00:00:00

Mensaje de error:

Diagnóstico

Si los usuarios especificados no pueden usar el uso compartido de datos, el resultado se mostrará como **error**y la información adicional se registrará en las propiedades de diagnóstico y errores:

FQDN de destino: atl-cs-001.litwareinc.com

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

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que **Test-CsDataConference** podría fallar:

  - Se proporcionó un valor de parámetro incorrecto. Si se usa, los parámetros opcionales deben estar configurados correctamente o se producirá un error en la prueba. Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.

  - La posibilidad de llevar a cabo una conferencia de datos depende de la Directiva de conferencia que se haya asignado al usuario que organizó la Conferencia (en el caso del cmdlet **Test-CsDataConference** , que es el "remitente"). Si el organizador no puede incluir actividades de colaboración en su reunión (por ejemplo, si su Directiva de conferencia tiene la propiedad EnableDataCollaboration establecida en falso), el cmdlet **Test-CsDataConference** se producirá un error.

  - Este comando fallará si el servidor perimetral está mal configurado o aún no se ha implementado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

