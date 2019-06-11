---
title: 'Lync Server 2013: Configurar los nombres de dominio completos (FQDN) de la granja de servidores web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure web farm FQDNs
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429722(v=OCS.15)
ms:contentKeyID: 48185481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 517e00baef63e3597c2f5b2b6621e62efb02ca62
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a>Configurar los nombres de dominio completos (FQDN) de la granja de servidores web para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-29_

Al definir la configuración del servidor Standard Edition, el grupo de servidores front-end, el director o el grupo de directores en el generador de topología, se configura un nombre de dominio completo (FQDN) de servicios web externos. Durante el proceso de inicio de sesión de un cliente alojado en el servidor Standard Edition o en el grupo front-end, los FQDN de los servicios web configurados se envían por medio de aprovisionamiento en banda. Si necesita agregar o cambiar la dirección URL de los servicios web externos, use el generador de topología para configurar o volver a configurar la configuración de los servicios Web mediante el procedimiento de este tema.

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a>Para configurar un FQDN de grupo externo para servicios Web

1.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.

2.  En el generador de topología, en el árbol de consola, en **front ends Standard Edition**, **servidores front-end Enterprise Edition**, y **directores**, haga clic con el botón secundario en el nombre del grupo que necesita editar y, a continuación, haga clic en **Editar propiedades**.

3.  En la sección **servicios web** , agregue o edite el **FQDN de servicios web externos**.

4.  Revise y ajuste los **puertos de escucha** para http y https. Los valores predeterminados son los siguientes:
    
      - **Puertos de escucha:** HTTP 8080, HTTPS 4443
    
      - **Puertos publicados:** HTTP 80, HTTPS 443
    
    Donde los **puertos de escucha** son el puerto en el que los servicios web externos se configurarán para recibir solicitudes del proxy inverso, y los **puertos publicados** son los puertos publicados externamente por el proxy inverso y al que se les comunica clientes durante el aprovisionamiento en banda.

5.  Cuando haya completado las adiciones y actualizaciones, haga clic en **Aceptar** para continuar.

6.  Haga clic con el botón secundario en **Lync Server 2013**y, a continuación, haga clic en **publicar**.
    
    <div>
    

    > [!IMPORTANT]  
    > Después de la publicación, se puede presentar un vínculo que le informará de que hay pasos adicionales que es necesario realizar. Si se hace clic en el vínculo, se abre una lista de servidores afectados por los cambios realizados en el generador de topología que requerirán volver a ejecutar el Asistente para la implementación de Lync Server en cada servidor de la lista para actualizar la configuración de los componentes agregados, eliminados o modificados.

    
    </div>

7.  Repita estos pasos para cada servidor Standard Edition, grupo de servidores front-end, director o grupo de directores de la organización.

</div>

</div>

<span> </span>

</div>

</div>

</div>

