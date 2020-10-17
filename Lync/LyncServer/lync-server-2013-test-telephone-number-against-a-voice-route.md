---
title: 'Lync Server 2013: probar el número de teléfono con una ruta de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e2db63b7f8c4d801c7e2e89da93593a5745c9c6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519127"
---
# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a>Probar el número de teléfono con una ruta de voz en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsVoiceRoute. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

Las rutas de voz funcionan junto con las directivas de voz para ayudar a enrutar las llamadas de telefonía IP empresarial a la red RTC. Cada ruta de voz incluye una expresión regular (un patrón de número) que identifica los números de teléfono que se redirigirán a través de una ruta de voz determinada: la ruta podrá controlar los números de teléfono que coinciden con esta expresión regular. Por ejemplo, una ruta de voz puede tener una expresión regular que permite controlar cualquier número de 10 dígitos. Eso significa que la ruta podría administrar un número de teléfono como el siguiente:

  - 2065551219

La ruta no podría controlar ninguno de los dos números siguientes, ninguno de los cuales tiene 10 dígitos:

  - 5551219

  - 12065551219

El cmdlet Test-CsVoiceRoute comprueba si una ruta de voz determinada puede enrutar un número de teléfono especificado.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

Comprobar que la capacidad de una ruta de voz para enrutar un número de teléfono especificado es un proceso de dos pasos. Primero tiene que usar el cmdlet Get-CsVoiceRoute para devolver una instancia de esa ruta de voz y, a continuación, debe usar el cmdlet Test-CsVoiceRoute para comprobar la capacidad de esa ruta para controlar el número de teléfono de destino. Por ejemplo, este comando comprueba si la ruta de voz RedmondVoiceRoute puede enrutar el número de teléfono 2065551219:

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

Tenga en cuenta que el número de teléfono debe escribirse tal como espera que los usuarios marquen ese número. Por ejemplo, si no espera que los usuarios incluyan el código de país y el código de área al marcar, use una sintaxis similar a la siguiente:

`-TargetNumber "5551219"`

En este caso, el número de destino deja el código de país y el código de área.

Para usar un único comando para probar todas las rutas de voz con un número de destino especificado, use una sintaxis como la siguiente:

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

Para obtener más información, consulte la documentación de ayuda del cmdlet Test-CsVoiceRoute.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si la ruta de voz puede enrutar el número de teléfono de destino, el cmdlet Test-CsVoiceRoute solo devuelve el valor true:

MatchesPattern

\--------------

Verdadero

Esto significa que Route puede controlar números similares al número de destino. Si la ruta de voz no puede controlar el número de destino, Test-CsVoiceRoute devuelve el valor false:

MatchesPattern

\--------------

False

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Al probar rutas de voz, "error" es un término relativo. En este caso, no significa que la ruta se "rompe" de algún modo, sino simplemente que la ruta no puede controlar el número de destino. Esto puede deberse a que la ruta de voz no se ha configurado correctamente. También podría significar que la ruta nunca se diseñó para controlar números con este patrón. Por ejemplo, si no desea enrutar las llamadas a otros países a través de una ruta determinada, es posible que la ruta esté configurada para rechazar todos los números de teléfono que incluyan un código de país. Si Test-CsVoiceRoute devuelve false cuando esperaba que devolvera el valor true, compruebe que escribió el número de destino correctamente. Si lo hizo, use un comando similar al siguiente para ver la NumberPattern configurada para la ruta:

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a>Consulte también


[Test-CsVoiceRoute](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

