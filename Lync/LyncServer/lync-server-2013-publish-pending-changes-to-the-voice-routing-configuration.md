---
title: 'Lync Server 2013: publicar los cambios pendientes en la configuración del enrutamiento de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish pending changes to the voice routing configuration
ms:assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413088(v=OCS.15)
ms:contentKeyID: 48185974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9307389d89418e6a50259cebca6c71b121618eab
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a>Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-08-07_

Después de realizar algún cambio en cualquiera de las opciones de configuración de las páginas del grupo **Enrutamiento de voz**, siga este procedimiento para revisar, publicar o cancelar los cambios pendientes.

<div>


> [!IMPORTANT]  
> Compruebe que solo modifica las opciones de configuración de Enrutamiento de voz un usuario cada vez.<BR>Todos los cambios pendientes deben publicarse al mismo tiempo, ejecutando el comando <STRONG>Confirmar todo</STRONG>. No se pueden publicar los cambios pendientes de forma selectiva. Antes de publicar los cambios pendientes, ejecute el comando <STRONG>Revisar cambios sin confirmar</STRONG> y cancele los cambios de configuración que no desee publicar.<BR>Si sale de las páginas del grupo <STRONG>Enrutamiento de voz</STRONG> antes de confirmar los cambios pendientes, se perderán todos los cambios pendientes. Sin embargo, puede exportar la configuración actual (incluidos los cambios pendientes) a un archivo de configuración de voz y, a continuación, importar y publicar la configuración actualizada. Para obtener más información, consulte <A href="lync-server-2013-export-a-voice-route-configuration-file.md">exportar un archivo de configuración de enrutamiento de voz en Lync Server 2013</A>.



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>Para revisar, publicar o cancelar cambios de configuración de enrutamiento de voz

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.

4.  Realice los cambios de configuración que desee en las opciones de cada página del grupo **Enrutamiento de voz**.

5.  Para revisar los cambios pendientes sin publicarlos, seleccione **Revisar cambios sin confirmar** en el menú **Confirmar**.

6.  Si desea cancelar alguno de los cambios pendientes, realice una de las siguientes acciones:
    
      - Seleccione **Cancelar todos los cambios sin confirmar** en el menú **Confirmar**.
    
      - Navegue hasta la pestaña de la página de **Enrutamiento de voz** que tiene los cambios pendientes que desea cancelar, seleccione el elemento con cambios pendientes, haga clic en **Confirmar** y, a continuación, haga clic en **Cancelar cambios seleccionados**.

7.  Después de revisar todos los cambios pendientes y cancelar los que no desee publicar, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.

8.  En el cuadro de diálogo **Configuración de voz no confirmada**, que muestra una lista de todos los cambios pendientes, haga clic en **Aceptar**.
    
    Cuando el panel de control de Lync Server ha confirmado los cambios, aparece el mensaje **configuración de enrutamiento de voz publicada correctamente** .

</div>

</div>

<span> </span>

</div>

</div>

</div>

