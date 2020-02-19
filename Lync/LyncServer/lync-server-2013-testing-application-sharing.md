---
title: 'Lync Server 2013: prueba del uso compartido de aplicaciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing application sharing
ms:assetid: 8d21db9b-10d1-4b43-b057-0deb1df1c205
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727310(v=OCS.15)
ms:contentKeyID: 63969629
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb9f5771651f68d36666e039a9af71436ac3635b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-application-sharing-in-lync-server-2013"></a>Prueba del uso compartido de aplicaciones en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsASConference. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet **Test-CsASConference** comprueba que un par de usuarios de prueba puedan participar en una conferencia en línea que incluya el uso compartido de aplicaciones. Para ello, el cmdlet registra los dos usuarios con Lync Server 2013 y, a continuación, usa una de las cuentas de usuario para crear una nueva Conferencia que incluye el uso compartido de aplicaciones. Luego, el cmdlet comprueba que el segundo usuario puede unirse a esa llamada de conferencia.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El comando que se muestra en el ejemplo 1 comprueba que se puede llevar a cabo una conferencia de uso compartido de aplicaciones en el grupo atl-cs-001.litwareinc.com. Este comando asume que ha configurado un par de usuarios de prueba para el grupo especificado. Si los usuarios de prueba no existen, se producirá un error en el comando.

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

El ejemplo 2 comprueba la capacidad del servicio Join Launcher para participar en una conferencia de uso compartido de aplicaciones en el grupo atl-cs-001.litwareinc.com. Tenga en cuenta que este comando comprueba solo el servicio de sí mismo; no es necesario ningún dispositivo móvil para iniciar el comando.

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

Los comandos que se muestran en el ejemplo 2 prueban la capacidad de un par\\de usuarios (\\litwareinc Pilar y litwareinc kenmyer) para iniciar sesión en Lync Server 2013 y, a continuación, realizar una conferencia de uso compartido de aplicaciones. Para ello, el primer comando del ejemplo usa el cmdlet Get-Credential para crear un objeto de credencial de interfaz de línea de comandos de Windows PowerShell que contiene el nombre y la contraseña del usuario Pilar Ackerman. (Como el nombre de inicio de\\sesión, litwareinc pilar, se ha incluido como parámetro, el cuadro de diálogo solicitud de credenciales de Windows PowerShell solo requiere que el administrador escriba la contraseña de la cuenta Pilar Ackerman). El objeto Credential resultante se almacena en una variable llamada $cred 1. El segundo comando realiza la misma acción pero, esta vez, devuelve un objeto de credenciales de la cuenta de Ken Myer.

Con los objetos de credenciales a mano, el tercer comando determina si estos dos usuarios pueden iniciar sesión en Lync Server 2013 y realizar una conferencia de uso compartido de aplicaciones. Para llevar a cabo esta tarea, se llama al cmdlet **Test-CsASConference** , junto con los siguientes parámetros: TargetFqdn (el FQDN del grupo de registrador); SenderSipAddress (la dirección SIP del primer usuario de prueba); SenderCredential (el objeto de Windows PowerShell que contiene las credenciales para este mismo usuario); ReceiverSipAddress (la dirección SIP del otro usuario de prueba); y ReceiverCredential (el objeto de Windows PowerShell que contiene las credenciales del otro usuario de prueba).

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si el uso compartido de aplicaciones está configurado correctamente, recibirá un resultado similar al siguiente, con la propiedad result marcada como **correcta:**

FQDN de destino: atl-cs-001.litwareinc.com

Resultado: correcto

Latencia: 00:00:01

Mensaje de error:

Diagnóstico

Si los usuarios especificados no pueden compartir aplicaciones, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnosis:

FQDN de destino: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

Mensaje de error: 10060, se ha producido un error en el intento de conexión porque la entidad conectada

no respondió correctamente después de un período de tiempo o

error en la conexión establecida porque el host conectado tiene

no se pudo responder 10.188.116.96:5061

Excepción interna: error en el intento de conexión porque el

la parte conectada no respondió correctamente después de un período de

tiempo o error de conexión establecida debido a que el host conectado

Error al responder 10.188.116.96:5061

Diagnóstico

Por ejemplo, la salida anterior incluye la nota "la persona conectada no respondió correctamente" que normalmente indica un problema con el servidor perimetral.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que **Test-CsASConference** podría fallar:

  - Se ha suministrado un valor de parámetro incorrecto. Si se usa, los parámetros opcionales deben configurarse correctamente o se producirá un error en la prueba. Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.

  - Se producirá un error en este comando si a los usuarios de prueba se les asignó una directiva de conferencia que les impida usar el uso compartido de aplicaciones.

  - Este comando producirá un error si el servidor perimetral está mal configurado o no se ha implementado todavía.

</div>

<div>

## <a name="see-also"></a>Vea también


[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

