---
title: 'Lync Server 2013: probar la capacidad de usar la expansión de grupos'
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
ms.openlocfilehash: 358d869f212ac3acef91e28ddb8d08322133970f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a>Probar la capacidad de usar la expansión de grupos en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsGroupExpansion. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet test-CsGroupExpansion le permite determinar si la expansión de grupos funciona dentro de su organización. Cuando la expansión de grupos está habilitada, los usuarios configuran los grupos de distribución como un contacto. Esto significa que los usuarios pueden enviar el mismo mensaje instantáneo a todos los miembros del grupo al dirigir el mensaje al grupo en lugar de a los miembros individuales de ese grupo. La expansión de grupos permite ver, rápida y fácilmente, todos los miembros del grupo y su estado actual.

Con el cmdlet test-CsGroupExpansion, puede especificar un grupo de distribución de Active Directory mediante la dirección de correo electrónico del grupo. Test-CsGroupExpansion usa la expansión de grupos para recuperar la pertenencia a grupos y compara la lista recuperada con la pertenencia de la dirección de correo electrónico del grupo que ha proporcionado. Si las dos listas coinciden, la expansión de grupos funciona correctamente. Tenga en cuenta que puede probar la expansión de grupos de dos maneras: probando el servicio mismo o probando el servicio web asociado.

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet test-CsGroupExpansion se puede ejecutar con una cuenta de prueba preconfigurada (consulte la configuración de las cuentas de prueba para ejecutar pruebas de Lync Server) o en la cuenta de cualquier usuario que se haya habilitado para Lync Server. Para ejecutar esta comprobación con una cuenta de prueba, solo tiene que especificar el FQDN del grupo de Lync Server que se está probando y la dirección de correo electrónico de un grupo de distribución válido. Por ejemplo:

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

Para ejecutar esta comprobación con una cuenta de usuario real, primero debe crear un objeto de credenciales de Lync Server que contenga el nombre y la contraseña de la cuenta. A continuación, debe incluir ese objeto Credentials y la dirección SIP asignada a la cuenta cuando el sistema llame a test-CsGroupExpansion:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si el usuario especificado puede usar la expansión de grupo, recibirá un resultado similar al siguiente con la propiedad result marcada como **correcta:**

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: correcto

Latencia: 00:00:01.1234976

Error

Diagnóstico

Si el usuario especificado no puede usar la expansión de grupo, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnosis:

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

Error

Diagnóstico

Test-CsGroupExpansion: el punto de conexión no se pudo registrar. Consulte ErrorCode por motivos específicos.

La salida anterior indica que se produjo un error en la prueba porque el usuario especificado no se pudo registrar con Lync Server. Normalmente, esto ocurrirá si la cuenta de prueba no existe o no se ha habilitado para Lync Server. Puede comprobar que la cuenta existe y determinar si la cuenta se ha habilitado para nm-OCS-14-3rd ejecutando un comando similar al siguiente:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

Si test-CsGroupExpansion produce un error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

Cuando se incluye el parámetro verbose, test-CsGroupExpansion devolverá una cuenta paso a paso de cada acción que se intentó realizar cuando se comprobó la capacidad del usuario especificado para iniciar sesión en Lync Server. Por ejemplo, este resultado indica que no se encontró el grupo de distribución especificado:

Intentando obtener el vale Web.

Dirección URL del servicio Web:https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc

Uso de la autenticación NTLM/Kerbtray

GetWebTicketActivity completado.

Se inició la actividad ' VerifyDistributionList '.

El estado de respuesta del servicio Web de DLX es: NotFound.

Actividad ' VerifyDistributionList ' completada en ' 0,2597923 ' en segundos.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que test-CsGroupExpansion podría fallar:

  - Ha especificado una cuenta de usuario no válida. Puede comprobar si existe una cuenta de usuario mediante la ejecución de un comando similar al siguiente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server. Para comprobar que una cuenta de usuario se habilitó para Lync Server, ejecute un comando similar al siguiente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.

  - La expansión del grupo puede estar deshabilitada. Es posible desactivar la expansión de grupos. Si se deshabilitó la expansión de grupos, se producirá un error en el cmdlet test-CsGroupExpansion. Para determinar si la expansión de grupos está habilitada, use un comando similar al siguiente:
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

