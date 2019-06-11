---
title: 'Lync Server 2013: probar el número de teléfono en una ruta de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed50971c9656d454a44eeee627de95c187ef008f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a>Probar el número de teléfono en una ruta de voz en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsVoiceRoute. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

Las rutas de voz funcionan conjuntamente con directivas de voz para ayudar a dirigir llamadas de voz empresariales a la red RTC. Cada ruta de voz incluye una expresión regular (un patrón de número) que identifica los números de teléfono que se redirigirán a través de una ruta de voz determinada: la ruta podrá controlar cualquier número de teléfono que coincida con esta expresión regular. Por ejemplo, una ruta de voz puede tener una expresión regular que le permite controlar cualquier número de 10 dígitos. Eso significa que la ruta podría controlar un número de teléfono como este:

  - 2065551219

La ruta no podría controlar ninguno de los dos números siguientes, ninguno de los cuales tiene 10 dígitos:

  - 5551219

  - 12065551219

El cmdlet test-CsVoiceRoute verifica si una ruta de voz determinada puede enrutar un número de teléfono especificado.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

Comprobar la capacidad de una ruta de voz para enrutar un número de teléfono especificado es un proceso de dos pasos. Primero tiene que usar el cmdlet Get-CsVoiceRoute para devolver una instancia de esa ruta de voz y, a continuación, debe usar el cmdlet test-CsVoiceRoute para comprobar la capacidad de esa ruta para controlar el número de teléfono de destino. Por ejemplo, este comando comprueba si la ruta de voz RedmondVoiceRoute puede enrutar el número de teléfono 2065551219:

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

Ten en cuenta que el número de teléfono debe escribirse tal como espera que los usuarios marquen ese número. Por ejemplo, si no espera que los usuarios incluyan el prefijo internacional y el código de área al marcar, entonces use una sintaxis similar a esta:

`-TargetNumber "5551219"`

En este caso, el número de destino deja el prefijo internacional y el código de área.

Para usar un solo comando para probar todas las rutas de voz con un número de destino especificado, use una sintaxis como la siguiente:

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

Para obtener más información, consulte la documentación de ayuda del cmdlet test-CsVoiceRoute.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si la ruta de voz puede enrutar el número de teléfono de destino, el cmdlet test-CsVoiceRoute solo devuelve el valor true:

MatchesPattern

\--------------

True

Eso significa que Route puede administrar números similares al número de destino. Si la ruta de voz no puede controlar el número de destino, test-CsVoiceRoute devolverá el valor falso:

MatchesPattern

\--------------

False

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Al probar las rutas de voz, "error" es un término relativo. En este caso, no significa que la ruta esté de alguna manera "dañada", sino que simplemente significa que la ruta no puede controlar el número de destino. Esto puede deberse a que la ruta de voz no se ha configurado correctamente. También podría significar que la ruta nunca estaba destinada a tratar números usando este patrón. Por ejemplo, si no deseas enrutar llamadas a otros países a través de una ruta determinada, la ruta podría estar configurada para rechazar todos los números de teléfono que incluyan un prefijo internacional. Si prueba-CsVoiceRoute devuelve falso cuando se espera que devuelva el valor verdadero, compruebe que escribió correctamente el número de destino. Si lo hizo, use un comando similar a este para ver la NumberPattern configurada para la ruta:

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a>Vea también


[Test-CsVoiceRoute](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

