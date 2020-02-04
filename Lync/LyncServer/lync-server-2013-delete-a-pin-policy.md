---
title: 'Lync Server 2013: eliminar una directiva de PIN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a PIN policy
ms:assetid: 7c378927-2e41-418e-9721-327021bd2e45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521020(v=OCS.15)
ms:contentKeyID: 48184609
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc11f1383ec652c512fe5542d9a6780ce028c516
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-pin-policy-in-lync-server-2013"></a>Eliminar una directiva de PIN en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Siga estos pasos para eliminar una directiva de número de identificación personal (PIN).

<div>


> [!NOTE]  
> No puede eliminar la directiva global de PIN.



</div>

<div>

## <a name="to-delete-a-pin-policy-in-lync-server-2013-control-panel"></a>Para eliminar una directiva de PIN en el panel de control de Lync Server 2013

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Directiva de PIN**.

4.  En la página **Directiva de PIN**, escriba en el campo de búsqueda el nombre completo o parcial de la directiva que desea eliminar.

5.  En la lista de directivas, haga clic en la directiva que desea, en **Editar** y en **Eliminar**.

6.  Haga clic en **Aceptar**.

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Quitar directivas de PIN mediante cmdlets de Windows PowerShell

Puede eliminar directivas de PIN mediante Windows PowerShell y el cmdlet Remove-CsPinPolicy. Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-remove-a-specific-pin-policy"></a>Quitar una directiva de PIN específica

  - Este comando quita la Directiva de PIN con la RedmondPinPolicy de identidad:
    
        Remove-CsPinPolicy -Identity "RedmondPinPolicy"

</div>

<div>

## <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>Quitar todas las directivas de PIN que se aplican al ámbito del sitio

  - Este comando quita todas las directivas de PIN configuradas en el ámbito del sitio:
    
        Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy

</div>

<div>

## <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>Quitar todas las directivas de PIN que permiten el uso de patrones comunes

  - Y este elimina todas las Directivas de PIN que permiten el uso de patrones comunes:G
    
        et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy

</div>

Para obtener más información, consulte el tema de ayuda para el cmdlet [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

