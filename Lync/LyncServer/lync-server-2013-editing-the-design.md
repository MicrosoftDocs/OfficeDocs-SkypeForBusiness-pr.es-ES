---
title: 'Lync Server 2013: edición del diseño'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the design
ms:assetid: 08f639ba-0e5f-4ae7-9191-c3d96c25b169
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558608(v=OCS.15)
ms:contentKeyID: 51541445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7607fb2f31107e3368fa52167dc5015eb1b71f15
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-design-in-lync-server-2013"></a>Edición del diseño en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Después de completar las preguntas de la entrevista inicial, puede editar el nombre de dominio completo (FQDN) y las direcciones IP del sitio. Para ello, en la página **Topología global**, haga clic con el botón secundario en el sitio que desea editar.

La herramienta de planeación muestra la topología del sitio seleccionado. En la parte inferior de la página del sitio hay cuatro pestañas:

![Topología de sitio de la herramienta de planeación](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Topología de sitio de la herramienta de planeación")

  - Topología del sitio: La página que se muestra actualmente con información general visual de la topología recomendada.

  - Diagrama de red perimetral: la página de diagrama de red perimetral es donde el diseñador realiza la mayor parte del trabajo en la herramienta de planeación. El diagrama muestra la configuración de red para una topología de Lync Server 2013 recomendada, con entradas editables para direcciones IP y FQDN para servidores, grupo y equilibradores de carga de hardware y de sistema de nombres de dominio (DNS).

  - Informe de administración perimetral: El informe de administración perimetral contiene un total de cuatro informes:
    
    ![Página Informe de administración perimetral](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Página Informe de administración perimetral")  
    
      - Informe de resumen: Un informe general de las opciones de configuración de la red perimetral. Si edita los valores de la página de **Diagrama de red perimetral** con los valores de la topología TCP/IP y FQDN de que se usarán en la implementación real, esas direcciones y nombres se representarán aquí. De lo contrario, aparecerá el texto predeterminado.
    
      - Informe de certificado: En el informe de certificado se enumerará el nombre de sujeto y los nombres alternativos de sujeto para los certificados que la topología requiere.
    
      - Informe de firewall: En el informe de firewall se indicará la información necesaria para configurar firewalls perimetrales en la infraestructura. Esto incluye las direcciones IP (los valores predeterminados o modificados), el rol del servidor, el puerto y la IP de origen, el puerto y la IP de destino, el protocolo de transporte, el protocolo de la aplicación y las notas relevantes.
    
      - Informe de DNS: el informe de DNS muestra la información relevante para las entradas de DNS que debe crear. También se incluye el tipo de registro, el FQDN, la dirección IP y los comentarios necesarios para que obtener un funcionamiento correcto.

  - Resumen del sitio: el resumen del sitio presenta una descripción general de las selecciones realizadas al responder a las preguntas de la entrevista inicial o al rellenar los valores en **diseñar sitios**. También se presenta información sobre la capacidad.
    
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

