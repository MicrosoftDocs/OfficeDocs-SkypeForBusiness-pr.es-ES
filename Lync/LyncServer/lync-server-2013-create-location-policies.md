---
title: 'Lync Server 2013: crear directivas de ubicación'
description: 'Lync Server 2013: crear directivas de ubicación.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create location policies
ms:assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413006(v=OCS.15)
ms:contentKeyID: 48185794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 464ea9893890ab6185f180434e2dad13818123d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562266"
---
# <a name="create-location-policies-in-lync-server-2013"></a>Crear directivas de ubicación en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-11_

Lync Server usa una directiva de ubicación para habilitar clientes de Lync para E9-1-1 durante el registro de clientes. Una directiva de ubicación contiene la configuración que define cómo se implementará E9-1-1.

Puede editar la Directiva de ubicación global y crear nuevas directivas de ubicación con etiqueta. Un cliente obtiene una directiva global cuando no se encuentra en una subred con una directiva de ubicación asociada o cuando no se ha asignado directamente una directiva de ubicación al cliente. Las directivas etiquetadas se asignan a subredes o usuarios.

Para crear una directiva de ubicación, debe usar una cuenta que sea miembro del grupo RTCUniversalServerAdmins o que sea miembro del rol administrativo CsVoiceAdministrator o que tenga derechos y permisos de administrador equivalentes.

Para obtener una descripción completa de las directivas de ubicación, consulte [Defining The location Policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md). Los cmdlets de este procedimiento usan una directiva de ubicación definida con los siguientes valores:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Elemento</th>
<th>Valor</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnhancedEmergencyServicesEnabled</p></td>
<td><p><strong>True</strong></p></td>
</tr>
<tr class="even">
<td><p>LocationRequired</p></td>
<td><p><strong>Aviso de declinación de responsabilidades</strong></p></td>
</tr>
<tr class="odd">
<td><p>EnhancedEmergencyServiceDisclaimer</p></td>
<td><p>La Directiva de la empresa requiere que establezca una ubicación. Si no establece una ubicación, los servicios de emergencia no podrán localizarle en caso de emergencia. Establezca una ubicación.</p></td>
</tr>
<tr class="even">
<td><p>Uselocationfore911only era</p></td>
<td><p><strong>False</strong></p></td>
</tr>
<tr class="odd">
<td><p>PstnUsage</p></td>
<td><p><strong>EmergencyUsage</strong></p></td>
</tr>
<tr class="even">
<td><p>EmergencyDialString</p></td>
<td><p><strong>911</strong></p></td>
</tr>
<tr class="odd">
<td><p>EmergencyDialMask</p></td>
<td><p><strong>112</strong></p></td>
</tr>
<tr class="even">
<td><p>NotificationUri</p></td>
<td><p><strong>sip:security@litwareinc.com</strong></p></td>
</tr>
<tr class="odd">
<td><p>Uri</p></td>
<td><p><strong>sip:+14255550123@litwareinc.com</strong></p></td>
</tr>
<tr class="even">
<td><p>ConferenceMode</p></td>
<td><p><strong>TwoWay</strong></p></td>
</tr>
<tr class="odd">
<td><p>LocationRefreshInterval</p></td>
<td><p><strong>2</strong></p></td>
</tr>
</tbody>
</table>


Para obtener información detallada sobre cómo trabajar con directivas de ubicación, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:

  - New-CsLocationPolicy

  - Get-CsLocationPolicy

  - Set-CsLocationPolicy

  - Remove-CsLocationPolicy

  - Grant-CsLocationPolicy

<div>

## <a name="to-create-location-policies"></a>Para crear directivas de ubicación

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.
    
    <div>
    

    > [!NOTE]  
    > Se producirá un error en CsLocationPolicy si la configuración de <STRONG>PstnUsage</STRONG> no está ya en la lista global de PstnUsages.

    
    </div>

2.  Si lo desea, puede ejecutar el cmdlet siguiente para editar la Directiva de ubicación global:
    
        Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

3.  Ejecute lo siguiente para crear una directiva de ubicación con etiqueta.
    
        New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

4.  Ejecute el siguiente cmdlet para aplicar la Directiva de ubicación etiquetada creada en el paso 3 a una directiva de usuario.
    
        (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond

</div>

</div>

<span> </span>

</div>

</div>

</div>

