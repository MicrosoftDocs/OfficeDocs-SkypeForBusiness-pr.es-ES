---
title: 'Lync Server 2013: configuración de la página para unirse a la reunión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting join page
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204861(v=OCS.15)
ms:contentKeyID: 48184037
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 977903d8d85b3eaa4d944e8b3e62ec0df629c1d0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a>Configuración de la página de participación en la reunión en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-12-14_

Cuando un usuario hace clic en un vínculo de reunión en una convocatoria de reunión, la página de participación en la reunión detecta si un cliente de Lync 2013 ya está instalado en el equipo del usuario. Si hay uno instalado, el cliente se abre y se une a la reunión. Si un cliente no está instalado, se abre de forma predeterminada la versión 2013 de Lync Web App.

Puede modificar el comportamiento de la página de participación en la reunión si desea permitir que los usuarios se unan a reuniones con Office Communicator 2007 R2 o el operador de Lync 2010. Estas opciones de configuración se han quitado del panel de control de Lync Server 2013, pero puede configurarlas mediante el cmdlet Set-CsWebServiceConfiguration.

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a>Parámetros de Set-CsWebServiceConfiguration de la página para unirse a la reunión

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Parámetro Set-CsWebServiceConfiguration</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Showjoinusinglegacyclientlink establecidos</p></td>
<td><p>Si se establece en true, los usuarios que se unan a una reunión con una aplicación cliente distinta de Lync tendrán la oportunidad de unirse a la reunión mediante Office Communicator 2007 R2. El valor predeterminado es False.</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>Cuando se establece en True, se amplían automáticamente las opciones alternativas para unirse a una conferencia en línea (como Office Communicator 2007 R2) y se muestran a los usuarios. Cuando se establece en False (el valor predeterminado), estas opciones están disponibles pero el usuario tiene que mostrar la lista de opciones personalmente.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a>Para configurar la página de participación en la reunión mediante el shell de administración de Lync Server 2013

1.  Inicie el shell de administración de Lync Server 2013: haga clic en **Inicio**, **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Para ver las opciones de configuración del servicio web, ejecute el cmdlet siguiente:
    
        Get-CsWebServiceConfiguration

3.  Ejecute el siguiente comando, con los parámetros establecidos en true o false, en función de sus preferencias (para obtener información detallada sobre los parámetros de este cmdlet, consulte [set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) en la documentación del shell de administración de Lync Server 2013):
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a>Vea también


[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

