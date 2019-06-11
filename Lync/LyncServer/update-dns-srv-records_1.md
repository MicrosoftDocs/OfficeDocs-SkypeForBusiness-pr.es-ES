---
title: Actualizar registros SRV de DNS
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Update DNS SRV records
ms:assetid: a29149aa-30cc-4a59-af98-fb95c2385cce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688161(v=OCS.15)
ms:contentKeyID: 49733765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97ff3eed81a90960444b260bd0ca5b9c4c67022e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a>Actualizar registros SRV de DNS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-29_

Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor o dominio como miembro del grupo administradores de dominio o miembro del grupo DnsAdmins.

En este tema se describe cómo actualizar los registros del sistema de nombres de dominio (DNS) después de migrar a Lync Server 2013. Después de que todos los usuarios se hayan movido a Lync Server 2013, pero antes de que el director o grupo heredado de Office Communications Server 2007 R2 se haya decomisado, debe actualizar los registros SRV de DNS en el DNS interno para cada dominio SIP. En este procedimiento se supone que su DNS interno tiene zonas para sus dominios de usuario SIP.

**Para configurar un registro SRV de DNS**

1.  En el servidor DNS, haga clic en **Inicio**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **DNS**.

2.  En el árbol de consola de su dominio SIP, expanda **zonas de búsqueda directa**, expanda el dominio SIP en el que está instalado Lync Server 2013 ** \_** y vaya a la configuración de TCP.

3.  En el panel derecho, haga clic con el botón derecho en ** \_sipinternaltls** y seleccione **propiedades**.

4.  En el **hospedaje que ofrece este servicio**, actualice el FQDN del host para que apunte al grupo de servidores de Lync Server 2013.

5.  Haga clic en **Aceptar**.

**Para comprobar que se puede resolver el FQDN del grupo de servidores front-end o del servidor Standard Edition**

1.  Inicie sesión en un equipo cliente del dominio.

2.  Haga clic en  **Inicio ** y en  **Ejecutar **.

3.  En el cuadro **abrir** , escriba **cmd**y haga clic en **Aceptar**.

4.  En el símbolo del sistema, escriba **nslookup** \<FQDN del grupo\> de servidores Front \<-end o FQDN del servidor\>Standard Edition y, a continuación, presione Entrar.

5.  Compruebe que recibe una respuesta que se resuelve en la dirección IP adecuada para el nombre de dominio completo (FQDN).

</div>

<span> </span>

</div>

</div>

</div>

