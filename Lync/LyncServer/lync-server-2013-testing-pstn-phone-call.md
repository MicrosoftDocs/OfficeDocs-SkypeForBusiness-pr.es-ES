---
title: 'Lync Server 2013: prueba de llamadas telefónicas RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing PSTN phone call
ms:assetid: dc7d319d-a627-45b6-a978-6111901251e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690133(v=OCS.15)
ms:contentKeyID: 63969656
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 641b2f77079fee100d8f3ac85a1a7580d7cf7d84
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-in-lync-server-2013"></a>Prueba de llamadas telefónicas RTC en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsRegistration. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet test-CsPstnOutboundCall prueba la capacidad de un usuario de hacer una llamada a un número de teléfono ubicado en la RTC. Al ejecutar test-CsPstnOutboundCall, el cmdlet primero intenta registrar el usuario de prueba en Lync Server. Si el inicio de sesión se realiza correctamente, el cmdlet intentará realizar una llamada telefónica en la puerta de enlace PSTN. Esta llamada telefónica se realizará con el plan de marcado, la Directiva de voz y otras directivas y parámetros asignados a la cuenta de prueba. Cuando se responde a la llamada, el cmdlet envía códigos de multifrecuencia de doble tono (DTMF) a través de la red para comprobar la conectividad de los medios.

Al realizar su prueba, test-CsPstnOutboundCall hará una llamada real: el teléfono de destino sonará y debe responderse para que la prueba se realice correctamente. Esta llamada también debe ser finalizada manualmente por el administrador.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet test-CsPstnOutboundCall se puede ejecutar mediante una cuenta de prueba preconfigurada (consulte Configurar cuentas de prueba para ejecutar pruebas de Lync Server) o la cuenta de cualquier usuario que esté habilitado para Lync Server. Para ejecutar esta comprobación mediante una cuenta de prueba, solo tiene que especificar el FQDN del grupo de Lync Server que se está probando y el número de teléfono RTC al que se llama. Por ejemplo:

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

Para ejecutar esta comprobación mediante una cuenta de usuario real, primero debe crear un objeto de credenciales de Windows PowerShell que contenga el nombre de la cuenta y la contraseña. Después debes incluir ese objeto de credenciales y la dirección SIP asignada a la cuenta al llamar a test-CsPstnOutboundCall:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si el usuario especificado puede realizar la llamada y se responde a la llamada, recibirá una salida similar a la siguiente y la propiedad result se marcará como **correcta:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: éxito

Latencia: 00:00:06.8630376

:

Diagnóstico

Si el usuario especificado no puede hacer la llamada o si la llamada no es contestada, el resultado se mostrará como error y la información adicional se registrará en las propiedades de error y diagnóstico:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:0987365

Error: 403, prohibido

Diagnosis: ErrorCode = 12001, Source = ATL-CS-001. litwareinc. com, Reason = User

La Directiva no contiene uso de la ruta telefónica

El resultado anterior indica que no se pudo realizar la prueba porque la Directiva de voz asignada al usuario especificado no incluye un uso de teléfono. (Las directivas de voz se asocian con las directivas de voz. Sin una directiva de voz y una ruta de voz correspondiente, no puede hacer llamadas a través de la RTC.

Si prueba-CsPstnOutboundCall da error, es posible que desee volver a ejecutar la prueba, esta vez incluido el parámetro detallado:

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

Cuando se incluye el parámetro detallado, test-CsPstnOutboundCall devolverá una cuenta paso a paso de cada acción que se probó cuando se comprobó la capacidad del usuario especificado para iniciar sesión en Lync Server. Por ejemplo, esta salida indica que hay problemas de red que impiden una conexión con la RTC:

Establecer videollamadas de audio a ' SIP: +12065551219@litwareinc.com; User = Phone '.

Se ha recibido una respuesta ' una 404 (no se encontró) de la red y se produjo un error en la operación.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que test-CsPstnOutboundCall podría fallar:

  - Ha especificado una cuenta de usuario no válida. Puede comprobar que una cuenta de usuario existe ejecutando un comando similar a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server. Para comprobar que una cuenta de usuario está habilitada para Lync Server, ejecute un comando similar al siguiente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.

  - La Directiva de voz asignada al usuario especificado no tiene un uso de RTC válido. Puede determinar la Directiva de voz asignada a un usuario mediante un comando similar a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    Y, después, puede determinar los usos de RTC (si los hay) que se asignan a esa Directiva mediante un comando similar al siguiente, que recupera información sobre la Directiva de voz por usuario RedmondVoicePolicy:
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

