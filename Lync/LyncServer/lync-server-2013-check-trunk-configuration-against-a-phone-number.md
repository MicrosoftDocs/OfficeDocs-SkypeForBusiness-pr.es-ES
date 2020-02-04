---
title: 'Lync Server 2013: comprobar la configuración troncal con un número de teléfono'
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
ms.openlocfilehash: 7932e4cb7a7a9d74b945dcd60c2a1211ca5af694
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a>Comprobar la configuración troncal de un número de teléfono en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsTrunkConfiguration. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

Los troncos SIP conectan la red empresarial de Lync Server interna a cualquiera de las siguientes opciones:

  - La red de telefonía pública conmutada (RTC).

  - Un intercambio de sucursales (PBX) IP-Public.

  - Un controlador de borde de sesión (SBC).

El cmdlet test-CsTrunkConfiguration verifica que un número de teléfono (como marcados por un usuario) pueda convertirse a la red E. 164 y se enrute a través de un tronco SIP especificado.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

Para ejecutar el cmdlet test-CsTrunkConfiguration, primero debe usar el cmdlet Get-CsTrunkConfiguration para recuperar una instancia de su configuración de troncal de SIP; a continuación, esa instancia se canaliza a test-CsTrunkConfiguration:

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

La ejecución de test-CsTrunkConfiguration sin ejecutar First-CsTrunkConfiguration no funcionará. Por ejemplo, este comando producirá un error sin devolver ningún dato:

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

Si tiene varias colecciones de parámetros de configuración del tronco del SIP, puede usar un comando similar al siguiente para al mismo tiempo probar cada recopilación con el mismo número de teléfono:

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

Para obtener más información, consulte la documentación de ayuda del cmdlet test-CsTrunkConfiguration.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si prueba-CsTrunkConfiguration puede realizar una llamada al número marcado, el número de teléfono traducido (con el formato E. 164) y la regla usada para traducir ese número de teléfono se mostrarán en pantalla:

TranslatedNumber MatchingRule

\---------------- ------------

\+12065551219 global/Redmond

Si la prueba no se realiza correctamente, test-CsTrunkConfiguration devolverá valores de propiedad vacíos:

TranslatedNumber MatchingRule

\---------------- ------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Si prueba-CsTrunkConfiguration no devuelve una coincidencia que normalmente significa que los ajustes de configuración del tronco que se están probando no tienen una regla de traducción del número de llamadas salientes capaz de convertir el número marcado al formato E. 164. Para recuperar las reglas de traducción asignadas a una colección de valores de configuración del tronco, puede usar una sintaxis similar a la siguiente:

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

Que devuelva información similar a la siguiente para cada regla de traducción:

Descripción: números de teléfono sin un código de país o un código de área.

Patrón: ^\\+ (\\d\*) $

`Translation : $1`

Nombre: NoAreaCode

En ese momento, debe comprobar el valor de la propiedad Pattern (que es una cadena de [expresión regular](http://go.microsoft.com/fwlink/?linkid=400464) ) para ver si alguna de las reglas de traducción está configurada para controlar el número marcado. En caso contrario, tendrá que cambiar una de las reglas existentes (Set-CsOutboundTranslationRule) o usar el cmdlet New-CsOutboundTranslationRule para agregar una nueva regla a la colección.

</div>

<div>

## <a name="see-also"></a>Vea también


[Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

