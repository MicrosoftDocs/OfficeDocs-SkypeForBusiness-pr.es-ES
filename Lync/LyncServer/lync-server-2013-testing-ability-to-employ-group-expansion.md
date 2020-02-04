---
title: 'Lync Server 2013: capacidad de pruebas para usar la expansión de grupos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d79c5432bc2efca0d3a958d3837793eaf227b251
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a>Capacidad de pruebas para emplear la expansión de grupos en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsGroupExpansion. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet test-CsGroupExpansion le permite determinar si la expansión de grupos está funcionando en su organización. Cuando la expansión de grupo está habilitada, los usuarios configuran grupos de distribución como un contacto. Eso significa que los usuarios pueden enviar el mismo mensaje instantáneo a todos los miembros del grupo si dirigen el mensaje al grupo en lugar de a los miembros individuales de ese grupo. La expansión grupal te permite ver de forma rápida y sencilla a todos los miembros del grupo y su estado actual.

Con el cmdlet test-CsGroupExpansion, especifique un grupo de distribución de Active Directory mediante la dirección de correo electrónico del grupo. Prueba-CsGroupExpansion usa la expansión de grupo para recuperar la pertenencia a grupos y comparar la lista recuperada con la pertenencia de la dirección de correo electrónico del grupo que proporcionaste. Si las dos listas coinciden, la expansión del grupo funciona correctamente. Tenga en cuenta que puede probar la expansión de grupos de dos maneras: probando el servicio o probando el servicio web asociado.

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet test-CsGroupExpansion se puede ejecutar mediante una cuenta de prueba preconfigurada (consulte Configurar cuentas de prueba para ejecutar pruebas de Lync Server) o la cuenta de cualquier usuario que se haya habilitado para Lync Server. Para ejecutar esta comprobación mediante una cuenta de prueba, solo tiene que especificar el FQDN del grupo de servidores de Lync que se está probando y la dirección de correo electrónico de un grupo de distribución válido. Por ejemplo:

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

Para ejecutar esta comprobación mediante una cuenta de usuario real, primero debe crear un objeto de credenciales de Lync Server que contenga el nombre y la contraseña de la cuenta. Después, debes incluir ese objeto de credenciales y la dirección SIP asignada a la cuenta cuando el sistema llame test-CsGroupExpansion:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si el usuario especificado puede usar la expansión de grupo, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta:**

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: éxito

Latencia: 00:00:01.1234976

:

Diagnóstico

Si el usuario especificado no puede usar la expansión de grupo, el resultado se mostrará como error y la información adicional se registrará en las propiedades de diagnóstico y errores:

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

:

Diagnóstico

Prueba-CsGroupExpansion: el punto de conexión no se pudo registrar. Consulte ErrorCode por razones específicas.

El resultado anterior indica que no se pudo realizar la prueba porque el usuario especificado no se pudo registrar en Lync Server. Esto suele ocurrir si la cuenta de prueba no existe o no ha habilitado para Lync Server. Puede comprobar que la cuenta existe y determinar si la cuenta se ha habilitado para nm-OCS-14-3rd ejecutando un comando similar al siguiente:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

Si prueba-CsGroupExpansion da error, es posible que desee volver a ejecutar la prueba, esta vez incluido el parámetro detallado:

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

Cuando se incluye el parámetro detallado, test-CsGroupExpansion devolverá una cuenta paso a paso de cada acción que se probó cuando se comprobó la capacidad del usuario especificado para iniciar sesión en Lync Server. Por ejemplo, este resultado indica que no se pudo encontrar el grupo de distribución especificado:

Intentando obtener vale Web.

Dirección URL del servicio Web:https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc

Uso de NTLM/Kerb auth.

GetWebTicketActivity completado.

Actividad ' VerifyDistributionList ' iniciada.

El estado de respuesta del servicio Web de DLX es: NotFound.

Actividad ' VerifyDistributionList ' completada en ' 0,2597923 ' s.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que test-CsGroupExpansion podría fallar:

  - Ha especificado una cuenta de usuario no válida. Puede comprobar que una cuenta de usuario existe ejecutando un comando similar a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server. Para comprobar que una cuenta de usuario se ha habilitado para Lync Server, ejecute un comando similar al siguiente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.

  - Es posible que la expansión del grupo esté deshabilitada. Es posible desactivar la expansión de grupos. Si se deshabilitó la expansión de grupos, el cmdlet test-CsGroupExpansion fallará. Para determinar si la expansión de grupo está habilitada, use un comando similar a este:
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

