---
title: 'Lync Server 2013: Configuración de la página de participación en reuniones'
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
ms.openlocfilehash: 8471b6b897a365763d55edcbd55e4a9bab4a3124
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a>Configuración de la página de participación en reuniones en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-12-14_

Cuando un usuario hace clic en un vínculo de reunión en una convocatoria de reunión, la página de la reunión detecta si un cliente de Lync 2013 ya está instalado en el equipo del usuario. Si un cliente ya está instalado, el cliente se abre y se une a la reunión. Si un cliente no está instalado, de forma predeterminada se abre la versión 2013 de Lync Web App.

Puede modificar el comportamiento de la página de la combinación de reuniones si desea permitir que los usuarios se unan a reuniones con Office Communicator 2007 R2 o el operador de Lync 2010. Estas opciones de configuración se han eliminado del panel de control de Lync Server 2013, pero se configuran mediante el cmdlet Set-CsWebServiceConfiguration.

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a>Conjunto de páginas de combinación de reuniones-parámetros de CsWebServiceConfiguration

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
<td><p>ShowJoinUsingLegacyClientLink</p></td>
<td><p>Si se establece en true, los usuarios que se unan a una reunión mediante una aplicación cliente que no sea Lync tendrán la oportunidad de unirse a la reunión mediante Office Communicator 2007 R2. El valor predeterminado es False.</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>Si se establece en true, las opciones alternativas para unirse a una conferencia en línea (como Office Communicator 2007 R2) se expandirán y mostrarán automáticamente a los usuarios. Cuando se establece en false (valor predeterminado), estas opciones estarán disponibles, pero el usuario tendrá que mostrar la lista de opciones por sí mismos.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a>Para configurar la página de la combinación de reuniones con el shell de administración de Lync Server 2013

1.  Inicie el shell de administración de Lync Server 2013: haga clic en **Inicio**, haga clic en **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Para ver la configuración del servicio Web, ejecute el siguiente cmdlet:
    
        Get-CsWebServiceConfiguration

3.  Ejecute el siguiente comando, con los parámetros establecidos en true o false, en función de su preferencia (para obtener información detallada sobre los parámetros para este cmdlet, consulte [set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) en la documentación del shell de administración de Lync Server 2013):
    
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

