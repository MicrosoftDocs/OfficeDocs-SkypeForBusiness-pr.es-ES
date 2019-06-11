---
title: 'Lync Server 2013: Comprobar el servidor Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test the Standard Edition server
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412890(v=OCS.15)
ms:contentKeyID: 48185220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a960451ebdd1e6e8728bf3b6c7df6e267c49c3f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-standard-edition-server-in-lync-server-2013"></a>Comprobar el servidor Standard Edition en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

En el procedimiento siguiente se describe cómo probar la implementación de un servidor Standard Edition.

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a>Para probar la implementación de un servidor Standard Edition

1.  Use equipos y usuarios de Active Directory para agregar el objeto de usuario de Active Directory de la función Administrador de la implementación de Lync Server 2013 (en la que está instalado el panel de control de Lync Server) en el grupo **CSAdministrator** .

2.  Si actualmente el objeto de usuario ha iniciado sesión, cierre sesión y, luego, vuelva a iniciarla para registrar la nueva asignación de grupo.
    
    <div>
    

    > [!NOTE]  
    > La cuenta de usuario no puede ser el administrador local del servidor que ejecuta Lync Server 2013, Standard Edition. Si no agrega los usuarios y grupos adecuados al grupo CsAdministors, recibirá un error al abrir el panel de control de Lync Server 2013, que indica que "no autorizado: acceso denegado debido a un error de autorización de control de acceso basado en roles (RBAC)."

    
    </div>

3.  Use la cuenta administrativa para iniciar sesión en el equipo en el que está instalado el panel de control de Lync Server.

4.  Inicie el panel de control de Lync Server y proporcione credenciales, si se le solicita. El panel de control de Lync Server 2013 muestra información de implementación.

5.  En la barra de navegación izquierda, haga clic en **topología**y, a continuación, confirme que el estado del servicio es un icono de equipo con una flecha verde y hay una marca de verificación verde junto a cada rol de servidor de Lync Server que se ha implementado y se ha puesto en conexión.

6.  En la barra de navegación izquierda, haga clic en **usuarios**y, a continuación, habilite los dos usuarios para Lync Server 2013.

7.  Iniciar sesión de un usuario en un equipo unido al dominio y el otro usuario en otro equipo del dominio.

8.  Instale Lync Server 2013 en cada uno de los dos equipos cliente y, a continuación, compruebe que ambos usuarios pueden iniciar sesión en Lync Server 2013 y pueden enviar mensajes instantáneos entre sí.

</div>

<div>

## <a name="see-also"></a>Vea también


[Implementación de clientes y dispositivos en Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

