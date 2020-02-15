---
title: 'Lync Server 2013: probar el plan de marcado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the dial plan
ms:assetid: 70eec03c-aca3-4106-86a7-77ae96b53779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690130(v=OCS.15)
ms:contentKeyID: 63969616
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c35d204a8a3fa16ff38dbcce89c0c8f36da2039
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-dial-plan-in-lync-server-2013"></a>Probar el plan de marcado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-06-05_


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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsDialPlan. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet test-CsDialPlan permite ver los resultados de la aplicación de un plan de marcado a un número de teléfono determinado. Los planes de marcado proporcionan información, como la forma en que se aplican las reglas de normalización, necesarias para permitir a los usuarios de Enterprise Voice realizar llamadas telefónicas. Después de especificar un número de marcado y un plan de marcado, el cmdlet verificará qué regla de normalización del plan de marcado se aplicará y cuál será el número traducido.

Puede usar este cmdlet para solucionar problemas con las traducciones de números o para comprobar cómo aplicar reglas a determinados números.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet test-CsDialPlan requiere que haga dos cosas. En primer lugar, debe obtener una instancia del plan de marcado que se está probando; Esto se puede hacer con el cmdlet Get-CsDialPlan. En segundo lugar, debe especificar el número de teléfono que se va a normalizar. El formato que se usa para el número de teléfono debe coincidir con el número marcado o escrito por un usuario. Por ejemplo, este comando recupera una instancia del plan de marcado, RedmondDialPlan, y comprueba si el número de teléfono 12065551219 se puede normalizar:

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

Si tiene una regla de normalización que agrega automáticamente el código de país (en este ejemplo, 1) y el código de área (206), es posible que desee comprobar el número de teléfono 5551219 de la siguiente manera:

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Test-CsDialPlan se diferencia de muchos de los cmdlets de prueba de Lync Server porque solo indica indirectamente si una prueba se ha realizado correctamente o no. Cuando se usa test-CsDialPlan, no se obtiene una salida similar a la siguiente con el resultado claramente marcado:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: correcto

Latencia: 00:00:06.8630376

Error

Diagnóstico

En su lugar, si test-CsDialPlan se realiza correctamente, recibirá información acerca de la regla de normalización que pudo traducir correctamente y usar el número de teléfono especificado:

TranslatedNumber: + 12065551219

MatchingRule: Description =; Pattern = ^ (\\d (11)) $; Traducción = + $1;

Name = prefix All; IsInternalExtension = false

Si test-CsDialPlan produce un error (es decir, si el plan de marcado no tiene una regla de normalización que pueda traducir el número de teléfono especificado), solo recibirá el resultado "vacío" de la siguiente manera:

TranslatedNumber :

MatchingRule :

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que test-CsDialPlan podría fallar:

  - Es posible que haya usado un formato incorrecto al especificar el número de teléfono. Los planes de marcado incluyen reglas de normalización que permiten que Lync Server traduzca los números de teléfono marcados o introducidos por un usuario. Por lo tanto, el plan de marcado debe tener reglas de normalización que coinciden con los números que los usuarios pueden marcar. Por ejemplo, si los usuarios pueden marcar el código de país, el código de área y, a continuación, el número de teléfono, significa que su plan de marcado debe tener una regla de normalización para controlar los números de teléfono como esta:
    
    12065551219
    
    Sin embargo, si escribe un número de teléfono incorrecto (por ejemplo, dejando fuera del dígito final), se producirá un error de test-CsDialPlan. No es porque el plan de marcado es defectuoso, pero ya ha escrito un número de teléfono que no se puede interpretar.

</div>

</div>

<span> </span>

</div>

</div>

</div>

