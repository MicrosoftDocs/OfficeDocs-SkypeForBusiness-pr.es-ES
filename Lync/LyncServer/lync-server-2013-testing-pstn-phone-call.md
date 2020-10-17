---
title: 'Lync Server 2013: prueba de llamadas de teléfono RTC'
description: 'Lync Server 2013: prueba de llamadas telefónicas RTC.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call
ms:assetid: dc7d319d-a627-45b6-a978-6111901251e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690133(v=OCS.15)
ms:contentKeyID: 63969656
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b42ea6dd46145961a34386d704f8f44e9b7909ad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547406"
---
# <a name="testing-pstn-phone-call-in-lync-server-2013"></a>Prueba de llamadas de teléfono RTC en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsRegistration. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet Test-CsPstnOutboundCall comprueba la capacidad de un usuario de realizar una llamada a un número de teléfono ubicado en la RTC. Al ejecutar test-CsPstnOutboundCall, el cmdlet intenta iniciar sesión en Lync Server en el primer lugar del usuario. Si el inicio de sesión se realiza correctamente, el cmdlet intentará realizar una llamada telefónica en la puerta de enlace RTC. Esta llamada telefónica se realizará mediante el plan de marcado, la Directiva de voz y otras directivas y configuraciones asignadas a la cuenta de prueba. Cuando se responde a la llamada, el cmdlet envía códigos de tono de marcado de frecuencia múltiple (DTMF) a través de la red para comprobar la conectividad de los medios.

Al realizar su prueba, Test-CsPstnOutboundCall realizará una llamada de teléfono real: el teléfono de destino sonará y debe responderse para que la prueba se realice correctamente. El administrador también debe finalizar manualmente esta llamada.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet Test-CsPstnOutboundCall se puede ejecutar con una cuenta de prueba preconfigurada (consulte la configuración de las cuentas de prueba para ejecutar pruebas de Lync Server) o en la cuenta de cualquier usuario que esté habilitado para Lync Server. Para ejecutar esta comprobación con una cuenta de prueba, solo tiene que especificar el FQDN del grupo de Lync Server que se está probando y el número de teléfono RTC al que se llama. Por ejemplo:

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

Para ejecutar esta comprobación con una cuenta de usuario real, primero debe crear un objeto de credenciales de Windows PowerShell que contenga el nombre y la contraseña de la cuenta. A continuación, debe incluir ese objeto Credentials y la dirección SIP asignada a la cuenta al llamar a test-CsPstnOutboundCall:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si el usuario especificado puede realizar la llamada y si se responde a la llamada, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: correcto

Latencia: 00:00:06.8630376

Error

Diagnóstico

Si el usuario especificado no puede realizar la llamada o si no se responde a la llamada, el resultado se mostrará como error y se registrará información adicional en las propiedades error y diagnosis:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:0987365

Error: 403, prohibido

Diagnosis: ErrorCode = 12001, Source = ATL-CS-001. litwareinc. com, Reason = User

La Directiva no contiene uso de ruta telefónica

La salida anterior indica que la prueba produjo un error porque la Directiva de voz asignada al usuario especificado no incluye un uso de teléfono. (Los usos de teléfono unen las directivas de voz a las rutas de voz. Sin una directiva de voz y una ruta de voz correspondiente, no se pueden realizar llamadas a través de la RTC.

Si Test-CsPstnOutboundCall da error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

Cuando se incluye el parámetro verbose, Test-CsPstnOutboundCall devolverá una cuenta paso a paso por cada acción que se intentó realizar cuando se comprobó la capacidad del usuario especificado para iniciar sesión en Lync Server. Por ejemplo, este resultado indica que hay problemas de red que impiden la conexión con la RTC:

Establecimiento de una llamada de audio en vídeo a ' SIP: + 12065551219@litwareinc. com; User = Phone '.

Se ha recibido una respuesta de excepción de 404 (no se encontró) desde la red y se ha producido un error en la operación.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que Test-CsPstnOutboundCall podría producir un error:

  - Ha especificado una cuenta de usuario no válida. Puede comprobar si existe una cuenta de usuario mediante la ejecución de un comando similar al siguiente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server. Para comprobar que una cuenta de usuario está habilitada para Lync Server, ejecute un comando similar al siguiente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.

  - La Directiva de voz asignada al usuario especificado no tiene un uso de RTC válido. Puede determinar la Directiva de voz que se asigna a un usuario mediante un comando similar a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    A continuación, puede determinar los usos de RTC (si los hay) asignados a esa Directiva mediante un comando similar al siguiente, que recupera información sobre la Directiva de voz por usuario RedmondVoicePolicy:
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

