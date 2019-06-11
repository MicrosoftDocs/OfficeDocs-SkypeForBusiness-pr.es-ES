---
title: 'Lync Server 2013: Configurar registros de host DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac3bb3c771d99e56e0c584675d77a92d95fdd757
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a>Configurar registros de host DNS para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor o dominio como mínimo como miembro del grupo administradores de dominio o miembro del grupo DnsAdmins.

<div>

## <a name="to-configure-dns-host-a-records"></a>Para configurar registros A de host DNS

1.  En el servidor del sistema de nombres de dominio (DNS), haga clic en **Inicio**, en **herramientas administrativas**y, por último, en **DNS**.

2.  En el árbol de consola de su dominio, expanda **zonas de búsqueda directa**y haga clic con el botón secundario en el dominio en el que se instalará Lync Server 2013.

3.  Haga clic en **nuevo host (A o aaaa)**.

4.  Haga clic en **nombre**, escriba el nombre de host del grupo (el nombre de dominio se supone de la zona en la que está definido el registro y no tiene que especificarse como parte del registro A).

5.  Haga clic en **dirección IP**, escriba la IP virtual (VIP) del equilibrador de carga para el grupo de servidores front-end.
    
    <div>
    

    > [!IMPORTANT]  
    > En las implementaciones que usan un grupo de directores, los registros de host (A) para las direcciones URL simples deben señalar a la dirección VIP del equilibrador de carga de director.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Si implementa solo un servidor Enterprise Edition o director que está conectado a la topología sin un equilibrador de carga, o si implementa un servidor Standard Edition, escriba la dirección IP del servidor Enterprise Edition, servidor Standard Edition o director. Es necesario un equilibrador de carga si implementa más de un servidor Enterprise Edition o Director en un grupo. Los equilibradores de carga no se usan con servidores Standard Edition.

    
    </div>

6.  Haga clic en **Agregar host**y, a continuación, en **Aceptar**.

7.  Para crear un registro A adicional, repita los pasos 4 y 5.

8.  Cuando haya terminado de crear todos los registros A que necesita, haga clic en **listo**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

