---
title: 'Lync Server 2013: probar reglas, rutas y directivas de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b3d0cec7e5bd127f5b69eba6956fc3c653cfa51
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a>Probar reglas, rutas y directivas de voz en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-20_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Programación de verificación</p></td>
<td><p>Cada mes</p></td>
</tr>
<tr class="even">
<td><p>Herramienta de prueba</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permisos necesarios</p></td>
<td><p>Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</p>
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsVoiceUser. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

Cuando un usuario realiza una llamada, la ruta que la llamada toma para alcanzar su destino depende de las directivas y los planes de marcado asignados a ese usuario. Dada la dirección SIP de un usuario y un número de teléfono, el cmdlet test-CsVoiceUser verifica si el usuario en cuestión puede completar una llamada a ese número. Si la prueba se realiza correctamente, test-CsVoiceUser devuelve lo siguiente:

  - El número traducido al formato E. 164 (según el plan de marcado del usuario)

  - Regla de normalización que proporcionó esa traducción

  - La ruta de voz usada (según la prioridad de la ruta);

  - El uso del teléfono que vinculó la Directiva de voz del usuario a la ruta de voz.

Prueba-CsVoiceUser le permite determinar si un número de teléfono específico se enrutará y se traducirá como se espera, y puede ayudarle a solucionar problemas relacionados con la llamada que experimentan los usuarios individuales.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

Al ejecutar el cmdlet test-CsVoiceUser, debe proporcionar dos datos: el número que se marca (DialedNumber) y la identidad de la cuenta de usuario que se está probando. Por ejemplo, este comando prueba la capacidad del usuario que tiene la dirección SIP sip:kenmyer@litwareinc.com para hacer una llamada al número de teléfono + 1206555-1219:

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

El número de teléfono debe tener el formato que espera que se marque. Por ejemplo, si los usuarios normalmente no marcan el 1 antes de hacer una llamada de larga distancia, debe usar este formato:

`-DialedNumber "2065551219"`

Por supuesto, en ese caso, la prueba fallará si no tiene una regla de normalización que pueda traducir correctamente el número 2065551219 en el formato de teléfono E. 164 que usa Lync Server. Para obtener más información, vea el tema sobre el cmdlet New-CsVoiceNormalizationRule de la ayuda.

Si desea ejecutar esta misma prueba en cada una de sus cuentas de usuario, puede usar un comando similar al siguiente:

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

Para obtener más información, consulte la documentación de ayuda del cmdlet test-CsVoiceUser.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si la prueba se completa correctamente (es decir, si el usuario puede hacer una llamada telefónica al número especificado), la salida mostrará información como el número de teléfono traducido y la regla de normalización correspondiente y la ruta de voz:

TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage

\----------------    ------------    ------------------    -------------

\+12065551219 unscripti...    LocalRoute local

Debido a las limitaciones de la pantalla de Windows PowerShell, al menos parte de la información devuelta (principalmente, la descripción completa de la regla de normalización correspondiente) podría no aparecer en pantalla. Si solo le interesa el éxito o el fracaso de la prueba, esto podría no importarse. Si prefiere ver los detalles completos de los datos devueltos, Canalice el resultado al cmdlet Format-List al ejecutar la prueba:

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

Eso mostrará la salida en un formato más fácil de obtener:

TranslatedNumber: + 12065551219

MatchingRule: Descripción =; Patrón = ^ (\\d{11}) $; Traducción = + $1;

Nombre = prefijo All; IsInternalExtension = false

FirsMatchingRoute : LocalRoute

MatchingUsage: local

Si la prueba no se realiza correctamente, test-CsVoiceUser devolverá un conjunto vacío de valores de propiedad:

TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage

\---------------- ------------ ------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Hay varias razones por las que el cmdlet test-CsVoiceUser puede dar error: es posible que no haya una regla de normalización que pueda traducir el número de teléfono proporcionado. Puede haber problemas con la ruta de voz. Podría haber un problema de configuración con el plan de marcado asignado al usuario en cuestión. Por eso, es posible que desee incluir el parámetro verbose al ejecutar el cmdlet test-CsVoiceUser:

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

Cuando se incluye el cmdlet detallado, test-CsVoiceUser emitirá una cuenta detallada de todos los pasos que se lleven a cabo al realizar las comprobaciones. Por ejemplo, es posible que vea pasos similares a estos: 

VERBOse: ubicar un usuario con la identidad "sip:kenmyer@litwareinc.com"

DETALLADO: cargando plan de marcado: "RedmondDialPlan"

Esta información adicional puede proporcionar consejos sobre los pasos que puede tomar para determinar la causa del error. Por ejemplo, la salida detallada que se muestra aquí nos dice que al usuario que se está probando se le asignó el plan de marcado RedmondDialPlan. Si la prueba ha fallado, un paso siguiente lógico sería comprobar que RedmondDialPlan puede traducir el número de teléfono suministrado.

</div>

<div>

## <a name="see-also"></a>Vea también


[Test-CsVoiceUser](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

