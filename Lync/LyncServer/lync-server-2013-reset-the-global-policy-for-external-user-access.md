---
title: 'Lync Server 2013: Restablecer la directiva global para el acceso de usuarios externos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reset the global policy for external user access
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 327a658bcd75c05e291798598e53947b23c0c12f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-the-global-policy-for-external-user-access-in-lync-server-2013"></a>Restablecer la directiva global para el acceso de usuarios externos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

No puede eliminar completamente una directiva global. El uso de la opción **eliminar** en la directiva global solo restablece la directiva global a la configuración predeterminada, que no incluye compatibilidad con las opciones de acceso de usuarios externos.

<div>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>Para restablecer la configuración predeterminada de la directiva global

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**, haga clic en **Directiva de acceso externo**.

4.  En la pestaña **Directiva de acceso externo** , haga clic en la directiva global, haga clic en **Editar**y, a continuación, haga clic en **eliminar**.

5.  Cuando se le pida que confirme la eliminación, haga clic en **Aceptar**. En la parte superior de la página aparece un mensaje que le informa de que se ha restablecido la directiva global.

</div>

<div>

## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Restablecer la Directiva de acceso externo global mediante cmdlets de Windows PowerShell

La Directiva de acceso externo global se puede restablecer mediante Windows PowerShell y el cmdlet Remove-CsExternalAccessPolicy. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-reset-the-global-external-access-policy"></a>Para restablecer la Directiva de acceso externo global

  - Este comando restablece la Directiva de acceso externo global:
    
        Remove-CsExternalAccessPolicy -Identity "global"

</div>

Para obtener más información, consulte el tema de ayuda para el cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

