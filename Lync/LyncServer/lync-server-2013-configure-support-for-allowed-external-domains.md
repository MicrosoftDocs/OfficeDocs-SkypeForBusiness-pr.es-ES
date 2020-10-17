---
title: 'Lync Server 2013: configurar la compatibilidad con dominios externos permitidos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2eaa9da579561464c46776662cacaca80dafe016
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517693"
---
# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a>Configurar la compatibilidad con dominios externos permitidos en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Si ha configurado la compatibilidad para socios federados, puede administrar qué dominios específicos pueden federar con su organización. Se configuran uno o más dominios externos específicos como dominios federados permitidos. Para hacerlo, agregue cada uno de los dominios a la lista de dominios admitidos. Incluso en el caso de que la detección de socios esté habilitada en la organización, haga lo anterior si el dominio es un socio federado que podría necesitar comunicarse con más de 1.000 usuarios o enviar más de 20 mensajes por segundo. Si la detección de socios no está habilitada en la organización, solo los usuarios de dominios externos que agregue a la lista de dominios permitidos podrán participar en reuniones y compartir mensajería instantánea con usuarios de su organización. Si desea restringir el acceso de un dominio federado a un servidor específico que ejecuta el servicio perimetral de acceso del socio federado, puede especificar el nombre de dominio del servidor que ejecuta el servicio perimetral de acceso para cada dominio de la lista de dominios permitidos.

<div>


> [!NOTE]  
> Este procedimiento describe cómo configurar la compatibilidad para dominios específicos, pero para permitir usuarios federados es necesario habilitar también dicha compatibilidad en la organización y, además, configurar y aplicar directivas para determinar qué usuarios pueden colaborar con usuarios federados. Para obtener más información sobre cómo habilitar la compatibilidad con usuarios federados, consulte <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013</A>. Para más información sobre la configuración de directivas para controlar la Federación, vea <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure Policies to control Federated User Access in Lync Server 2013</A>.



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>Para agregar un dominio externo a la lista de dominios permitidos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En el barra de navegación izquierda, haga clic en **Acceso de usuarios externos** y, a continuación, en **Dominios federados**.

4.  En la página **Dominios federados**, haga clic en **Nuevo** y, a continuación, seleccione **Dominio permitido**.

5.  En **Nuevos dominios federados**, haga lo siguiente:
    
      - En **Nombre de dominio (o FQDN)**, escriba el nombre de dominio de socio federado.
        
        <div>
        

        > [!NOTE]  
        > El nombre debe ser único y no puede haber otro dominio permitido con el mismo nombre en el servidor que ejecuta el servicio perimetral de acceso. El nombre no puede superar los 256 caracteres.<BR>La búsqueda del dominio de socio federado busca la coincidencia de sufijos. Por ejemplo, si escribe <STRONG>contoso.com</STRONG>, la búsqueda devolverá el dominio <STRONG>it.contoso.com</STRONG>.<BR>Un dominio de socio federado no puede bloquearse y permitirse simultáneamente. Lync Server 2013 impide que esto suceda, por lo que no es necesario sincronizar las listas.

        
        </div>
    
      - Si desea restringir el acceso de este dominio federado a usuarios de un servidor específico que ejecuta el servicio perimetral de acceso, en **Servicio perimetral de acceso(FQDN)**, escriba el FQDN del servidor del dominio federado que ejecuta el servicio perimetral de acceso.
    
      - Si desea proporcionar información adicional, en **Comentario**, escriba la información que desee compartir con otros administradores del sistema sobre esta configuración.

6.  Haga clic en **Confirmar**.

7.  Repita los pasos del 4 al 6 para cada dominio de socio federado que desee permitir.

Para habilitar el acceso de usuarios federados, también debe permitir el acceso de usuarios federados en su organización. Para obtener más información, consulte [habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

Además, debe configurar y aplicar la directiva a los usuarios que quiera permitir que colaboren con usuarios federados. Para obtener más información, consulte [Configure Policies to control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

