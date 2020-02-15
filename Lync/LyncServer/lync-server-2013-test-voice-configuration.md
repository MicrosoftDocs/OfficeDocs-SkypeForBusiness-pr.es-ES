---
title: 'Lync Server 2013: probar la configuración de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2894d61a4dabd174315e24a225392bde7a893300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-configuration-in-lync-server-2013"></a>Probar la configuración de voz en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsVoiceTestConfiguration. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

Lync Server incluye varios cmdlets de Windows PowerShell (como test-CsVoiceRoute y test-CsVoicePolicy, test-CsTrunkConfiguration) que le permiten comprobar que las partes individuales de su infraestructura de telefonía IP empresarial (rutas de voz, voz) directivas, troncos SIP: funcionan según lo previsto.

Aunque es importante con telefonía IP empresarial que funcionan todas las piezas individuales: es posible tener una ruta de voz válida, una directiva de voz válida y un tronco SIP válido, pero seguir haciendo que los usuarios no puedan realizar o recibir llamadas telefónicas. Por eso, Lync Server también ofrece la posibilidad de crear configuraciones de prueba de voz. Las configuraciones de prueba de voz representan escenarios comunes de Enterprise Voice: puede especificar aspectos como una ruta de voz, una directiva de voz y un plan de marcado y, a continuación, comprobar que esos elementos individuales funcionan conjuntamente para proporcionar el servicio telefónico. Además, puede validar sus expectativas en un escenario determinado. Por ejemplo, supongamos que espera que la combinación de plan de marcado A y Directiva de voz B dé como resultado que las llamadas se enruten a través de la ruta de voz C. Puede escribir la ruta de voz C como ExpectedRoute. Cuando se ejecuta la prueba, si no se usa la ruta de voz C, la prueba se marcará como con error.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

Antes de probar las colecciones de configuración de voz con Windows PowerShell, primero debe usar el cmdlet Get-CsVoiceTestConfiguration para recuperar una instancia de estas opciones de configuración. A continuación, esa instancia se debe canalizar a test-CsVoiceTestConfiguration. Por ejemplo:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

Para validar todas las opciones de configuración de prueba de voz al mismo tiempo, use este comando en su lugar:

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

Para obtener más información, consulte la documentación de ayuda del cmdlet test-CsVoiceTestConfiguration.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

El cmdlet test-CsVoiceTestConfiguration informa si una prueba ha tenido éxito o no se ha realizado correctamente y proporciona información adicional acerca de cada una de las pruebas, como la regla de conversión, la ruta de voz y el uso de RTC que se usan para completar la tarea:

Resultado: correcto

TranslatedNumber: + 15551234

MatchingRule: Description =; Pattern = ^ (\\d{4}) $; Traducción = + 1\\d; Name = test; IsInternalExtension = false

FirstMatchingRoute: sitio: Redmond

MatchingUsage: local

Si se produce un error en la prueba, se notifica que el resultado es incorrecto:

Resultado: error

TranslatedNumber:   

FirstMatchingRoute:

MatchingUsage:      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Debido a que la prueba de la configuración de prueba de voz prueba varios elementos diferentes, como directivas de voz, planes de marcado, rutas de voz, etc., hay varios factores diferentes que podrían dar como resultado una prueba con errores. Si se produce un error en una prueba, el primer paso debe ser revisar las opciones de configuración mediante el cmdlet Get-CsVoiceTestConfiguration:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

Si la configuración parece estar correctamente configurada, vuelva a ejecutar la prueba al incluir el parámetro verbose:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

El parámetro verbose proporcionará una cuenta paso a paso de cada acción que test-CsVoiceTestConfiguration toma como se muestra en este ejemplo:

VERBOse: cargando plan de marcado: "global"

VERBOse: cargando Directiva de voz: "RedmondDialPlan"

Esta cuenta paso a paso puede proporcionar una pista útil sobre dónde se produjo el error en la prueba. Si no es así, puede usar otros cmdlets de Windows PowerShell (como test-CsVoicePolicy) y empezar a comprobar los componentes individuales que se incluyen en las opciones de configuración de la prueba de voz.

Además, tenga en cuenta que es posible que una prueba pueda enrutar una llamada y que todavía se marque como un error; Esto puede ocurrir si escribe valores para ExpectedRoute, ExpectedTranslatedNumber y ExpectedUsage, y no se cumple alguna de estas expectativas. Por ejemplo, supongamos que escribe ruta de voz C como la ruta de voz esperada, pero la prueba completa realmente la llamada usando la ruta de voz D. En ese caso, la prueba se marcará como fallida porque no se usó la ruta de voz esperada. Si se produce un error en una prueba, puede quitar los valores de ExpectedRoute, ExpectedTranslatedNumber y ExpectedUsage y, a continuación, volver a ejecutar la prueba. Esto le ayudará a determinar si el error se debe a que la llamada no se ha podido completar o porque se espera una cosa y se recibe realmente otra.

</div>

<div>

## <a name="see-also"></a>Vea también


[Test-CsVoiceTestConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

