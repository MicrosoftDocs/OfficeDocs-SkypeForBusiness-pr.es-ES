---
title: La comprobación de la replicación de usuarios ha finalizado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e96d3231fbbfe9ce9062e948e6b60de6521720e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849827"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a>La comprobación de la replicación de usuarios ha finalizado

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-17_

Al ejecutar el cmdlet **Move-CsUser** , puede experimentar un error porque la información del usuario entre los servicios de dominio de Active Directory (AD DS) y las bases de datos de Lync Server 2013 no está sincronizada porque la replicación inicial está incompleta. El tiempo que tarda la finalización satisfactoria de la sincronización inicial del servicio duplicador de usuarios de Lync Server 2013 depende del número de controladores de dominio que se hospeden en el bosque de Active Directory que hospeda el grupo de servidores de Lync Server 2013. El proceso de sincronización inicial del servicio replicador de usuarios de Lync Server 2013 se produce cuando el servidor front-end de Lync Server 2013 se inicia por primera vez. Después, la sincronización se basa en el intervalo del replicador de usuarios. Complete los pasos siguientes para comprobar que la replicación de usuario se ha completado antes de ejecutar el cmdlet **Move-CsUser** .

<div>

## <a name="to-verify-user-replication-has-completed"></a>Para comprobar que la replicación de usuario se ha completado

1.  Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.

2.  Haga clic en el menú **Inicio** y, a continuación, en **Ejecutar**.

3.  Escribe **eventvwr. exe** y haz clic en **Aceptar**.

4.  En el visor de eventos, haga clic en **registros de aplicaciones y servicios** para expandirlo y, a continuación, seleccione Lync Server.

5.  En el panel **acciones** , haga clic en **filtrar registro actual**.

6.  En la lista **orígenes de eventos** , haga clic en replicador de usuarios de **LS**.

7.  En ** \<todos los\> identificadores de evento** , escriba **30024** y haga clic en **Aceptar**.

8.  En la lista eventos filtrados, en la pestaña **General** , busque una entrada que indique que la replicación de usuarios se ha completado correctamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

