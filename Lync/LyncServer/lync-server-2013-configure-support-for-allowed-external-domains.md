---
title: 'Lync Server 2013: Configurar la compatibilidad con dominios externos permitidos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfab1a41f39d975d2920bdf97ea601618277f35a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a>Configurar la compatibilidad con dominios externos permitidos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Si ha configurado la compatibilidad con los socios federados, puede administrar los dominios específicos que se pueden federar con su organización. Configure uno o varios dominios externos específicos como dominios federados permitidos. Para ello, agregue cada dominio a la lista de dominios permitidos. Incluso si el descubrimiento de Partners está habilitado para su organización, haga esto si el dominio es un socio federado que puede que necesite comunicarse con más de 1.000 de sus usuarios o que necesite enviar más de 20 mensajes por segundo. Si el descubrimiento de Partners no está habilitado para su organización, solo los usuarios de dominios externos que agregue a la lista de dominios permitidos podrán participar en la mensajería instantánea y las conferencias con los usuarios de su organización. Si desea restringir el acceso de un dominio federado a un servidor específico que ejecute el servicio perimetral de acceso del socio federado, puede especificar el nombre de dominio del servidor que ejecuta el servicio perimetral de acceso para cada dominio de la lista de dominios permitidos.

<div>


> [!NOTE]  
> Este procedimiento describe cómo configurar la compatibilidad con dominios específicos, pero la implementación de soporte técnico para usuarios federados también requiere que habilite la compatibilidad con usuarios federados para su organización, y configure y aplique directivas para controlar qué usuarios pueden colaborar con usuarios federados. Para obtener más información sobre cómo habilitar la compatibilidad para usuarios federados, consulte <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013</A>. Para obtener más información sobre cómo configurar directivas para controlar la Federación, consulte <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013</A>.



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>Para agregar un dominio externo a la lista de dominios permitidos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**y, a continuación, en **dominios federados**.

4.  En la página **dominios federados** , haga clic en **nuevo**y, a continuación, haga clic en **dominio permitido**.

5.  En **nuevos dominios federados**, haga lo siguiente:
    
      - En **nombre de dominio (o FQDN)**, escriba el nombre del dominio del socio federado.
        
        <div>
        

        > [!NOTE]  
        > Este nombre debe ser único y no puede existir como dominio permitido para este servidor que ejecuta el servicio perimetral de acceso. El nombre no puede superar los 256 caracteres de longitud.<BR>La búsqueda en el nombre de dominio del socio federado realiza una coincidencia de sufijo. Por ejemplo, si escribe <STRONG>contoso.com</STRONG>, la búsqueda también devolverá el dominio <STRONG>it.contoso.com</STRONG>.<BR>Un dominio del socio federado no puede bloquearse y permitirse al mismo tiempo. Lync Server 2013 impide que esto suceda, por lo que no es necesario sincronizar las listas.

        
        </div>
    
      - Si desea restringir el acceso a este dominio federado a los usuarios de un servidor específico que ejecute el servicio perimetral de acceso, en el **servicio perimetral de acceso (FQDN)**, escriba el FQDN del servidor del dominio federado que ejecuta el servicio perimetral de acceso.
    
      - Si desea proporcionar información adicional, en **Comentario**, escriba la información que desea compartir con otros administradores del sistema acerca de esta configuración.

6.  Haga clic en **Confirmar**.

7.  Repita los pasos 4 a 6 para cada dominio de socio federado que desee permitir.

Para habilitar el acceso de usuarios federados, también debe habilitar la compatibilidad con el acceso de usuarios federados de su organización. Para obtener más información, vea [habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

Además, debe configurar y aplicar la Directiva a los usuarios que desee que puedan colaborar con los usuarios federados. Para obtener más información, vea [configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

