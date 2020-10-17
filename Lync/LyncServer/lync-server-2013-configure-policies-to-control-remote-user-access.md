---
title: 'Lync Server 2013: configurar directivas para controlar el acceso de usuarios remotos'
description: 'Lync Server 2013: configurar directivas para controlar el acceso de usuarios remotos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6408747cfbbc5e7dff8fd198c0de162f49fc5ff2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548716"
---
# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a>Configurar directivas para controlar el acceso de usuarios remotos en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

Configure una o más directivas de acceso de usuarios externos para controlar si los usuarios remotos pueden colaborar con usuarios internos de Lync Server. Para controlar el acceso de usuarios remotos, puede configurar directivas en el nivel global, de sitio y de usuario. Las directivas de sitio invalidan la directiva global y las directivas de usuario invalidan las directivas de sitio y globales. Para obtener más información sobre los tipos de directivas que puede configurar, consulte [Managing Federation and external Access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md). La configuración de la Directiva de Lync Server que se aplica en un nivel de Directiva puede invalidar la configuración que se aplica en otro nivel de directiva. La prioridad de la Directiva de Lync Server es: la Directiva de usuario (más influencia) reemplaza una directiva de sitio y, a continuación, una directiva de sitio invalida una directiva global (menor influencia). Esto significa que cuanto más se aproxime la configuración de la directiva al objeto al que afecta la directiva, más influencia tendrá en el objeto.

<div>


> [!NOTE]  
> Puede configurar directivas para controlar el acceso de usuarios remotos, incluso aunque no se haya habilitado el acceso de usuarios remotos en su organización. Sin embargo, las directivas que se configuran solo son efectivas cuando se habilita el acceso de usuarios remotos en su organización. Para obtener información detallada sobre cómo habilitar el acceso de usuarios remotos, vea <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013</A>. Además, si especifica una directiva de usuario para controlar el acceso de usuarios remotos, la Directiva solo se aplica a los usuarios que están habilitados para Lync Server y que están configurados para usar la Directiva. Para obtener información detallada sobre cómo especificar los usuarios que pueden iniciar sesión en Lync Server desde ubicaciones remotas, consulte <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync en Lync Server 2013</A>.



</div>

Use el procedimiento siguiente para configurar cada directiva de acceso externo que desea usar para controlar el acceso de usuarios remotos.

<div>


> [!NOTE]  
> Este procedimiento describe cómo se configura una directiva solo para habilitar comunicaciones con usuarios remotos, pero cada directiva que se configura para permitir el acceso de usuarios remotos puede también configurar el acceso de usuarios federados y usuarios públicos. Para obtener más información sobre cómo configurar directivas para admitir usuarios federados, consulte <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013</A>. Para más información sobre cómo configurar directivas para admitir usuarios públicos, vea <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">crear o editar proveedores federados de SIP públicos en Lync Server 2013</A>.



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>Para configurar una directiva de acceso de usuarios externos para permitir el acceso de usuarios remotos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y, a continuación, en **Directiva de acceso externo**.

4.  En la página **Directiva de acceso externo**, siga uno de estos procedimientos:
    
      - Para configurar la directiva global para permitir el acceso de usuarios remotos, haga clic en la directiva global, seleccione **Editar** y, a continuación, haga clic en **Mostrar detalles**.
    
      - Para crear una directiva de sitio nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de sitio**. En **Seleccionar un sitio**, haga clic en el sitio apropiado de la lista y, a continuación, en **Aceptar**.
    
      - Para crear una directiva de usuario nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de usuario**. En **Nueva directiva de acceso externo**, cree un nombre único en el campo **Nombre** que indique los aspectos que cubre la directiva de usuario (por ejemplo, **EnableRemoteUsers** para una directiva de usuario que permita comunicaciones a usuarios remotos).
    
      - Para cambiar una directiva existente, haga clic en la directiva correspondiente que aparece en la tabla, en **Editar** y, a continuación en **Mostrar detalles**.

5.  (Opcional) Si quiere agregar o editar una descripción, especifique la información para la directiva en **Descripción**.

6.  Siga uno de estos procedimientos:
    
      - Para habilitar el acceso de usuarios remotos de la directiva, active la casilla **Habilitar comunicaciones con usuarios remotos**.
    
      - Para deshabilitar el acceso de usuarios remotos de la directiva, desactive la casilla **Habilitar comunicaciones con usuarios remotos**.

7.  Haga clic en **Confirmar**.

Para habilitar el acceso de usuarios remotos, también debe permitir el acceso de usuarios remotos en su organización. Para obtener más información, consulte [habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) en la documentación de implementación o en la documentación de operaciones.

Si se trata de una directiva de usuario, también debe aplicar la directiva a usuarios a los que quiera permitir conectarse de forma remota. Para obtener más información, consulte [asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync en Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) en la documentación de implementación o en la documentación de operaciones.

</div>

</div>

<span> </span>

</div>

</div>

</div>

