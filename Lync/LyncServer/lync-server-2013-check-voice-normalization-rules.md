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
ms.openlocfilehash: 1cf48022fc62f959bbddcd3cb6978e2e668a9334
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsVoiceNormalizationRule. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

Las reglas de normalización de voz se usan para convertir un número de teléfono marcado por un usuario (por ejemplo, 2065551219) al formato E. 164 que usa Lync Server (+ 12065551219). Por ejemplo, si los usuarios tienen la costumbre de marcar un número de teléfono sin incluir el código de país o el código de área (por ejemplo, 5551219), debe tener una regla de normalización de voz que pueda convertir ese número al formato E. 164: + 12065551219. Sin dicha regla, el usuario no podrá llamar a 555-1219.

El cmdlet test-CsVoiceNormalizationRule comprueba que una regla de normalización de voz especificada puede convertir correctamente un número de teléfono especificado. Por ejemplo, este comando comprueba si la regla de normalización global NoAreaCode puede normalizar y convertir la cadena de marcado 5551219.

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

Para ejecutar el cmdlet test-CsVoiceNormalizationRule, primero debe usar el cmdlet Get-CsVoiceNormalizationRule para recuperar una instancia de la regla que se está probando y, a continuación, canalizar esa instancia para probar la CsVoiceNormalizationRule. Una sintaxis similar a esta no funcionará:

Test-CsVoiceNormalizationRule-DialedNumber "12065551219" – NormalizationRule "global/prefix All"

En su lugar, use una sintaxis como la siguiente, que combina los cmdlets Get-CsVoiceNormalizationRule y test-CsVoiceNormalizationRule:

Get-CsVoiceNormalizationRule-Identity "global/prefix All" | Test-CsVoiceNormalizationRule-DialedNumber "12065551219"

<div>


> [!NOTE]  
> . También puede usar este método para recuperar una instancia de una regla y, a continuación, probar dicha regla con un número de teléfono especificado:



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

Escriba el valor del parámetro DialedNumber exactamente como esperaba que se marque como un número. Por ejemplo, si se supone que la regla de normalización de voz especificada agrega automáticamente el código de país (el 1 inicial en el valor 12065551219), debe omitir el código de país:

`-DialedNumber "2065551219"`

Si la regla está correctamente configurada, se agregará automáticamente el código de país al traducir el número al formato E. 164 que usa Lync Server.

Para obtener más información, consulte la documentación de ayuda del cmdlet test-CsVoiceNormalizationRule.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si la regla de normalización de voz especificada puede traducir el número proporcionado, el número traducido se mostrará en pantalla:

TranslatedNumber

\----------------

\+12065551219

Si se produce un error en la prueba, se devolverá un número traducido en blanco:

TranslatedNumber

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Si el test-CsVoiceNormalizationRule devuelve un número convertido que significa que la regla de normalización de voz especificada no ha podido traducir el número de teléfono proporcionado en el formato E. 164 que usa Lync Server. Para comprobar que, primero debe asegurarse de que escribió el número de teléfono correctamente. Por ejemplo, esperaría que la regla de normalización de voz tenga problemas para traducir un número similar al siguiente:

`-DialedNumber "1"`

Si se ha escrito el número correctamente, el siguiente paso debe ser comprobar que la regla de normalización especificada está diseñada para controlar ese número de teléfono. Por ejemplo, una regla de normalización puede estar diseñada para controlar el formato 12065551219, pero una segunda regla puede estar diseñada para controlar el número 2065551219. (Es decir, el mismo número de teléfono, menos el código de país 1 en el principio). Para obtener información detallada sobre una regla de normalización de voz, ejecute un comando similar a este:

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

Para obtener información detallada sobre todas las reglas de normalización de voz, ejecute este comando en su lugar:

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

