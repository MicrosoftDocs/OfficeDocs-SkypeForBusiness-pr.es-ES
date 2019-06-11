---
title: 'Lync Server 2013: Edición del diseño'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Editing the design
ms:assetid: 08f639ba-0e5f-4ae7-9191-c3d96c25b169
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558608(v=OCS.15)
ms:contentKeyID: 51541445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 601c313231a26341c3c4cf8a4897d11872dec9a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-design-in-lync-server-2013"></a>Edición del diseño en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Una vez completadas las preguntas iniciales de la entrevista, podrá editar las direcciones IP y el nombre de dominio completo (FQDN) del sitio. Para ello, en la página **Topología global**, haga doble clic en el sitio que desea editar.

La herramienta de planeación muestra la topología del sitio seleccionado. En la parte inferior de la página del sitio hay cuatro pestañas:

![Topología de sitio] de la herramienta de planificación (images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Topología de sitio") de la herramienta de planificación

  - Topología del sitio: la página que se muestra actualmente con información general visual de la topología recomendada.

  - Diagrama de red perimetral: la página de diagrama de red perimetral es el lugar donde el diseñador realiza la mayor parte del trabajo en la herramienta de planeación. El diagrama muestra la configuración de red para una topología recomendada de Lync Server 2013, con entradas editables para direcciones IP y FQDN para servidores, grupos y equilibradores de carga de hardware y de sistema de nombres de dominio (DNS).

  - Informe de administración de la red perimetral: el informe de administración perimetral contiene un total de cuatro informes:
    
    ![Página Informe de administración de Edge] (images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Página Informe de administración de Edge")  
    
      - Informe de resumen: un informe general de los valores de configuración de la red perimetral. Si modifica los valores de la página **Diagrama de red perimetral** por los valores de TCP/IP y FQDN de la topología que se usarán en la implementación real, esas direcciones y nombres se representarán aquí. De lo contrario, se mostrará el texto predeterminado.
    
      - Informe de certificados: en el informe de certificado se enumerará el nombre de sujeto y los nombres alternativos de sujeto para los certificados que la topología requiere.
    
      - Informe de firewall: en el informe de firewall se indicará la información necesaria para configurar firewalls perimetrales en la infraestructura. Esto incluye las direcciones IP (ya sea los valores predeterminados o los modificados), el rol de servidor, el puerto y la IP de origen, el puerto y la IP de destino, el protocolo de transporte, el protocolo de aplicación y las notas relevantes.
    
      - Informe de DNS: en el informe de DNS se proporciona información relevante para las entradas DNS que deberá crear. También se incluye el tipo de registro, el FQDN, la dirección IP y los comentarios necesarios para obtener un funcionamiento correcto.

  - Resumen del sitio: el resumen del sitio presenta información general sobre las selecciones que ha realizado, ya sea respondiendo a las preguntas de la entrevista inicial o rellenando los valores en **Diseñar sitios**. También se muestra información sobre la capacidad.
    
    <div>
    

    > [!NOTE]  
    > La información de la página Resumen del sitio está personalizada para cada diseño y puede que no contenga todas las secciones o toda la información que se indica aquí.

    
    </div>

<div>

## <a name="see-also"></a>Vea también


[Editar el diagrama de configuración de red en Lync Server 2013](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

