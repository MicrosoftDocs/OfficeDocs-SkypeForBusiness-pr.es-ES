---
title: Comprobar que la replicación de usuarios se ha completado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96e8df3cb77e6b53596ae17e15fed6b05243a99a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a>Comprobar que la replicación de usuarios se ha completado

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-17_

Cuando se ejecuta el cmdlet **Move-CsUser** , puede experimentar un error porque la información de usuario entre los servicios de dominio de Active Directory (AD DS) y las bases de datos de Lync Server 2013 no está sincronizada porque la replicación inicial está incompleta. El tiempo que tarda la finalización correcta de la sincronización inicial del servicio replicador de usuarios de Lync Server 2013 depende del número de controladores de dominio que se hospedan en el bosque de Active Directory que hospeda el grupo de servidores de Lync Server 2013. El proceso de sincronización inicial del servicio replicador de usuarios de Lync Server 2013 se produce cuando el servidor front-end de Lync Server 2013 se inicia por primera vez. Posteriormente, la sincronización se basa en el intervalo del User Replicator. Realice los siguientes pasos para verificar que se haya completado la replicación de usuario antes de ejecutar el cmdlet **Move-CsUser**.

<div>

## <a name="to-verify-user-replication-has-completed"></a>Para comprobar que la replicación de usuarios ha finalizado

1.  Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.

2.  Haga clic en el menú **Inicio** y, a continuación, haga clic en **Ejecutar**.

3.  Escriba **eventvwr.exe** y, a continuación, haga clic en **Aceptar**.

4.  En el Visor de eventos, haga clic en **Registros de aplicaciones y servicios** para expandirlo y, a continuación, seleccione Lync Server.

5.  En el panel **Acciones**, haga clic en **Filtrar registro actual**.

6.  En la lista **Orígenes del evento**, haga clic en **LS User Replicator**.

7.  En ** \<todos los identificadores\> de evento** , escriba **30024** y haga clic en **Aceptar**.

8.  En la lista de eventos filtrados, en la pestaña **General**, busque una entrada que indique que la replicación de usuarios finalizó correctamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

