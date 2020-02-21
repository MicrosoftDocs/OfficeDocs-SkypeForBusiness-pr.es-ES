---
title: 'Lync Server 2013: comprobar la configuración del tronco con un número de teléfono'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725206(v=OCS.15)
ms:contentKeyID: 63969574
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bf9d53d8702fbd9e63ec05af2c4942538f7298e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a>Comprobar la configuración del tronco con un número de teléfono en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsTrunkConfiguration. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

Los troncos SIP conectan la red de telefonía IP empresarial interna de Lync Server a cualquiera de los siguientes:

  - La red telefónica conmutada pública (RTC).

  - Una central de conmutación (PBX) de IP-Public.

  - Un controlador de borde de sesión (SBC).

El cmdlet test-CsTrunkConfiguration comprueba que un número de teléfono (como marcado por un usuario) se puede convertir a la red E. 164 y enrutarse a través de un tronco SIP especificado.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

Para ejecutar el cmdlet test-CsTrunkConfiguration, primero debe usar el cmdlet Get-CsTrunkConfiguration para recuperar una instancia de las opciones de configuración del tronco SIP; a continuación, esa instancia se canaliza a test-CsTrunkConfiguration:

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

Ejecutar test-CsTrunkConfiguration sin ejecutar primero Get-CsTrunkConfiguration no funcionará. Por ejemplo, se producirá un error en este comando sin que se devuelva ningún dato:

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

Si tiene varias colecciones de opciones de configuración de tronco SIP, puede usar un comando similar al siguiente para al mismo tiempo probar cada recopilación con el mismo número de teléfono:

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

Para obtener más información, consulte la documentación de ayuda del cmdlet test-CsTrunkConfiguration.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si test-CsTrunkConfiguration puede realizar una llamada al número marcado, el número de teléfono convertido (con el formato E. 164) y la regla utilizada para convertir ese número de teléfono se mostrarán en pantalla:

TranslatedNumber MatchingRule

\---------------- ------------

\+12065551219 global/Redmond

Si se produce un error en la prueba, test-CsTrunkConfiguration devolverá valores de propiedad vacía:

TranslatedNumber MatchingRule

\---------------- ------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Si test-CsTrunkConfiguration no devuelve una coincidencia que normalmente significa que los valores de configuración del tronco que se están comprobando no tienen una regla de conversión de números de llamadas salientes capaz de convertir el número marcado al formato E. 164. Para recuperar las reglas de conversión asignadas a una colección de opciones de configuración de tronco, puede usar una sintaxis similar a la siguiente:

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

Que devuelve información similar a la siguiente para cada regla de conversión:

Descripción: números de teléfono sin código de país ni código de área.

Patrón: ^\\+ (\\d\*) $

`Translation : $1`

Nombre: NoAreaCode

En ese momento, debe comprobar el valor de la propiedad Pattern (que es una cadena de [expresión regular](https://go.microsoft.com/fwlink/?linkid=400464) ) para ver si alguna de las reglas de conversión está configurada para controlar el número marcado. Si no es así, tendrá que cambiar una de las reglas existentes (Set-CsOutboundTranslationRule) o usar el cmdlet New-CsOutboundTranslationRule para agregar una nueva regla a la colección.

</div>

<div>

## <a name="see-also"></a>Consulta también


[Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

