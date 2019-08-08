---
title: Configurar la página para unirse a la reunión
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure the meeting join page
ms:assetid: 036c9d03-ad95-4d63-a3d8-6cae1a8ad530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204635(v=OCS.15)
ms:contentKeyID: 48183260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c01c2be988c94bd0bc90ed6b48702d426b42e505
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-meeting-join-page"></a>Configurar la página para unirse a la reunión

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-12-14_

Cuando un usuario hace clic en un vínculo de reunión en una convocatoria de reunión, la página de la reunión detecta si un cliente de Lync 2013 ya está instalado en el equipo del usuario. Si un cliente ya está instalado, ese cliente se abre y se une a la reunión. Si un cliente no está instalado, de forma predeterminada se abre la versión 2013 de Lync Web App.

Puede modificar el comportamiento de la página de la combinación de reuniones si desea permitir que los usuarios se unan a reuniones con Office Communicator 2007 R2 o el operador de Lync 2010. Estas opciones de configuración se han eliminado del panel de control de Lync Server 2013, pero se configuran mediante el cmdlet CsWebServiceConfiguration.

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a>Página de combinación de reuniones CsWebServiceConfiguration parámetros

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Parámetro CsWebServiceConfiguration</th>
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

2.  Ejecute el siguiente cmdlet:
    
        Get-CsWebServiceConfiguration
    
    Este cmdlet devuelve los parámetros de configuración del servicio Web.

3.  Ejecute el siguiente comando, con los parámetros establecidos en true o false, en función de su preferencia (para obtener información detallada sobre los parámetros para este cmdlet, consulte la documentación del shell de administración de Lync Server 2013):
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

