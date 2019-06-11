---
title: 'Lync Server 2013: crear nuevos parámetros de configuración del servicio Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create new Web Service configuration settings
ms:assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182605(v=OCS.15)
ms:contentKeyID: 48185801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86105e4dbf6b624f87844a68ebe5fca6bba02247
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835824"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-new-web-service-configuration-settings-in-lync-server-2013"></a>Crear nuevos parámetros de configuración de servicio Web en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Puede usar la página **servicio Web** para configurar los métodos de autenticación para obtener acceso a los servidores web y servicios web relacionados con Lync Server 2013.

Siga estos pasos para crear una nueva directiva de servicios web.

<div>

## <a name="to-create-new-web-service-configuration-settings"></a>Para crear opciones de configuración nuevas para un servicio web

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Seguridad**y, a continuación, en **Servicio web**.

4.  En la página **Servicio web**, haga clic en **Nuevo** y, a continuación, realice una de las siguientes acciones:
    
      - Para configurar el servicio web para un sitio, haga clic en **Configuración del sitio**. En **Seleccionar un sitio**, haga clic en el sitio al que se aplicará la directiva de servicios web y, a continuación, haga clic en **Aceptar**.
    
      - Para configurar el servicio web para un grupo de servidores, haga clic en **Configuración del grupo de servidores**. En **Seleccionar un servicio**, haga clic en el servicio al que se aplicará la directiva de servicios web y, a continuación, haga clic en **Aceptar**.

5.  En **Nueva configuración de servicio web**, en **Autenticación de Windows**, seleccione **Negociar**, **Autenticación de Windows Integrada** o **Ninguna**.

6.  Seleccione uno o más de los siguientes elementos en función de las capacidades de los clientes y compatibilidad de su entorno.
    
      - **Habilitar autenticación PIN** para habilitar la autenticación de clientes a través de números PIN.
    
      - **Habilitar autenticación de certificados** para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.
    
      - **Habilitar descarga de cadena de certificados** para que los servidores a los que se presente un certificado de autenticación descarguen la cadena de certificados para ese certificado.

7.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

