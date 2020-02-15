---
title: 'Lync Server 2013: posibilidad de probar la mensajería instantánea entre dos usuarios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to IM between two users
ms:assetid: a0f3f5c6-f115-4c3f-90ac-5fdc932b417e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743838(v=OCS.15)
ms:contentKeyID: 63969635
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d08627842b5a58a72801a018e8e8da49fcdeb249
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42015373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a>Probar la capacidad de mensajería instantánea entre dos usuarios en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsIM. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet test-CsIM comprueba que un par de usuarios de prueba puedan intercambiar mensajes instantáneos. Cuando se llama, el cmdlet test-CsIM se inicia intentando iniciar sesión en un par de usuarios de prueba en Lync Server. Si los dos inicios de sesión son correctos, el cmdlet inicia una sesión de mi entre los dos usuarios de prueba. (El usuario 1 invita al usuario 2 a una sesión de mi y el usuario 2 acepta la invitación). Después de comprobar que se pueden intercambiar mensajes entre los dos usuarios, test-CsIM finaliza la sesión de mensajería instantánea y registra a ambos usuarios fuera del sistema.

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet test-CsIM se puede ejecutar usando un par de cuentas de prueba preconfiguradas (consulte Setting up test accounts for Running Lync Server test) o las cuentas de dos usuarios que están habilitados para Lync Server. Para ejecutar esta comprobación mediante cuentas de prueba, solo tiene que especificar el FQDN del grupo de Lync Server que se está probando. Por ejemplo:

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

Para ejecutar esta comprobación con las cuentas de usuario reales, debe crear dos objetos de credenciales de Windows PowerShell (objetos que contienen el nombre de cuenta y la contraseña) para cada cuenta. A continuación, debe incluir dichos objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a test-CsIM:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si los dos usuarios pueden completar una sesión de mensajería instantánea, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: correcto

Latencia: 00:00:06.6630911

Error

Diagnóstico

Si los usuarios de prueba no pueden completar la sesión, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnosis:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

Error: 504, tiempo de espera del servidor

Diagnosis: ErrorCode = 2, Source = ATL-CS-001. litwareinc. com, Reason = vea

código de respuesta y frase de motivo.

Microsoft. RTC. Signaling. DiagnosticHeader

Por ejemplo, la salida anterior indica que se produjo un error en la prueba porque no se encontró el usuario especificado. Puede determinar si una dirección SIP es válida (y si el usuario asignado a esa dirección SIP está habilitado para Lync Server) ejecutando este comando:

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

Si test-CsIM produce un error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Cuando se incluye el parámetro verbose, test-CsIM devolverá una cuenta paso a paso de cada acción que se intentó realizar cuando se comprobó la capacidad de los dos usuarios de prueba para participar en una sesión de mensajería instantánea. Por ejemplo, aquí se muestran los resultados de ejemplo que se producen cuando se proporciona un conjunto incorrecto de credenciales de usuario (en este caso, una contraseña incorrecta) para test-CsIM:

Enviando solicitud de registro:

FQDN de destino = atl-cs-011.litwareinc.com

Dirección SIP del usuario = sip:kenmyer@litwareinc.com

Puerto del registrador = 5061

El tipo de autenticación "IWA" está seleccionado.

Aciertos de registro en SIP/ATL-CS-001. litwareinc. com

La actividad "Register" se completó en "0,0601795" segundos.

Excepción: "se denegó el inicio de sesión. Compruebe que se usan las credenciales correctas y que la cuenta está activa. se produjo durante el flujo de trabajo.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que test-CsIM podría fallar:

  - Ha especificado una cuenta de usuario que no es válida. Puede comprobar si existe una cuenta de usuario mediante la ejecución de un comando similar al siguiente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server. Para comprobar que una cuenta de usuario está habilitada para Lync Server, ejecute un comando similar al siguiente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.

  - Es posible que el servicio de mensajería instantánea no esté disponible. Con Lync Server, puede configurar el sistema para que mi no esté disponible si no se puede tener acceso a la base de datos de archivado. Puede comprobar si ejecuta un comando similar al siguiente:
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    Si BlockOnArchiveFailure se establece en true, debe determinar si la base de datos de archivado está disponible o no. Puede devolver las ubicaciones de las bases de datos de archivado con el siguiente comando:
    
        Get-CsService -ArchivingDatabase

  - Es posible que el servidor de archivado no esté disponible. Puede recuperar el FQDN de los servidores de archivado con este comando:
    
        Get-CsService -ArchivingServer
    
    A continuación, puede hacer ping en el servidor adecuado para comprobar que está disponible. Por ejemplo:
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

