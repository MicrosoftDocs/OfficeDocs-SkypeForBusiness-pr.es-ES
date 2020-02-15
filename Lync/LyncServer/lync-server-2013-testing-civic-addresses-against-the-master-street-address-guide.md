---
title: Prueba de direcciones cívicas con la guía de dirección principal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing civic addresses against the master street address guide
ms:assetid: dc680de9-2a0f-4fd3-a99e-9bab0bc30ae5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690132(v=OCS.15)
ms:contentKeyID: 63969657
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a55593bee333d03c71522bdd0a39cc91cb60882
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a>Comprobación de direcciones cívicas con la guía de dirección de Master Street en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsRegistration. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet test-CsLisCivicAddress se usa para comprobar las ubicaciones que se agregaron a la base de datos del servicio de información de ubicaciones (LIS). El cmdlet de funciona comparando las ubicaciones con las ubicaciones que se encuentran en la guía de direcciones maestras (MSAG) que pertenece a su proveedor de enrutamiento de red E9-1-1. Si no tiene un proveedor de enrutamiento de red o si no se puede obtener acceso al proveedor, se producirá un error en las pruebas.

Si agrega el parámetro switch opcional UpdateValidationStatus a su comando, la propiedad de base de datos MSAGValid correspondiente se establecerá en true para cada dirección que pase la prueba.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet test-CsLisCivicAddress se puede usar para probar direcciones individuales o para probar varias direcciones. Por ejemplo, este comando comprueba una única dirección que se encuentra en Redmond, WA:

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

Por comparación, este comando comprueba todas las direcciones que se encuentran actualmente en la base de datos de LIS:

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Test-CsLisCivicAddress informará de que se ha realizado correctamente o no un error en las direcciones suministradas. Se producirá un error en una prueba de dirección si no se encuentra la dirección o si no se puede establecer contacto con el proveedor de servicios.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que test-CsLisCivicAddress podría fallar:

  - Es posible que el proveedor de servicios LIS no esté disponible. Para recuperar la dirección URL de su proveedor de servicios de LIS, ejecute el cmdlet Get-CsLisConfiguration:
    
        Get-CsLisConfiguration 
    
    A continuación, puede hacer ping a esa dirección URL para comprobar que el proveedor de servicios está disponible.

</div>

</div>

<span> </span>

</div>

</div>

</div>

