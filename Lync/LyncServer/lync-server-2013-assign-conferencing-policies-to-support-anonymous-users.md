---
title: 'Lync Server 2013: asignar directivas de conferencia para admitir usuarios anónimos'
description: 'Lync Server 2013: asignar directivas de conferencia para admitir usuarios anónimos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign conferencing policies to support anonymous users
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07e94c3097e3e21f854e91fdee1ad0b33c3b9f53
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566166"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a>Asignar directivas de conferencia para admitir usuarios anónimos en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

De forma predeterminada, ningún usuario tiene permitido invitar a usuarios anónimos a participar en una reunión. Para controlar quién puede invitar a usuarios anónimos, se debe configurar una directiva de conferencias que admita la participación de usuarios anónimos, y aplicar dicha directiva a usuarios específicos. Para obtener más información sobre cómo configurar directivas de conferencia para admitir usuarios anónimos, vea [crear o modificar una directiva de conferencia en Lync server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) y [administrar la Federación y el acceso externo a Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).

Use el procedimiento descrito en esta sección para aplicar una directiva de conferencia que ya haya creado a uno o más usuarios o grupos de usuarios.

<div>


> [!NOTE]  
> Además de configurar y aplicar una directiva para permitir que los usuarios inviten a usuarios anónimos, también debe habilitar la compatibilidad con usuarios anónimos en su organización. Para obtener más información, consulte <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013</A>.



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>Para configurar una directiva de usuario para la participación anónima en las reuniones

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Conferencia** y, a continuación, siga uno de estos procedimientos:
    
    1.  Para crear una directiva de usuario nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de usuario**. Cree un nombre único en el campo **nombre** que indique lo que cubre la Directiva de usuario (por ejemplo, **EnableAnonymous** para una directiva de usuario que permita las comunicaciones con usuarios anónimos).
    
    2.  Para configurar una directiva de usuario existente, haga clic en la directiva correspondiente que aparece en la tabla, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

4.  En el cuadro de diálogo **directivas de conferencia** , active la casilla de verificación **permitir que los participantes inviten a usuarios anónimos** .

5.  Haga clic en **Confirmar**.

6.  En la barra de navegación izquierda, haga clic en **usuarios**y busque la cuenta de usuario que desea configurar.

7.  En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en  **Editar ** y, a continuación, en  **Mostrar detalles **.

8.  En **Editar usuario de Lync Server** en **Directiva de conferencia**, seleccione la Directiva de usuario con la configuración de acceso de usuario anónimo que desea aplicar a este usuario.
    
    <div>
    

    > [!NOTE]  
    > La configuración <STRONG> &lt; automática &gt; </STRONG> aplica la configuración de la instalación del servidor predeterminada y el servidor la aplica automáticamente.

    
    </div>

Para permitir a los usuarios invitar a usuarios anónimos a conferencias, también tiene que habilitar la compatibilidad con usuarios anónimos en la organización. Para obtener más información, consulte [configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) en la documentación de implementación o en la documentación de operaciones.

</div>

</div>

<span> </span>

</div>

</div>

</div>

