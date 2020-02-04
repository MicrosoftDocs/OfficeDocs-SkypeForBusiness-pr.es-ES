---
title: 'Lync Server 2013: capacidad de prueba de la mensajería instantánea entre dos usuarios'
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
ms.openlocfilehash: 201aceceadeba3c6c97530925273097fe039bc08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a>Posibilidad de probar la mensajería instantánea entre dos usuarios en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsIM. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet test-CsIM verifica que un par de usuarios de prueba puedan intercambiar mensajes instantáneos. Cuando se llama, el cmdlet test-CsIM comienza intentando iniciar sesión en un par de usuarios de prueba en Lync Server. Suponiendo que los dos inicios de sesión se hayan realizado correctamente, el cmdlet inicia una sesión de mensajería instantánea entre los dos usuarios de prueba. (El usuario 1 invita al usuario 2 a una sesión de mensajería instantánea y el usuario 2 la acepta). Después de comprobar que los mensajes se pueden intercambiar entre los dos usuarios, test-CsIM finaliza la sesión de mensajería instantánea y registra a ambos usuarios del sistema.

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet test-CsIM se puede ejecutar con un par de cuentas de prueba preconfiguradas (consulte Configurar cuentas de prueba para ejecutar pruebas de Lync Server) o las cuentas de dos usuarios que están habilitados para Lync Server. Para ejecutar esta comprobación mediante cuentas de prueba, solo tiene que especificar el FQDN del grupo de servidores de Lync que se está probando. Por ejemplo:

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

Para ejecutar esta comprobación con las cuentas de usuario reales, debe crear dos objetos de credenciales de Windows PowerShell (objetos que contengan el nombre y la contraseña de la cuenta) de cada cuenta. Después, debe incluir esos objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a test-CsIM:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si los dos usuarios pueden completar una sesión de mensajería instantánea, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: éxito

Latencia: 00:00:06.6630911

:

Diagnóstico

Si los usuarios de prueba no pueden completar la sesión, el resultado se mostrará como error y la información adicional se registrará en las propiedades de error y diagnóstico:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

Error: 504, tiempo de espera del servidor

Diagnosis: ErrorCode = 2, Source = ATL-CS-001. litwareinc. com, razón = ver

código de respuesta y frase de motivo.

Microsoft. RTC. Signaling. DiagnosticHeader

Por ejemplo, la salida anterior indica que se produjo un error en la prueba porque no se encontró el usuario especificado. Puede determinar si una dirección SIP es válida (y si el usuario asignó la dirección SIP a Lync Server) ejecutando este comando:

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

Si prueba-CsIM da error, es posible que desee volver a ejecutar la prueba, esta vez incluido el parámetro detallado:

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Cuando se incluye el parámetro detallado, test-CsIM devolverá una cuenta paso a paso de cada acción que se probó cuando se comprobó la capacidad de los dos usuarios de prueba para tomar parte en una sesión de mensajería instantánea. Por ejemplo, este es un resultado de ejemplo que se produce cuando se proporciona un conjunto incorrecto de credenciales de usuario (en este caso, una contraseña incorrecta) para probar-CsIM:

Enviando solicitud de registro:

FQDN de destino = atl-cs-011.litwareinc.com

Dirección SIP del usuario = sip:kenmyer@litwareinc.com

Registrar puerto = 5061

El tipo de autenticación ' IWA ' está seleccionado.

Registro de visitas contra SIP/ATL-CS-001. litwareinc. com

Actividad ' Register ' completada en ' 0,0601795 ' s.

Excepción ' se denegó el inicio de sesión. Compruebe que se están usando las credenciales correctas y que la cuenta está activa. durante el flujo de trabajo.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que test-CsIM podría fallar:

  - Ha especificado una cuenta de usuario que no es válida. Puede comprobar que una cuenta de usuario existe ejecutando un comando similar a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server. Para comprobar que una cuenta de usuario está habilitada para Lync Server, ejecute un comando similar al siguiente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.

  - Es posible que el servicio de mensajería instantánea no esté disponible. Con Lync Server, puede configurar el sistema para que el mensaje instantáneo no esté disponible si no se puede obtener acceso a la base de datos de archivado. Puede comprobar que al ejecutar un comando similar al siguiente:
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    Si BlockOnArchiveFailure se establece en true, debe determinar si la base de datos de archivado está disponible o no. Puede devolver las ubicaciones de las bases de datos de archivado con el siguiente comando:
    
        Get-CsService -ArchivingDatabase

  - Es posible que el servidor de archivado no esté disponible. Puede recuperar el FQDN de los servidores de archivado con este comando:
    
        Get-CsService -ArchivingServer
    
    Después, puede hacer ping al servidor apropiado para comprobar que está disponible. Por ejemplo:
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

