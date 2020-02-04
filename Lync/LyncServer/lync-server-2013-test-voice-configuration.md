---
title: 'Lync Server 2013: configuración de voz de prueba'
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
ms.openlocfilehash: 9532327640be12351143632813d403edddf5c437
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsVoiceTestConfiguration. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

Lync Server incluye varios cmdlets de Windows PowerShell (como test-CsVoiceRoute y test-CsVoicePolicy, test-CsTrunkConfiguration) que le permiten comprobar que las partes individuales de su infraestructura de voz empresarial (rutas de voz, voz) las políticas, los troncos SIP funcionan de la forma esperada.

Aunque es importante con la telefonía IP empresarial que funcionan todas las piezas individuales: es posible tener una ruta de voz válida, una política de voz válida y un tronco de SIP válido, pero seguir teniendo usuarios que no pueden hacer ni recibir llamadas telefónicas. Por eso, Lync Server también ofrece la capacidad de crear configuraciones de prueba de voz. Las configuraciones de prueba de voz representan escenarios comunes de Enterprise Voice: puede especificar cosas como una ruta de voz, una directiva de voz y un plan de marcado, y comprobar que esos elementos individuales funcionan conjuntamente para proporcionar servicio telefónico. Además, puede validar sus expectativas en un escenario determinado. Por ejemplo, supongamos que espera que la combinación del plan de marcado A y la Directiva de voz B dé lugar a que las llamadas se enruten a través de la ruta de voz C. Puede escribir la ruta de voz C como la ExpectedRoute. Al ejecutar la prueba, si no se utiliza la ruta de voz C, la prueba se marcará como con error.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

Antes de probar las colecciones de configuración de voz con Windows PowerShell, primero debe usar el cmdlet Get-CsVoiceTestConfiguration para recuperar una instancia de estas opciones de configuración. A continuación, esa instancia se debe canalizar a la prueba-CsVoiceTestConfiguration. Por ejemplo:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

Para validar todas las opciones de configuración de prueba de voz al mismo tiempo, use este comando:

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

Para obtener más información, consulte la documentación de ayuda del cmdlet test-CsVoiceTestConfiguration.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

El cmdlet test-CsVoiceTestConfiguration informa de si una prueba ha sido correcta o incorrecta, y proporciona información adicional sobre las pruebas correctas, como la regla de traducción, la ruta de voz y el uso de RTC que se usan para completar la tarea:

Resultado: éxito

TranslatedNumber: + 15551234

MatchingRule: Descripción =; Patrón = ^ (\\d{4}) $; Traducción = + 1\\d; Nombre = prueba; IsInternalExtension = falso

FirstMatchingRoute: sitio: Redmond

MatchingUsage: local

Si se produce un error en la prueba, el resultado se notifica como error:

Resultado: error

TranslatedNumber:   

FirstMatchingRoute:

MatchingUsage:      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Puesto que la prueba de la configuración de prueba de voz prueba varios elementos diferentes, como directivas de voz, planes de marcado, rutas de voz, etc., hay varios factores diferentes que podrían dar lugar a una prueba fallida. Si se produce un error en una prueba, el primer paso debe ser revisar las opciones de configuración mediante el cmdlet Get-CsVoiceTestConfiguration:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

Si la configuración parece estar configurada correctamente, vuelva a ejecutar la prueba al incluir el parámetro detallado:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

El parámetro verbose proporcionará una cuenta paso a paso de cada acción realizada por test-CsVoiceTestConfiguration como se muestra en este ejemplo:

DETALLADO: cargando plan de marcado: "global"

DETALLADO: cargando Directiva de voz: "RedmondDialPlan"

Esta cuenta paso a paso podría proporcionar una pista útil de dónde se produjo el error en la prueba. En caso contrario, puede usar otros cmdlets de Windows PowerShell (como test-CsVoicePolicy) y empezar a comprobar los componentes individuales que se incluyen en la configuración de la prueba de voz.

Además, tenga en cuenta que es posible que una prueba pueda enrutar una llamada y que aún se marque como una falla; Esto puede ocurrir si escribe valores para ExpectedRoute, ExpectedTranslatedNumber y ExpectedUsage, y no se cumplen estas expectativas. Por ejemplo, supongamos que escribe la ruta de voz C como la ruta de voz esperada, pero la prueba realmente completa la llamada usando la ruta de voz D. En ese caso, la prueba se marcará como fallida porque la ruta de voz esperada no se usó. Si se produce un error en una prueba, puede quitar los valores de ExpectedRoute, ExpectedTranslatedNumber y ExpectedUsage y, a continuación, volver a ejecutar la prueba. Esto le ayudará a determinar si el error se debe a que la llamada no se ha completado o a que se espera una cosa y que realmente se ha recibido de otra.

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

