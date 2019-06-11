---
title: 'Lync Server 2013: Configurar directivas para el control del acceso de usuarios remotos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6e542f2a2d836cce507863347384135f97db445
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a>Configurar directivas para el control del acceso de usuarios remotos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

Configure una o más directivas de acceso de usuarios externos para controlar si los usuarios remotos pueden colaborar con usuarios internos de Lync Server. Para controlar el acceso de usuarios remotos, puede configurar directivas en el nivel global, de sitio y de usuario. Las directivas de sitio invalidan la directiva global y las directivas de usuario invalidan las directivas globales y del sitio. Para obtener más información sobre los tipos de directivas que puede configurar, consulte [administrar la Federación y el acceso externo a Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md). La configuración de directiva de Lync Server que se aplica a un nivel de Directiva puede invalidar la configuración que se aplica a otro nivel de directiva. La prioridad de la Directiva de Lync Server es: la Directiva de usuario (más influencia) reemplaza a una directiva de sitio y, después, una directiva de sitio invalida una directiva global (menor influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.

<div>


> [!NOTE]  
> Puede configurar directivas para controlar el acceso de usuarios remotos, incluso si no ha habilitado el acceso de usuarios remotos para su organización. Sin embargo, las directivas que configure solo estarán vigentes cuando tenga habilitado el acceso de usuarios remotos en su organización. Para obtener más información sobre cómo habilitar el acceso de usuarios remotos, vea <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013</A>. Además, si especifica una directiva de usuario para controlar el acceso de usuarios remotos, la Directiva solo se aplica a los usuarios que están habilitados para Lync Server y que usan la Directiva. Para más información sobre cómo especificar usuarios que pueden iniciar sesión en Lync Server desde ubicaciones remotas, consulte <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">asignar una directiva de acceso de usuarios externos a un usuario habilitado de Lync en Lync Server 2013</A>.



</div>

Use el procedimiento siguiente para configurar cada directiva de acceso externo que desee usar para controlar el acceso de usuarios remotos.

<div>


> [!NOTE]  
> Este procedimiento describe cómo configurar una directiva solo para habilitar las comunicaciones con usuarios remotos, pero cada directiva que se configura para admitir el acceso de usuarios remotos también puede configurar el acceso de usuarios federados y el acceso de usuarios públicos. Para obtener más información sobre cómo configurar directivas para admitir usuarios federados, vea <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013</A>. Para obtener más información sobre cómo configurar directivas para admitir usuarios públicos, consulte <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">crear o editar proveedores federados de SIP públicos en Lync Server 2013</A>.



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>Para configurar una directiva de acceso externo para admitir el acceso de usuarios remotos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**y, después, en **Directiva de acceso externo**.

4.  En la página **Directiva de acceso externo** , realice una de las siguientes acciones:
    
      - Para configurar la directiva global para que admita el acceso de usuarios remotos, haga clic en la directiva global, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.
    
      - Para crear una nueva Directiva de sitio, haga clic en **nueva**y, a continuación, haga clic en **Directiva del sitio**. En **seleccionar un sitio**, haga clic en el sitio adecuado de la lista y, a continuación, haga clic en **Aceptar**.
    
      - Para crear una nueva Directiva de usuario, haga clic en **nueva**y, a continuación, haga clic en **Directiva de usuario**. En **nueva Directiva de acceso externo**, cree un nombre único en el campo **nombre** que indique lo que cubre la Directiva de usuario (por ejemplo, **EnableRemoteUsers** para una directiva de usuario que permita comunicaciones para usuarios remotos).
    
      - Para cambiar una directiva existente, haga clic en la directiva correspondiente que aparece en la tabla, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

5.  Faculta Si desea agregar o editar una descripción, especifique la información de la Directiva en **Descripción**.

6.  Siga uno de estos pasos:
    
      - Para habilitar el acceso de usuarios remotos para la Directiva, active la casilla **habilitar las comunicaciones con usuarios remotos** .
    
      - Para deshabilitar el acceso de usuarios remotos para la Directiva, desactive la casilla **Habilitar comunicaciones con usuarios remotos** .

7.  Haga clic en **Confirmar**.

Para habilitar el acceso de usuarios remotos, también debe habilitar el soporte técnico para el acceso de usuarios remotos en su organización. Para obtener más información, vea [habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) en la documentación de implementación o en la documentación de operaciones.

Si se trata de una directiva de usuario, también debe aplicar la Directiva a los usuarios que desee que puedan conectarse de forma remota. Para obtener más información, vea [asignar una directiva de acceso de usuarios externos a un usuario habilitado de Lync en Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) en la documentación de implementación o en la documentación de operaciones.

</div>

</div>

<span> </span>

</div>

</div>

</div>

