---
title: 'Lync Server 2013: probar el enrutamiento de llamadas de teléfono RTC'
description: 'Lync Server 2013: probar el enrutamiento de llamadas de teléfono RTC.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call routing
ms:assetid: 301dd44d-03e9-41cd-9722-54e00365aa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727302(v=OCS.15)
ms:contentKeyID: 63969598
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da931b43176932a9b6781fa27318e83e6994548c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556276"
---
# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a>Probar el enrutamiento de llamadas de teléfono RTC en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-11-01_


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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsInterTrunkRouting</strong> . Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet **Test-CsInterTrunkRouting** comprueba que las llamadas se pueden enrutar desde un SIP a otro. Para ello, el cmdlet recibe un número de teléfono y una configuración de tronco. **Test-CsInterTrunkRouting** , a continuación, notificará las rutas de coincidencia y los usos de RTC coincidentes para el número especificado. Tenga en cuenta que las llamadas pueden enrutarse entre líneas troncales solo si estas líneas tienen un patrón de número que coincide con el número telefónico especificado y solo si las líneas troncales comparten por lo menos un uso de RTC.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

Los comandos que se muestran a continuación devuelven las rutas de coincidencia y los usos de teléfono coincidentes que permiten a los usuarios llamar al número de teléfono 1-206-555-1219 con los valores de configuración del tronco para el sitio de Redmond.

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si las llamadas se pueden enrutar desde un SIP a otro, recibirá un resultado similar al siguiente:

FirstMatchingRoute MatchingUsage MatchingRoutes

\------------------ ------------- --------------

RedmondRoute LocalUsage {RedmondRoute}

Si la prueba no se realizó correctamente, recibirá un resultado similar al siguiente:

Test-CsInterTrunkRouting: no se puede procesar la transformación de argumentos en el parámetro

"TrunkConfiguration". TrunkConfigurationsetting (parámetro) no válido. Especificar un

valor válido (parámetro) y, a continuación, vuelva a intentarlo.

En la línea: 1 carácter: 79

\+ Test-CsInterTrunkRouting-TargetNumber "Tel: + 12065551219"

\-TrunkConfiguration $t...

\+

~~

\+ CategoryInfo: InvalidData: (:) \[ Test-CsInterTrunkRouting \] , par

ameterBindingArgumentTransformationException

\+ FullyQualifiedErrorId: ParameterArgumentTransformationError, Microsoft. R

The. Management. Voice. cmdlets. TestOcsInterTrunkRoutingCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que **Test-CsInterTrunkRouting** podría fallar:

  - Ha especificado parámetros no válidos. Es posible que el tronco no se haya configurado correctamente y que el número de destino especificado sea incorrecto o no sea válido.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

