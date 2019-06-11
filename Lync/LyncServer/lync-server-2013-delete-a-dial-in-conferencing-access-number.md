---
title: 'Lync Server 2013: eliminar un número de acceso de conferencia de acceso telefónico local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a dial-in conferencing access number
ms:assetid: 199c5d9c-0489-4ad5-a7f1-ca59fe0e6ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520956(v=OCS.15)
ms:contentKeyID: 48183522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2559b8a3e053c02a6a67ccc17ab5a1f25b46a05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-dial-in-conferencing-access-number-in-lync-server-2013"></a>Eliminar un número de acceso de conferencia de acceso telefónico local en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Siga estos pasos para eliminar un número de acceso de conferencia de acceso telefónico local.

<div>

## <a name="to-delete-a-dial-in-conferencing-access-number"></a>Para eliminar un número de acceso de conferencia de acceso telefónico local

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación de la izquierda, haga clic en **Conferencia** y después en **Número de acceso telefónico local**.

4.  En la página, haga clic en el número de acceso telefónico local que desea eliminar de la lista, haga clic en **Editar** y luego en **Eliminar**.

5.  Haga clic en **Aceptar**.

</div>

<div>

## <a name="removing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a>Quitar números de acceso a la Conferencia de acceso telefónico local mediante cmdlets de Windows PowerShell

Los números de acceso de la Conferencia de acceso telefónico local se pueden eliminar con Windows PowerShell y el cmdlet **Remove-CsDialInConferencingAccessNumber** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-remove-a-specific-dial-in-conferencing-access-number"></a>Para quitar un número de acceso de conferencia de acceso telefónico local específico

  - Este comando elimina el número de acceso de la Conferencia de acceso telefónico local con la identidad sip:RedmondDialInAccess@litwareinc.com:
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

</div>

<div>

## <a name="to-remove-all-the-dial-in-conferencing-access-numbers-assigned-to-a-specific-region"></a>Para quitar todos los números de acceso de la Conferencia de acceso telefónico local asignados a una región específica

  - Este comando elimina todos los números de acceso de la Conferencia de acceso telefónico local asociados con la región del noroeste:
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

</div>

<div>

## <a name="to-remove-dial-in-conferencing-access-numbers-based-on-primary-language"></a>Para quitar los números de acceso a la Conferencia de acceso telefónico local en función del idioma principal

  - Este comando elimina todos los números de acceso de la Conferencia de acceso telefónico local en los que el italiano es el idioma principal:
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

</div>

Para obtener más información, consulte el tema de ayuda para el cmdlet [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

