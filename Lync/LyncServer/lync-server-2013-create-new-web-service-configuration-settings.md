---
title: 'Lync Server 2013: crear nuevas opciones de configuración de un servicio Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create new Web Service configuration settings
ms:assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182605(v=OCS.15)
ms:contentKeyID: 48185801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79508e99c8bc70e7781e77cd7727be30ebdda58f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-new-web-service-configuration-settings-in-lync-server-2013"></a>Crear nuevas opciones de configuración de servicio Web en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Puede usar la página **servicio Web** para configurar los métodos de autenticación para obtener acceso a los servidores web y servicios web relacionados con Lync Server 2013.

Siga estos pasos para crear una nueva Directiva de servicio Web.

<div>

## <a name="to-create-new-web-service-configuration-settings"></a>Para crear nuevas opciones de configuración de un servicio Web

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Servicio web**.

4.  En la página **servicio Web** , haga clic en **nuevo**y, a continuación, realice una de las siguientes acciones:
    
      - Para configurar el servicio web para un sitio, haga clic en **configuración del sitio**. En **seleccionar un sitio**, haga clic en el sitio al que se aplicará la Directiva de servicio Web y, a continuación, haga clic en **Aceptar**.
    
      - Para configurar el servicio web para un grupo de servidores, haga clic en **configuración del grupo**. En **seleccionar un servicio**, haga clic en el servicio al que se aplicará la Directiva de servicio Web y, a continuación, haga clic en **Aceptar**.

5.  En **nueva configuración de servicio Web**, en **autenticación integrada de Windows**, seleccione **negociar**, **autenticación de Windows integrada**o **ninguno**.

6.  Seleccione uno o más de los siguientes elementos en función de las capacidades de los clientes y compatibilidad de su entorno.
    
      - **Habilitar autenticación PIN** para habilitar la autenticación de clientes a través de números PIN.
    
      - **Habilitar autenticación de certificados**: para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.
    
      - **Habilitar descarga de cadena de certificados** para que los servidores se presenten con un certificado de autenticación, descargue la cadena de certificados para ese certificado.

7.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

