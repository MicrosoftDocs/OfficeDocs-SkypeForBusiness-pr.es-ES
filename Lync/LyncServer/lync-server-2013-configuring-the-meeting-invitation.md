---
title: 'Lync Server 2013: configuración de la invitación a la reunión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting invitation
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398638(v=OCS.15)
ms:contentKeyID: 48184641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bd615179a3aac9edcebb45dd2241ebf17453951
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a>Configuración de la invitación a la reunión en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-16_

Puede personalizar las invitaciones a reuniones enviadas por el complemento de reunión en línea para Lync 2013 mediante la inclusión de los siguientes elementos opcionales en el cuerpo de la invitación a la reunión:

  - **Logotipo de la organización** Agregue el logotipo de su organización a invitaciones a reuniones mediante la opción de dirección URL del logotipo. Si las invitaciones a reuniones se enviarán a personas externas a la organización, la imagen debe estar ubicada en una dirección URL disponible públicamente. Los formatos de imagen admitidos son GIF y JPG. Aunque Lync Server 2013 almacena la dirección URL sin restricciones de tamaño en la imagen, para obtener los mejores resultados, el tamaño máximo de la imagen debe ser de 30 píxeles de alto por 188 píxeles de ancho.

  - **Vínculo personalizado de ayuda o soporte técnico** Agregue una dirección URL para el sitio web de ayuda o soporte técnico de la organización. Si se van a enviar invitaciones a reuniones a personas externas a la organización, la dirección URL debe estar disponible públicamente. La longitud máxima de la dirección URL es 1 KB.

  - **Texto de declinación de responsabilidades legal** Agregue una dirección URL para el texto legal o un aviso de declinación de responsabilidades que se mostrará en todas las invitaciones a reuniones. Si se van a enviar invitaciones a reuniones a personas externas a la organización, la dirección URL debe estar disponible públicamente. La longitud máxima de la dirección URL es 1 KB.

  - **Texto de pie de página personalizado** Agregar texto que se representará como pie de página personalizado en la invitación. La longitud máxima del texto que se puede Agregar es 2 KB.

Puede configurar estas opciones mediante el panel de control de Lync Server o el shell de administración de Lync Server.

<div>


**Para personalizar la invitación a la reunión mediante el panel de control de Lync Server**

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.

4.  En la página **Configuración de reunión**, haga clic en **Nueva** y después realice una de las siguientes acciones:
    
      - Para crear una directiva de nivel de sitio, haga clic en **Configuración de sitio**. En el campo de búsqueda **Seleccionar un sitio**, escriba el nombre, o parte del nombre, del sitio para el que desee definir la configuración de participación en reuniones. En la lista de sitios resultante, haga clic en el sitio que desee y después en **Aceptar**.
    
      - Para crear una directiva de nivel de grupo de servidores, haga clic en **Configuración del grupo de servidores**. En el campo de búsqueda **Seleccionar un servicio**, escriba el nombre, o parte del nombre, del servicio del grupo de servidores para el que desee definir la configuración de participación en reuniones. En la lista de servicios resultante, haga clic en el grupo de servidores que desee y después en **Aceptar**.

5.  Siga uno de estos procedimientos:
    
      - En el campo **dirección URL del logotipo** , escriba la dirección URL de la imagen de logotipo de su organización.
    
      - En el campo **dirección URL** de la ayuda, escriba la dirección URL del sitio de ayuda o soporte técnico de su organización.
    
      - En el campo **texto legal** , escriba la dirección URL del texto legal o declinación de responsabilidades que desea incluir en las invitaciones a reuniones.
    
      - En el campo de **texto personalizado de pie de página** , escriba texto de pie de página, hasta 2 KB.

**Para personalizar la invitación a la reunión con el shell de administración de Lync Server**

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet **New-CsMeetingConfiguration** o **set-CsMeetingConfiguration** para crear o configurar las opciones de la invitación a la reunión. Por ejemplo, ejecute:
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

