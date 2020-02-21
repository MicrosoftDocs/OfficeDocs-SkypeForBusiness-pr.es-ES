---
title: 'Lync Server 2013: probar el director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad5c885e032800e4233aaa58c5238c066a87a1df
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-the-director-in-lync-server-2013"></a>Probar el Director en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

Llegados a este punto, ya tiene configurado un director o un grupo de servidores de director, pero las entradas SRV de su Sistema de nombres de dominio (DNS) continúan obligando a los clientes a iniciar sesión mediante un grupo de servidores o un servidor Standard Edition. Antes de cambiar el registro DNS para que los clientes de Lync 2013 inicien sesión automáticamente mediante el director, pruebe un cliente de forma manual hacia él para dirigirlo al Director.

<div>

## <a name="to-test-the-deployment"></a>Para probar la implementación

1.  Inicie sesión en el equipo donde tenga instalado el panel de control de Lync Server con una cuenta de dominio que forme parte del grupo **CSAdministrator** .

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En el panel de navegación, haga clic en **topología**y, en la columna **Estado** , confirme que haya un servidor verde con una flecha (es decir, un ![icono de servidor con flecha verde](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Icono de servidor con flecha verde")) para su director o grupo de directores.

4.  Conecte dos equipos cliente que tengan el cliente de Lync Server 2013 instalado e inicie sesión con una cuenta de usuario distinta habilitada para Lync Server 2013 en cada equipo.

5.  En uno de los equipos cliente, haga clic en el menú **Opciones**, seleccione el grupo de configuración **Personal**, haga clic en **Avanzada** y, a continuación, en **Configuración manual**. Por último, defina en **Nombre de servidor interno o dirección IP** el nombre de dominio completo (FQDN) del nuevo director o grupo de servidores del director.

6.  Inicie sesión en ambos clientes y compruebe que el cliente que inicie sesión usando el director pueda iniciar sesión correctamente, observe el estado de presencia del otro usuario y si pueden intercambiar mensajes instantáneos.

</div>

</div>

<span> </span>

</div>

</div>

</div>

