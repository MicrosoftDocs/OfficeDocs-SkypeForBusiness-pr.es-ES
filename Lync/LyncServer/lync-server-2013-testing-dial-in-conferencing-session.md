---
title: 'Lync Server 2013: probar la sesión de conferencia de acceso telefónico local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing dial-in conferencing session
ms:assetid: 6c505be5-5af7-450c-b3ca-10d9122bee5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743834(v=OCS.15)
ms:contentKeyID: 63969613
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efcc6d9277f7333989c59b812ed76087b9b6ca9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a>Probar la sesión de conferencia de acceso telefónico local en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsDialInConferencing. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet test-CsDialInConferencing comprueba si un usuario puede participar en una conferencia de acceso telefónico local. Test-CsDialInConferencing funciona intentando registrar un usuario de prueba en el sistema. Si el inicio de sesión se realiza correctamente, el cmdlet usará las credenciales y permisos del usuario para probar todos los números de acceso disponibles para la Conferencia de acceso telefónico local. El éxito o el fracaso de cada prueba de acceso telefónico se anotará, luego el usuario de prueba se cerrará en Lync Server. prueba-CsDialInConferencing solo verifica que se puedan realizar las conexiones apropiadas. En realidad, el cmdlet no realiza llamadas telefónicas ni crea conferencias de acceso telefónico local a las que otros usuarios pueden unirse.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet test-CsDialInConferencing se puede ejecutar mediante una cuenta de prueba preconfigurada (consulte Configurar cuentas de prueba para ejecutar pruebas de Lync Server) o la cuenta de cualquier usuario que esté habilitado para Lync Server. Para ejecutar esta comprobación mediante una cuenta de prueba, solo tiene que especificar el FQDN del grupo de servidores de Lync que se está probando. Por ejemplo:

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

Para ejecutar esta comprobación mediante una cuenta de usuario real, debe crear un objeto de credenciales de Windows PowerShell que contenga el nombre de la cuenta y la contraseña. A continuación, debe incluir ese objeto de credenciales y la dirección SIP de la cuenta de la prueba de llamada: CsDialInConferencing:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si el usuario especificado puede iniciar sesión en Lync Server y, a continuación, realizar una conexión con uno de los números de acceso de conferencia de acceso telefónico local disponibles, recibirá un resultado similar a este, con la propiedad result marcada como **correcta:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: éxito

Latencia: 00:00:06.8630376

:

Diagnóstico

Si el usuario especificado no puede establecer esta conexión, el resultado se mostrará como error y la información adicional se registrará en las propiedades de diagnóstico y errores:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

Error: se denegó el inicio de sesión. Comprobar que las credenciales correctas son

se está usando y la cuenta está activa.

Excepción interna: error de NegotiateSecurityAssociation, error:-

2146893044

Diagnóstico

El resultado anterior indica que el usuario de prueba ha denegado el acceso a Lync Server. Normalmente, esto significa que las credenciales de usuario pasadas a test-CsDialInConferencing no eran válidas. A su vez, debe volver a crear el objeto de credenciales de Windows PowerShell. Aunque puede recuperar la contraseña de la cuenta de usuario, puede comprobar la dirección SIP con un comando parecido a este:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que test-CsDialInConferencing podría fallar:

  - Ha especificado una cuenta de usuario que no es válida. Puede comprobar que una cuenta de usuario existe ejecutando un comando similar a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server. Para comprobar que una cuenta de usuario está habilitada para Lync Server, ejecute un comando similar al siguiente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.

  - Es posible que tenga un número de acceso de conferencia de acceso telefónico local incorrecto. Puede devolver la lista configurada actualmente de números de acceso a la Conferencia de acceso telefónico local con este comando:
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

