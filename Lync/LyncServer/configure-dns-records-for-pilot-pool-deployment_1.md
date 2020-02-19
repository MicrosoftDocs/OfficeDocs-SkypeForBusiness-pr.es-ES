---
title: Configurar registros DNS para la implementación del grupo piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: 5c7a6e10-e1e9-4479-9bf9-d4a3e2e09ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688072(v=OCS.15)
ms:contentKeyID: 49733666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbc77ddf3b0bb1d58eadc43424e638e4c59608e1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136124"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Configurar registros DNS para la implementación del grupo piloto

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-24_

Antes de implementar el grupo piloto de Lync Server 2013, debe actualizar las entradas de host DNS A para el grupo piloto. Para completar correctamente este procedimiento, debe iniciar sesión en el servidor o dominio como mínimo como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.

**Para configurar los registros de host DNS A**

1.  En el servidor del Sistema de nombres de dominio (DNS), haga clic en **Inicio**, **Herramientas administrativas ** y, a continuación, en **DNS**.

2.  En el árbol de la consola del dominio, expanda **zonas de búsqueda directa**y, a continuación, haga clic con el botón secundario en el dominio en el que se instalará Lync Server 2013.

3.  Haga clic en **Host nuevo (A o AAAA)**.

4.  Haga clic en **nombre**, escriba el nombre de host del grupo de servidores (el nombre de dominio se asume de la zona en la que se define el registro y no es necesario introducirlo como parte del registro A).

5.  Haga clic en **dirección IP**, escriba la dirección IP del grupo de servidores front-end.

6.  Haga clic en **Agregar host** y, a continuación, haga clic en **Aceptar**.

7.  Cuando haya terminado, haga clic en **Listo**.

</div>

<span> </span>

</div>

</div>

</div>

