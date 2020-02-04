---
title: 'Lync Server 2013: probar el enrutamiento de llamadas de teléfono RTC'
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
ms.openlocfilehash: 2dabe54fb2ba4df864d172015efb62ef161c77cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a>Probar el enrutamiento de llamadas de teléfono RTC en Lync Server 2013

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
<td><p>Programación de verificación</p></td>
<td><p>Cada día</p></td>
</tr>
<tr class="even">
<td><p>Herramienta de prueba</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permisos necesarios</p></td>
<td><p>Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</p>
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsInterTrunkRouting</strong> . Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet **Test-CsInterTrunkRouting** verifica que las llamadas se puedan enrutar desde un SIP a otro. Para ello, el cmdlet recibe un número de teléfono y una configuración de tronco. **Prueba-CsInterTrunkRouting** notificará las rutas de coincidencia y los usos de RTC que coincidan con el número especificado. Tenga en cuenta que las llamadas pueden enrutarse entre líneas troncales solo si estas líneas tienen un patrón de número que coincide con el número telefónico especificado y solo si las líneas troncales comparten por lo menos un uso de RTC.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

Los comandos que se muestran a continuación devuelven las rutas correspondientes y los usos de teléfono coincidentes que permiten a los usuarios llamar al número de teléfono 1-206-555-1219 con la configuración del tronco para el sitio de Redmond.

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si las llamadas se pueden desviar de un SIP a otro, recibirás un resultado similar a este:

FirstMatchingRoute MatchingUsage MatchingRoutes

\------------------ ------------- --------------

RedmondRoute LocalUsage {RedmondRoute}

Si la prueba no se completó correctamente, recibirá un resultado similar a este:

Prueba-CsInterTrunkRouting: no se puede procesar la transformación de argumentos en el parámetro

'TrunkConfiguration'. TrunkConfigurationsetting (parámetro) no válido. Especificar un

configuración válida (parámetro) y, a continuación, inténtalo de nuevo.

En la línea: 1 carácter: 79

\+Prueba-CsInterTrunkRouting-TargetNumber "Tel: + 12065551219"

\-TrunkConfiguration $t...

\+

~~

\+CategoryInfo: InvalidData: (:) \[Prueba-CsInterTrunkRouting\], par

ameterBindingArgumentTransformationException

\+FullyQualifiedErrorId: ParameterArgumentTransformationError, Microsoft. R

CT. Management. Voice. cmdlets. TestOcsInterTrunkRoutingCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que **Test-CsInterTrunkRouting** podría fallar:

  - Ha especificado parámetros no válidos. Es posible que el tronco no esté configurado correctamente y que el número de destino especificado sea incorrecto o no válido.

</div>

<div>

## <a name="see-also"></a>Vea también


[Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

