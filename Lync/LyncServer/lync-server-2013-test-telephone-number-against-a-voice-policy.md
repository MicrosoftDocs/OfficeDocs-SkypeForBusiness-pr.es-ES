---
title: 'Lync Server 2013: probar el número de teléfono con una directiva de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice policy
ms:assetid: 30c51700-17c6-4c57-891a-8d5ec30b50ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725207(v=OCS.15)
ms:contentKeyID: 63969596
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d22c801c7d08c3df663f69df07a6c73a5f17f858
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a>Probar el número de teléfono con una directiva de voz en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsVoicePolicy. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

La capacidad de los usuarios de Enterprise Voice de realizar llamadas salientes telefónicas a través de las bisagras de la red telefónica conmutada (RTC) en gran parte, en tres cosas:

  - La Directiva de voz asignada al usuario.

  - Rutas de voz usadas para enrutar las llamadas de Lync Server a la red RTC.

  - Uso de RTC, una propiedad de Lync Server que conecta una directiva de voz a una ruta de voz.

El uso de RTC es especialmente importante: es la propiedad que conecta una directiva de voz a una ruta de voz. (Se dice que una directiva de voz y una ruta de voz están conectadas si tienen como mínimo un uso de RTC en común). Las directivas de voz se pueden configurar sin especificar un uso de RTC. En ese caso, los usuarios a los que se les asignó esta Directiva no podrán realizar llamadas salientes a través de la red RTC. Del mismo modo, las rutas de voz que no tienen al menos un uso de RTC especificado no podrán enrutar las llamadas a la red RTC.

El cmdlet test-CsVoicePolicy comprueba que una directiva de voz determinada tiene un uso de RTC y que el uso se comparte con al menos una ruta de voz. Si la comprobación ejecutada por test-CsVoicePolicy se realiza correctamente, el cmdlet devolverá el nombre de la primera ruta de voz válida que encuentre y también el nombre del uso de RTC que conecta la Directiva a la ruta.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

Para ejecutar el cmdlet test-CsVoicePolicy, primero debe usar el cmdlet Get-CsVoicePolicy para recuperar una instancia de la Directiva de voz que se va a probar; a continuación, esa instancia se debe canalizar a test-CsVoicePolicy. Por ejemplo:

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

Tenga en cuenta que este comando, que no usa Get-CsVoicePolicy para recuperar una instancia de la Directiva de voz, producirá un error:

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

Si desea comprobar todas las directivas de voz en un número de teléfono especificado, use un comando similar al siguiente:

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

Tenga en cuenta que el TargetNumber debe especificarse con el formato E. 164. Test-CsVoicePolicy no intentará normalizar ni traducir los números de teléfono al formato E. 164.

Para obtener más información, consulte la documentación de ayuda del cmdlet test-CsVoicePolicy.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si la Directiva de voz puede encontrar tanto una ruta de voz coincidentes como un uso de RTC que coincida, se mostrarán en pantalla tanto la ruta como el uso:

FirstMatchingRoute MatchingUsage

\------------------ -------------

RedmondVoiceRoute RedmondPstnUsage

Si no se puede encontrar una ruta de voz adecuada o un uso de RTC adecuado, los valores de la propiedad en blanco se mostrarán en la pantalla:

FirstMatchingRoute MatchingUsage

\------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Si test-CsVoicePolicy no devuelve una coincidencia, puede significar que la Directiva de voz no comparte el uso de RTC con una ruta de voz. Para comprobar que, use un cmdlet similar al siguiente para comprobar que los usos de RTC asignados a la Directiva de voz:

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

A continuación, ejecute este comando para determinar los usos de RTC que se asignan a cada una de las rutas de voz:

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

Si ve alguna coincidencia (es decir, si ve una o varias rutas de voz que comparten al menos un uso de RTC con la Directiva de voz), debe ejecutar el cmdlet test-CsVoiceRoute para comprobar que la ruta de voz puede marcar el número de teléfono proporcionado.

</div>

<div>

## <a name="see-also"></a>Consulta también


[Test-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

