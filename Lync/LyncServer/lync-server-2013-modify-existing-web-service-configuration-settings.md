---
title: 'Lync Server 2013: modificar la configuración de un servicio web existente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Web Service configuration settings
ms:assetid: bd9c7aa5-d31c-4fab-b31d-8baae26b1296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182580(v=OCS.15)
ms:contentKeyID: 48185272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11bd7f4629d4a3cf0f356a47760810e380af7deb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-existing-web-service-configuration-settings-in-lync-server-2013"></a>Modificar las opciones de configuración de un servicio web existente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Puede usar la página **servicio Web** para configurar los métodos de autenticación para obtener acceso a los servidores web y servicios web relacionados con Lync Server 2013.

Siga estos pasos para modificar una directiva de servicio web existente.

<div>

## <a name="to-modify-existing-web-service-configuration-settings"></a>Para modificar opciones de configuración de un servicio web existente

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Seguridad**y, a continuación, en **Servicio web**.

4.  En la página **Servicio web**, haga clic en una configuración, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.

5.  En **Editar configuración de servicio web**, en **Autenticación de Windows integrada**, seleccione **Negociar**, **NTLM** o **Ninguna**.

6.  Seleccione uno o más de los siguientes elementos en función de las capacidades de los clientes y compatibilidad de su entorno.
    
      - **Habilitar autenticación PIN** para habilitar la autenticación de clientes a través de números PIN.
    
      - **Habilitar autenticación de certificados** para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.
    
      - **Habilitar descarga de cadena de certificados** para que los servidores a los que se presente un certificado de autenticación descarguen la cadena de certificados para ese certificado.

7.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Vea también


[Configuración de la autenticación en el panel de control de Lync Server 2013](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

