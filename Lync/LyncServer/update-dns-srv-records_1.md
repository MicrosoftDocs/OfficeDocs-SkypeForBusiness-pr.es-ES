---
title: Actualizar registros DNS SRV
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: a29149aa-30cc-4a59-af98-fb95c2385cce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688161(v=OCS.15)
ms:contentKeyID: 49733765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed2f97046e7ea82f23e07776ffde60e78dc81e28
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a>Actualizar registros DNS SRV

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-29_

Para completar con éxito este procedimiento, debe iniciar sesión en el servidor o el dominio como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.

En este tema se describe cómo actualizar los registros del sistema de nombres de dominio (DNS) después de migrar a Lync Server 2013. Una vez que todos los usuarios se han movido a Lync Server 2013, pero antes de que el director o grupo de Office Communications Server 2007 R2 haya sido retirado, debe actualizar los registros DNS SRV en el DNS interno para cada dominio SIP. En este procedimiento, se presupone que el DNS interno tiene zonas para los dominios de usuarios SIP.

**Para configurar un registro DNS SRV**

1.  En el servidor DNS, haga clic en **Inicio**, **Herramientas administrativas** y, a continuación, **DNS**.

2.  En el árbol de la consola del dominio SIP, expanda **zonas de búsqueda directa**, expanda el dominio SIP en el que Lync Server 2013 está instalado ** \_** y navegue hasta la configuración TCP.

3.  En el panel derecho, haga clic con el botón secundario en ** \_sipinternaltls** y seleccione **propiedades**.

4.  En **host que ofrece este servicio**, actualice el FQDN de host para que apunte al grupo de servidores de Lync Server 2013.

5.  Haga clic en **Aceptar**.

**Para comprobar que se puede resolver el FQDN del grupo de servidores front-end o del servidor Standard Edition**

1.  Inicie sesión en un equipo cliente en el dominio.

2.  Haga clic en **Inicio** y, a continuación, en **Ejecutar**.

3.  En el cuadro **Abrir**, escriba **cmd** y, a continuación, haga clic en **Aceptar**.

4.  En el símbolo del sistema, escriba **nslookup** \<FQDN del grupo\> de servidores Front \<-end o el FQDN del\>servidor Standard Edition y, a continuación, presione Entrar.

5.  Compruebe que recibe una respuesta que resuelve la dirección IP adecuada para el FQDN.

</div>

<span> </span>

</div>

</div>

</div>

