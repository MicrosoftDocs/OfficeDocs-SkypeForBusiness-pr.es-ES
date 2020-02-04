---
title: 'Lync Server 2013: comprobar las reglas de normalización de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check voice normalization rules
ms:assetid: bf71a218-71cd-4b64-b8e8-b3a98b6e87a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725212(v=OCS.15)
ms:contentKeyID: 63969649
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04e383f38d5af6f106354a766c857635bcd87eb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733870"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-voice-normalization-rules-in-lync-server-2013"></a>Comprobar las reglas de normalización de voz en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsVoiceNormalizationRule. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

Las reglas de normalización de voz se usan para convertir un número de teléfono marcado por un usuario (por ejemplo, 2065551219) al formato E. 164 que usa Lync Server (+ 12065551219). Por ejemplo, si los usuarios tienen el hábito de marcar un número de teléfono sin incluir el prefijo internacional o el código de área (por ejemplo, 5551219), debe tener una regla de normalización de voz que pueda convertir ese número al formato E. 164: + 12065551219. Sin dicha regla, el usuario no podrá llamar al 555-1219.

El cmdlet test-CsVoiceNormalizationRule comprueba que una regla de normalización de voz especificada puede convertir correctamente un número de teléfono especificado. Por ejemplo, este comando comprueba si la regla de normalización NoAreaCode puede normalizar y convertir la cadena de marcado 5551219.

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

Para ejecutar el cmdlet test-CsVoiceNormalizationRule, primero debe usar el cmdlet Get-CsVoiceNormalizationRule para recuperar una instancia de la regla que se está probando y, a continuación, canalizar esa instancia para probar-CsVoiceNormalizationRule. La sintaxis es similar a esta:

Test-CsVoiceNormalizationRule-DialedNumber "12065551219"-NormalizationRule "global/prefix All"

En su lugar, use una sintaxis como la siguiente, que combina los cmdlets Get-CsVoiceNormalizationRule y test-CsVoiceNormalizationRule:

Get-CsVoiceNormalizationRule-Identity "global/prefix All" | Prueba-CsVoiceNormalizationRule-DialedNumber "12065551219"

<div>


> [!NOTE]  
> . También puede usar este método para recuperar una instancia de una regla y, a continuación, probarla con un número de teléfono especificado:



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

Escriba el valor del parámetro DialedNumber exactamente como espera que se marque ese número. Por ejemplo, si se supone que la regla de normalización de voz especificada agrega automáticamente el prefijo internacional (el 1 en el valor 12065551219), debe omitir el prefijo internacional:

`-DialedNumber "2065551219"`

Si la regla está configurada correctamente, se agregará automáticamente el prefijo internacional al traducir el número al formato E. 164 usado por Lync Server.

Para obtener más información, consulte la documentación de ayuda del cmdlet test-CsVoiceNormalizationRule.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si la regla de normalización de voz especificada puede traducir el número suministrado, el número traducido se mostrará en pantalla:

TranslatedNumber

\----------------

\+12065551219

Si se produce un error en la prueba, se devolverá un número traducido en blanco:

TranslatedNumber

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Si la prueba-CsVoiceNormalizationRule devuelve un número traducido que significa que la regla de normalización de voz especificada no pudo traducir el número de teléfono suministrado al formato E. 164 usado por Lync Server. Para verificar que, primero, asegúrate de escribir el número de teléfono correctamente. Por ejemplo, esperamos que su regla de normalización de voz tenga problemas para traducir un número parecido a este:

`-DialedNumber "1"`

Suponiendo que el número se haya introducido correctamente, el siguiente paso debe comprobar que la regla de normalización especificada está diseñada para controlar ese número de teléfono. Por ejemplo, una regla de normalización podría estar diseñada para controlar el formato 12065551219, pero una segunda regla podría estar diseñada para controlar el número 2065551219. (Es decir, el mismo número de teléfono, menos el prefijo internacional 1 al principio). Para obtener información detallada sobre una regla de normalización de voz, ejecute un comando similar a este:

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

Para obtener información detallada sobre todas las reglas de normalización de voz, ejecute este comando:

`Get-CsVoiceNormalizationRule | Format-List`

</div>

<div>

## <a name="see-also"></a>Vea también


[Test-CsVoiceNormalizationRule](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceNormalizationRule)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

