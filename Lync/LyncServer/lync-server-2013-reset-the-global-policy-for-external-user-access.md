---
title: 'Lync Server 2013: restablecer la directiva global para el acceso de usuarios externos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset the global policy for external user access
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72c025c15841e55462a5bab4f269e2fc4ed5f49a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511797"
---
# <a name="reset-the-global-policy-for-external-user-access-in-lync-server-2013"></a>Restablecer la directiva global para el acceso de usuarios externos en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

No se puede eliminar íntegramente una política global. Si se usa la opción **Eliminar** en la directiva global solamente se restablece la directiva global según la configuración predeterminada, que no incluye compatibilidad con opciones de acceso para usuarios externos.

<div>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>Para restablecer la directiva global según la configuración predeterminada

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y en **Directiva de acceso externo**.

4.  En la ficha **Directiva de acceso externo**, haga clic en la directiva global, haga en **Editar** y, a continuación, haga clic en **Eliminar**.

5.  Cuando se le solicite confirmar la eliminación, haga clic en **Aceptar**. Aparecerá un mensaje en la parte superior de la página donde se le comunica que la directiva global se ha restablecido.

</div>

<div>

## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Restablecimiento de la Directiva de acceso externo global mediante cmdlets de Windows PowerShell

La Directiva de acceso externo global se puede restablecer mediante Windows PowerShell y el cmdlet Remove-CsExternalAccessPolicy. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-reset-the-global-external-access-policy"></a>Para restablecer la Directiva de acceso externo global

  - Este comando restablece la directiva de acceso externo global:
    
        Remove-CsExternalAccessPolicy -Identity "global"

</div>

Para obtener más información, consulte el tema de ayuda del cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

