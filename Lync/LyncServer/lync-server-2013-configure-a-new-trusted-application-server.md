---
title: 'Lync Server 2013: configurar un nuevo servidor de aplicaciones de confianza'
description: 'Lync Server 2013: configurar un nuevo servidor de aplicaciones de confianza.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3cc13c747c5755297b01ae36f27f06d19591acc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552126"
---
# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a>Configurar un nuevo servidor de aplicaciones de confianza en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Una aplicación de confianza es una aplicación basada en el SDK de Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK en el que confía Microsoft Lync Server 2013. Para obtener más información acerca de las aplicaciones de UCMA, consulte la documentación de Unified Communications Managed API 3,0 Core SDK en [https://go.microsoft.com/fwlink/p/?linkId=210320](https://go.microsoft.com/fwlink/p/?linkid=210320) .

Para obtener información acerca de la configuración de Microsoft Outlook Web Access (OWA) y Lync Server 2013, consulte "configure Outlook Web App and Lync Server 2010 Integration" en la documentación de Microsoft Exchange Server 2013.

Para publicar, habilitar o deshabilitar correctamente una topología al agregar o quitar un rol de servidor, debe haber iniciado sesión como usuario miembro de los grupos Administradores del dominio y RTCUniversalServerAdmins. También es posible delegar los permisos y derechos de administrador adecuados para agregar roles de servidor. Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) en la documentación sobre implementación. Para realizar otros cambios de configuración, solo se requiere pertenecer al grupo RTCUniversalServerAdmins.

<div>

## <a name="to-configure-a-trusted-application-server"></a>Para configurar un servidor de aplicaciones de confianza

1.  Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.

2.  Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.

3.  Seleccione **Descargar topología de la implementación existente** y haga clic en **Aceptar**.

4.  En el cuadro de diálogo **Guardar topología como** , haga clic en el archivo del generador de topologías que desee usar y, a continuación, haga clic en **Guardar**.

5.  En el panel izquierdo, haga clic con el botón secundario en **servidores de aplicaciones de confianza**y haga clic en **nuevo grupo de aplicaciones de confianza**.

6.  Escriba el**** FQDN del grupo de servidores del grupo de aplicaciones de confianza, seleccione si va a ser un servidor único o varios servidores y haga clic en **Siguiente**.

7.  En la página **seleccionar el próximo salto** , en la lista, seleccione el grupo de servidores front-end 2013 de Lync Server.

8.  Haga clic en **Finalizar**.

9.  Seleccione el nodo superior **Lync Server 2013**y, a continuación, en el menú **acciones** , haga clic en **publicar topología**.
    
    El **grupo de aplicaciones de confianza** debe haberse creado correctamente y asociado con el grupo de servidores front-end correcto.

</div>

</div>

<span> </span>

</div>

</div>

</div>

