---
title: 'Lync Server 2013: probar reglas, rutas y directivas de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8da7334e00c0361a5c8ad840dbf57ee7d5024763
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a>Probar reglas de voz, rutas y directivas en Lync Server 2013

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
<td><p>Programación de comprobación</p></td>
<td><p>Mensualmente</p></td>
</tr>
<tr class="even">
<td><p>Herramienta de prueba</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permisos necesarios</p></td>
<td><p>Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</p>
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsVoiceUser. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

Cuando un usuario realiza una llamada telefónica, la ruta que toma la llamada para llegar a su destino depende de las directivas y los planes de marcado asignados a ese usuario. Según la dirección SIP de un usuario y un número de teléfono, el cmdlet test-CsVoiceUser comprueba si el usuario en cuestión puede completar una llamada a ese número. Si la prueba es correcta, test-CsVoiceUser devuelve lo siguiente:

  - El número convertido al formato E. 164 (basado en el plan de marcado del usuario)

  - La regla de normalización que suministró esa traducción

  - La ruta de voz usada (en función de la prioridad de ruta);

  - El uso del teléfono que vinculó la Directiva de voz del usuario a la ruta de voz.

Test-CsVoiceUser permite determinar si un número de teléfono específico se enrutará y traducirá como se esperaba, y puede ayudar a solucionar problemas relacionados con la llamada que experimentan los usuarios individuales.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

Al ejecutar el cmdlet test-CsVoiceUser, debe proporcionar dos datos: el número que se marca (DialedNumber) y la identidad de la cuenta de usuario que se está probando. Por ejemplo, este comando comprueba la capacidad del usuario que tiene la dirección SIP sip:kenmyer@litwareinc.com para realizar una llamada al número de teléfono + 1206555-1219:

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

El número de teléfono debe tener el formato de la forma en que espera que se marque. Por ejemplo, si los usuarios no suelen marcar el 1 antes de realizar una llamada de larga distancia, debe usar este formato:

`-DialedNumber "2065551219"`

Por supuesto, en ese caso, se producirá un error en la prueba si no tiene una regla de normalización que pueda traducir correctamente el número 2065551219 en el formato de teléfono E. 164 que usa Lync Server. Para obtener más información, consulte el cmdlet New-CsVoiceNormalizationRule del tema de ayuda.

Si desea ejecutar esta misma prueba en cada una de las cuentas de usuario, puede usar un comando similar al siguiente:

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

Para obtener más información, consulte la documentación de ayuda del cmdlet test-CsVoiceUser.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si la prueba se completa correctamente (es decir, si el usuario puede realizar una llamada telefónica al número especificado), el resultado mostrará información como el número de teléfono convertido y la regla de normalización de coincidencia y la ruta de voz:

TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage

\----------------    ------------    ------------------    -------------

\+12065551219 descripti...    LocalRoute local

Debido a las limitaciones de la pantalla de Windows PowerShell, al menos parte de la información devuelta (más concretamente la descripción completa de la regla de normalización correspondiente) puede que no aparezca en la pantalla. Si solo le interesa el éxito o el fracaso de la prueba, esto podría no importarse. Si prefiere ver los detalles completos de los datos devueltos, canalice la salida al cmdlet Format-List al ejecutar la prueba:

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

Esto mostrará el resultado en un formato más sencillo para el lector:

TranslatedNumber: + 12065551219

MatchingRule: Description =; Pattern = ^ (\\d{11}) $; Traducción = + $1;

Name = prefix All; IsInternalExtension = false

FirsMatchingRoute: LocalRoute

MatchingUsage: local

Si se produce un error en la prueba, test-CsVoiceUser devolverá un conjunto vacío de valores de propiedad:

TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage

\---------------- ------------ ------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Existen varios motivos por los que el cmdlet test-CsVoiceUser puede fallar: puede que no haya una regla de normalización que pueda traducir el número de teléfono proporcionado. Puede haber problemas con la ruta de voz. Podría haber un problema de configuración con el plan de marcado asignado al usuario en cuestión. Por ello, es posible que desee incluir el parámetro verbose cuando ejecute el cmdlet test-CsVoiceUser:

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

Cuando se incluye el cmdlet verbose, test-CsVoiceUser emitirá una cuenta detallada de todos los pasos que se emprenderán en la realización de las comprobaciones. Por ejemplo, podría ver pasos similares a estos: 

VERBOse: buscando el usuario con la identidad "sip:kenmyer@litwareinc.com"

DETALLADO: cargando plan de marcado: "RedmondDialPlan"

Esta información adicional puede proporcionar sugerencias en cuanto a los pasos que puede realizar para identificar la causa del error. Por ejemplo, el resultado detallado que se muestra aquí nos dice que el usuario que se está probando se asignó al plan de marcado RedmondDialPlan. Si se ha producido un error en la prueba, un paso siguiente lógico sería comprobar que RedmondDialPlan puede traducir el número de teléfono proporcionado.

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

