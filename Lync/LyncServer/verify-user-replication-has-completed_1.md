---
title: La comprobación de la replicación de usuarios ha finalizado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13f4fbd2e0d0236f9dc404ffa84ab2f0ce385e2a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a>La comprobación de la replicación de usuarios ha finalizado

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

Al ejecutar el cmdlet **Move-CsLegacyUser** , puede experimentar un error debido a que la información del usuario entre los servicios de dominio de Active Directory (AD DS) y las bases de datos de Lync Server 2013 no está sincronizada porque la replicación inicial está incompleta. El tiempo que tarda la finalización satisfactoria de la sincronización inicial del servicio duplicador de usuarios de Lync Server 2013 depende del número de controladores de dominio que se hospeden en el bosque de Active Directory que hospeda el grupo de servidores de Lync Server 2013. El proceso de sincronización inicial del servicio replicador de usuarios de Lync Server 2013 se produce cuando el servidor front-end de Lync Server 2013 se inicia por primera vez. Después, la sincronización se basa en el intervalo del replicador de usuarios. Complete los pasos siguientes para comprobar que la replicación de usuario se ha completado antes de ejecutar el cmdlet **Move-CsLegacyUser** .

<div>

## <a name="to-verify-that-user-replication-has-completed"></a>Para comprobar que la replicación de usuarios se ha completado

1.  En el servidor front-end de Lync Server 2013, haga clic en el menú **Inicio** y, a continuación, haga clic en **Ejecutar**.

2.  Escribe **eventvwr. exe** y haz clic en **Aceptar**.

3.  En el visor de eventos, haga clic en **registros de aplicaciones y servicios** para expandirlo y, a continuación, seleccione Lync Server.

4.  En el panel **acciones** , haga clic en **filtrar registro actual**.

5.  En la lista **orígenes de eventos** , haga clic en replicador de usuarios de **LS**.

6.  En ** \<todos los\> identificadores de evento** , escriba **30024** y haga clic en **Aceptar**.

7.  En la lista eventos filtrados, en la pestaña **General** , busque una entrada que indique que la replicación de usuarios se ha completado correctamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

