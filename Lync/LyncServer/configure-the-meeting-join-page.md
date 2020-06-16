---
title: Configurar la página para unirse a la reunión
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the meeting join page
ms:assetid: 036c9d03-ad95-4d63-a3d8-6cae1a8ad530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204635(v=OCS.15)
ms:contentKeyID: 48183260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10700dc8a75d5c067870b53c0e0e74b7a469504a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-meeting-join-page"></a>Configurar la página para unirse a la reunión

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-12-14_

Cuando un usuario hace clic en un vínculo de reunión en una convocatoria de reunión, la página de participación en la reunión detecta si un cliente de Lync 2013 ya está instalado en el equipo del usuario. Si un cliente ya está instalado, ese cliente se abre y se une a la reunión. Si un cliente no está instalado, se abre de forma predeterminada la versión 2013 de Lync Web App.

Puede modificar el comportamiento de la página de participación en la reunión si desea permitir que los usuarios se unan a reuniones con Office Communicator 2007 R2 o el operador de Lync 2010. Estas opciones de configuración se han quitado del panel de control de Lync Server 2013, pero puede configurarlas mediante el cmdlet CsWebServiceConfiguration.

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a>Parámetros de CsWebServiceConfiguration de la página para unirse a la reunión

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Parámetro de CsWebServiceConfiguration</th>
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
<td><p>When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users. When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a>Para configurar la página de participación en la reunión mediante el shell de administración de Lync Server 2013

1.  Inicie el shell de administración de Lync Server 2013: haga clic en **Inicio**, **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Ejecute el siguiente cmdlet:
    
        Get-CsWebServiceConfiguration
    
    Este cmdlet devuelve las opciones de configuración del servicio web.

3.  Ejecute el siguiente comando, con los parámetros establecidos en true o false, en función de sus preferencias (para obtener información detallada sobre los parámetros de este cmdlet, consulte la documentación del shell de administración de Lync Server 2013):
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

