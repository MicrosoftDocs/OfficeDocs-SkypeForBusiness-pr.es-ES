---
title: 'Lync Server 2013: Probar el director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f889d548ddc9b177113aa3e395ac181095de8008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-director-in-lync-server-2013"></a>Probar el director en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

En este momento, tiene un grupo de directores o directores configurado, pero las entradas SRV del sistema de nombres de dominio (DNS) aún apuntan a los clientes para iniciar sesión usando un grupo de servidores o un servidor Standard Edition. Antes de cambiar el registro DNS para que los clientes de Lync 2013 inicien sesión automáticamente con el director, pruebe un cliente de forma manual al Director.

<div>

## <a name="to-test-the-deployment"></a>Para probar la implementación

1.  Inicie sesión en el equipo en el que tiene instalado el panel de control de Lync Server con una cuenta de dominio que forme parte del grupo **CSAdministrator** .

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En el panel de navegación, haga clic en **topología**y, en la columna **Estado** , confirme que hay un servidor verde con una flecha (es decir, ![icono del servidor con](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "")una flecha verde) para su director o grupo de directores.

4.  Conecte dos equipos cliente que tengan el cliente de Lync Server 2013 instalado e inicie sesión con una cuenta de usuario diferente habilitada para Lync Server 2013 en cada equipo.

5.  En uno de los equipos cliente, haga clic en el menú **Opciones** , seleccione el grupo configuración **personal** , haga clic en opciones **avanzadas**, haga clic en **configuración manual**y, a continuación, establezca el **nombre del servidor interno o la dirección IP** en el nombre completo nombre de dominio (FQDN) del nuevo grupo de directores o de directores.

6.  Inicie sesión en ambos clientes y compruebe que el cliente que inicia sesión con el director puede iniciar sesión correctamente, ver el estado de presencia del otro usuario y que pueden intercambiar mensajes instantáneos.

</div>

</div>

<span> </span>

</div>

</div>

</div>

