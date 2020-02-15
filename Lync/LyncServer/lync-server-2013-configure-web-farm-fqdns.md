---
title: 'Lync Server 2013: configurar FQDN de granja de servidores Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web farm FQDNs
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429722(v=OCS.15)
ms:contentKeyID: 48185481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fedaf9fdc48e067b20a956e8945e43469b967011
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a>Configurar FQDN de granja de servidores web para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-29_

Al definir la configuración del servidor Standard Edition, el grupo de servidores front-end, el director o el grupo de directores en el generador de topologías, se configura un nombre de dominio completo (FQDN) de servicios web externos. Durante el proceso de inicio de sesión de un cliente hospedado en el servidor Standard Edition o el grupo de servidores front-end, los FQDN de servicios web configurados se envían por medio del aprovisionamiento en banda. Si necesita agregar o cambiar la dirección URL de los servicios web externos, use el generador de topologías para configurar o volver a configurar la configuración de los servicios Web mediante el procedimiento descrito en este tema.

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a>Para configurar el FQDN de un grupo de servidores externo para servicios web

1.  Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.

2.  En el generador de topologías, en el árbol de la consola, en **servidores front-end Standard Edition**, **servidores front-end Enterprise Edition**y **directores**, haga clic con el botón secundario en el nombre del grupo que tiene que editar y, a continuación, haga clic en **Editar propiedades**.

3.  En la sección **Servicios web**, agregue o edite el **FQDN de servicios web externos**.

4.  Revise y ajuste los  **Puertos de escucha** para HTTP y HTTPS. Los valores predeterminados serán:
    
      - **Puertos de escucha:** HTTP 8080, HTTPS 4443
    
      - **Puertos de escucha:** HTTP 80, HTTPS 443
    
    Donde los **Puertos de escucha** son los puertos que los servicios web externos configurarán para recibir solicitudes desde el proxy inverso y los **Puertos publicados** son los puertos que publica externamente el proxy inverso y se comunican a los clientes durante el aprovisionamiento en banda.

5.  Cuando haya completado las adiciones y actualizaciones, haga clic en **Aceptar** para continuar.

6.  Haga clic con el botón secundario en **Lync Server 2013**y, a continuación, haga clic en **publicar**.
    
    <div>
    

    > [!IMPORTANT]  
    > Una vez finalizada la publicación correctamente, puede aparecer un vínculo que le informa de que hay pasos adicionales que deban llevarse a cabo. Si se hace clic en el vínculo, se abre una lista de servidores afectados por los cambios realizados en Topology Builder que requerirán volver a ejecutar el Asistente para la implementación de Lync Server en cada servidor de la lista para actualizar la configuración de los componentes agregados, quitados o modificados.

    
    </div>

7.  Repita estos pasos para cada servidor Standard Edition, grupo de servidores front-end, director o grupo de directores de la organización.

</div>

</div>

<span> </span>

</div>

</div>

</div>

