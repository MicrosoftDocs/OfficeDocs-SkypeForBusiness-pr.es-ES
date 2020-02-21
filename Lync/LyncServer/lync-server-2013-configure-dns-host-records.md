---
title: 'Lync Server 2013: configurar registros de host DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c688d09e1aababd384c28c5a79989fc5d93e69b8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204540"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a>Configurar registros de host DNS para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

Para completar correctamente este procedimiento, debe iniciar sesión en el servidor o dominio como mínimo como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.

<div>

## <a name="to-configure-dns-host-a-records"></a>Para configurar los registros de host DNS A

1.  En el servidor del Sistema de nombres de dominio (DNS), haga clic en **Inicio**, **Herramientas administrativas ** y, a continuación, en **DNS**.

2.  En el árbol de la consola del dominio, expanda **zonas de búsqueda directa**y, a continuación, haga clic con el botón secundario en el dominio en el que se instalará Lync Server 2013.

3.  Haga clic en **Host nuevo (A o AAAA)**.

4.  Haga clic en **nombre**, escriba el nombre de host del grupo de servidores (el nombre de dominio se asume de la zona en la que se define el registro y no es necesario introducirlo como parte del registro A).

5.  Haga clic en **dirección IP**, escriba la IP virtual (VIP) del equilibrador de carga para el grupo de servidores front-end.
    
    <div>
    

    > [!IMPORTANT]  
    > En las implementaciones que usan un grupo de directores, los registros de host (A) para las direcciones URL simples deben apuntar a la VIP del equilibrador de carga de director.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Si implementa un solo servidor Enterprise Edition o un director que está conectado a la topología sin un equilibrador de carga, o si implementa un servidor Standard Edition, escriba la dirección IP del servidor Enterprise Edition, el servidor Standard Edition o el director. Se requiere un equilibrador de carga si se implementa más de un servidor Enterprise Edition o Director en un grupo de servidores. Los equilibradores de carga no se usan con los servidores Standard Edition.

    
    </div>

6.  Haga clic en **Agregar host** y, a continuación, haga clic en **Aceptar**.

7.  Para crear un registro A adicional, repita los pasos 4 y 5.

8.  Cuando termine de crear todos los registros A que necesita, haga clic en **listo**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

