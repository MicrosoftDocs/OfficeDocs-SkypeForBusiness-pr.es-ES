---
title: Comprobar que la replicación de usuarios se ha completado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b526bd5dc6c451d8e8bd9998043d20a7c185f6b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a>Comprobar que la replicación de usuarios se ha completado

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

Cuando se ejecuta el cmdlet **Move-CsLegacyUser** , puede experimentar un error debido a la información de usuario entre los servicios de dominio de Active Directory (AD DS) y las bases de datos de Lync Server 2013 que no están sincronizadas porque la replicación inicial está incompleta. El tiempo que tarda la finalización correcta de la sincronización inicial del servicio replicador de usuarios de Lync Server 2013 depende del número de controladores de dominio que se hospedan en el bosque de Active Directory que hospeda el grupo de servidores de Lync Server 2013. El proceso de sincronización inicial del servicio replicador de usuarios de Lync Server 2013 se produce cuando el servidor front-end de Lync Server 2013 se inicia por primera vez. Tras ello, la sincronización se basa en el intervalo del replicador de usuarios. Complete los siguientes pasos para comprobar que la replicación de usuarios se ha completado antes de ejecutar el cmdlet **Move-CsLegacyUser**.

<div>

## <a name="to-verify-that-user-replication-has-completed"></a>Para comprobar que la replicación de usuarios se ha completado

1.  En el servidor front-end de Lync Server 2013, haga clic en el menú **Inicio** y, a continuación, haga clic en **Ejecutar**.

2.  Escriba **eventvwr.exe** y, a continuación, haga clic en **Aceptar**.

3.  En el Visor de eventos, haga clic en **Registros de aplicaciones y servicios** para expandirlo y, a continuación, seleccione Lync Server.

4.  En el panel **Acciones**, haga clic en **Filtrar registro actual**.

5.  En la lista **Orígenes del evento**, haga clic en **LS User Replicator**.

6.  En ** \<todos los identificadores\> de evento** , escriba **30024** y haga clic en **Aceptar**.

7.  En la lista de eventos filtrados, en la pestaña **General**, busque una entrada que indique que la replicación de usuarios finalizó correctamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

