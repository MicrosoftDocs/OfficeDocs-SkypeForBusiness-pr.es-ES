---
title: 'Lync Server 2013: modificar la configuración de registrador existente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify existing Registrar configuration settings
ms:assetid: a8931511-3e66-49ed-a3ec-03bcd61ce1f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182566(v=OCS.15)
ms:contentKeyID: 48185095
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42629c027157c33bc9431d04d493019e4907d87b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-existing-registrar-configuration-settings-in-lync-server-2013"></a>Modificar las opciones de configuración de registrador existentes en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Puede usar el registrador para configurar los protocolos de autenticación del servidor proxy. Para obtener información sobre los protocolos disponibles, consulte [crear opciones de configuración de registrar en Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).

<div>


> [!NOTE]  
> Se recomienda habilitar Kerberos y NTLM cuando un servidor admita la autenticación para los clientes remotos y de empresa. El servidor perimetral y los servidores internos se comunican para garantizar que solamente se ofrezca la autenticación NTLM a clientes remotos. Si solamente se habilita Kerberos en estos servidores, no podrán autenticar usuarios remotos. Si los usuarios de empresa también se autentican frente al servidor, se usa Kerberos.



</div>

Siga los pasos a continuación para modificar un registrador existente.

<div>

## <a name="to-modify-existing-registrar-configuration-settings"></a>Para modificar las opciones de configuración de un registrador existente

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Registrador**.

4.  En la página **Registrador**, haga clic en un servicio, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.

5.  En **Editar configuración de registrador**, seleccione uno o más de los siguientes elementos en función de las capacidades de los clientes y compatibilidad de su entorno:
    
      - **Habilitar autenticación Kerberos** para que los servidores del grupo emitan desafíos mediante la autenticación Kerberos.
    
      - **Habilitar autenticación NTLM** para que los servidores del grupo emitan desafíos mediante la autenticación NTLM.
    
      - **Habilitar autenticación de certificados** para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.

6.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

