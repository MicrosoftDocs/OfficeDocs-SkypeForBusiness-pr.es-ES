---
title: 'Lync Server 2013: configurar un nuevo servidor de aplicaciones de confianza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fc5a982724dd390ff97bf6dd4cad10f25572732
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a>Configurar un nuevo servidor de aplicaciones de confianza en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Una aplicación de confianza es una aplicación basada en el SDK del núcleo de la API administrada de Microsoft Unified Communications (UCMA) 3,0 en el que confía Microsoft Lync Server 2013. Para obtener más información acerca de las aplicaciones de UCMA, consulte "documentación de SDK de comunicaciones [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320)unificadas de la API de Core 3,0" en.

Para obtener información sobre cómo configurar Microsoft Outlook Web Access (OWA) y Lync Server 2013, consulte "configurar la integración de Outlook Web App y Lync Server 2010" en la documentación de Microsoft Exchange Server 2013.

Para publicar, habilitar o deshabilitar correctamente una topología al agregar o quitar un rol de servidor, debe haber iniciado sesión como un usuario que sea miembro de los grupos administradores de dominio y RTCUniversalServerAdmins. También es posible delegar los permisos de administrador apropiados y los derechos para agregar roles de servidor. Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) en la documentación de implementación. Para otros cambios de configuración, solo es necesario pertenecer al grupo RTCUniversalServerAdmins.

<div>

## <a name="to-configure-a-trusted-application-server"></a>Para configurar un servidor de aplicaciones de confianza

1.  Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.

2.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.

3.  Seleccione **Descargar topología de la implementación existente**y, a continuación, haga clic en **Aceptar**.

4.  En el cuadro de diálogo **Guardar topología como** , haga clic en el archivo del generador de topología que desea usar y, a continuación, haga clic en **Guardar**.

5.  En el panel izquierdo, haga clic con el botón secundario en **servidores de aplicaciones de confianza**y luego haga clic en **nuevo grupo de aplicaciones de confianza**.

6.  Escriba el **FQDN del grupo** del grupo de aplicaciones de confianza, seleccione si va a ser un servidor único o de varios servidores y, a continuación, haga clic en **siguiente**.

7.  En la página **seleccionar el próximo salto** , en la lista, seleccione el grupo de servidores front-end de Lync Server 2013.

8.  Haga clic en **Finalizar**.

9.  Seleccione el nodo superior de **Lync Server 2013**y, a continuación, en el menú **acciones** , haga clic en **publicar topología**.
    
    El **grupo de aplicaciones de confianza** se creó correctamente y se asoció con el grupo de servidores front-end correcto.

</div>

</div>

<span> </span>

</div>

</div>

</div>

