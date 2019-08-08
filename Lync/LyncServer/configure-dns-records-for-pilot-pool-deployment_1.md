---
title: Configurar registros DNS para una implementación de grupo de servidores piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: 5c7a6e10-e1e9-4479-9bf9-d4a3e2e09ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688072(v=OCS.15)
ms:contentKeyID: 49733666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18c9bc007eda604ce4894497db4a6ef334315d28
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Configurar registros DNS para una implementación de grupo de servidores piloto

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-24_

Antes de implementar el grupo piloto de Lync Server 2013, debe actualizar las entradas de host DNS A para la agrupación piloto. Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor o dominio como mínimo como miembro del grupo administradores de dominio o miembro del grupo DnsAdmins.

**Para configurar registros A de host DNS**

1.  En el servidor del sistema de nombres de dominio (DNS), haga clic en **Inicio**, en **herramientas administrativas**y, por último, en **DNS**.

2.  En el árbol de consola de su dominio, expanda **zonas de búsqueda directa**y haga clic con el botón secundario en el dominio en el que se instalará Lync Server 2013.

3.  Haga clic en **nuevo host (A o aaaa)**.

4.  Haga clic en **nombre**, escriba el nombre de host del grupo (el nombre de dominio se supone de la zona en la que está definido el registro y no tiene que especificarse como parte del registro A).

5.  Haga clic en **dirección IP**y escriba la dirección IP del grupo de servidores front-end.

6.  Haga clic en **Agregar host**y, a continuación, en **Aceptar**.

7.  Cuando haya terminado, haga clic en **listo**.

</div>

<span> </span>

</div>

</div>

</div>

