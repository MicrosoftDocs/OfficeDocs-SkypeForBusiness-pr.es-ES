---
title: 'Lync Server 2013: Configurar la compatibilidad con dominios externos bloqueados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure support for blocked external domains
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49733638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08191e8600f5e247ba6b4a358557ea3def0a1756
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a>Configurar la compatibilidad con dominios externos bloqueados en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

Si ha configurado la compatibilidad con los socios federados, puede administrar los dominios que estarán bloqueados para que no se federen con su organización. La lista de dominios bloqueados actuará como una lista de bloqueados (lista de entradas explícitas no permitidas) y se aplicará en la detección de dominios federados, si tiene esta opción habilitada. Para obtener más información, vea [habilitar o deshabilitar la detección de socios de Federación en Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).

Bloquear la conexión de uno o varios dominios externos a su organización. Para ello, agregue el dominio a la lista de dominios bloqueados.

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>Para agregar un dominio externo a la lista de dominios bloqueados

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**.

4.  Haga clic en **dominios federados**, en **nuevo**y, a continuación, en **dominio bloqueado**.

5.  En **nuevos dominios federados**, haga lo siguiente:
    
      - En **nombre de dominio (o FQDN)**, escriba el nombre del dominio del socio federado que desea bloquear.
        
        <div>
        

        > [!NOTE]  
        > El nombre no puede superar los 256 caracteres de longitud.<BR>La búsqueda en el nombre de dominio del socio federado realiza una coincidencia de sufijo. Por ejemplo, si escribe <STRONG>contoso.com</STRONG>, la búsqueda también devolverá el dominio <STRONG>it.contoso.com</STRONG>.<BR>Un dominio del socio federado no puede bloquearse y permitirse al mismo tiempo. Lync Server 2013 impide que esto suceda, por lo que no es necesario sincronizar las listas.

        
        </div>
    
      - Faculta En **Comentario**, escriba la información que desea compartir con otros administradores del sistema acerca de esta configuración.

6.  Haga clic en **Confirmar**.

7.  Repita los pasos 4 a 6 para cada socio federado que desee bloquear.

Para habilitar el acceso de usuarios federados, también debe habilitar la compatibilidad con el acceso de usuarios federados de su organización. Para obtener más información, vea [habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

Además, debe configurar y aplicar la Directiva a los usuarios que desee que puedan colaborar con los usuarios federados. Para obtener más información, vea [configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

