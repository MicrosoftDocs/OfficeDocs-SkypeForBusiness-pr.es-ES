---
title: Configurar registros DNS para la implementación del grupo piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: eb421bad-4bf1-4837-a077-7795094692d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721921(v=OCS.15)
ms:contentKeyID: 49733855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d3b1f4b507887bc046cefddae9c924f0de1916b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "41999125"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Configurar registros DNS para la implementación del grupo piloto

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-29_

Antes de implementar el grupo piloto de Lync Server 2013, debe actualizar las entradas de host DNS A para el grupo piloto. Para completar con éxito este procedimiento, debe iniciar sesión en el servidor o el dominio como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.

**Para configurar los registros de host DNS A**

1.  En el servidor del Sistema de nombres de dominio (DNS), haga clic en **Inicio**, **Herramientas administrativas ** y, a continuación, en **DNS**.

2.  En el árbol de la consola del dominio, expanda **zonas de búsqueda directa**y, a continuación, haga clic con el botón secundario en el dominio en el que se instalará Lync Server 2013.

3.  Haga clic en **Host nuevo (A o AAAA)**.

4.  Haga clic en **nombre**, escriba el nombre de host para el grupo de servidores de Lync Server 2013 (el nombre de dominio se asume de la zona en la que está definido el registro y no es necesario especificarlo como parte del registro A).

5.  Haga clic en **dirección IP**, escriba la dirección IP del grupo de servidores front-end.

6.  Haga clic en **Agregar host** y, a continuación, haga clic en **Aceptar**.

7.  Cuando haya terminado, haga clic en **Listo**.

</div>

<span> </span>

</div>

</div>

</div>

