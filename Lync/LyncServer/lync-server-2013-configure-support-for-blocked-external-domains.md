---
title: 'Lync Server 2013: configurar la compatibilidad con dominios externos bloqueados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for blocked external domains
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49733638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1be998071bc0cad49d3e96c3c82cf395b2da7ca1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515687"
---
# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a>Configurar la compatibilidad con dominios externos bloqueados en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

Si ha configurado la compatibilidad para socios federados, puede administrar los dominios que se bloquearán de la federación con su organización. La lista de dominios bloqueados actuará como una lista de bloqueo (lista de entradas explícitas que no se van a permitir) y se aplicará en la detección de dominios federados, si tiene activada esta opción. Para obtener más información, consulte [habilitar o deshabilitar la detección de socios de Federación en Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).

Bloquee uno o más dominios externos para que no puedan conectarse a su organización. Para hacerlo, agregue el dominio a la lista de dominios bloqueados.

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>Para agregar un dominio externo a la lista de dominios bloqueados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Acceso de usuarios externos **.

4.  Seleccione **Dominios federados **, haga clic en **Nuevo ** y, a continuación, seleccione **Dominio bloqueado **.

5.  En **Nuevos dominios federados **, haga lo siguiente:
    
      - En **Nombre de dominio (o FQDN) **, escriba el nombre de dominio de socio federado que desea bloquear.
        
        <div>
        

        > [!NOTE]  
        > El nombre no puede superar los 256 caracteres.<BR>La búsqueda del dominio de socio federado busca la coincidencia de sufijos. Por ejemplo, si escribe <STRONG>contoso.com</STRONG>, la búsqueda devolverá el dominio <STRONG>it.contoso.com</STRONG>.<BR>Un dominio de socio federado no puede bloquearse y permitirse simultáneamente. Lync Server 2013 impide que esto suceda, por lo que no es necesario sincronizar las listas.

        
        </div>
    
      - (Opcional) En **Comentario **, escriba la información que desea compartir con otros administradores del sistema sobre esta configuración.

6.  Haga clic en **Confirmar **.

7.  Repita los pasos del 4 al 6 para cada socio federado que desee bloquear.

Para habilitar el acceso de usuarios federados, también debe permitir el acceso de usuarios federados en su organización. Para obtener más información, consulte [habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

Además, debe configurar y aplicar la directiva a los usuarios que quiera permitir que colaboren con usuarios federados. Para obtener más información, consulte [Configure Policies to control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

