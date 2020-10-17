---
title: 'Lync Server 2013: tecnologías de virtualización admitidas y limitaciones conocidas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61d2d884566c21933e00dd3897f5fe394b4a2624
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523937"
---
# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a>Tecnologías de virtualización admitidas y limitaciones conocidas en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2017-02-06_

El complemento de VDI de Lync permite llamadas de audio y vídeo para tecnologías de virtualización compatibles. Esto amplía la funcionalidad que se describe en Microsoft Lync Server 2010 en las notas del producto [de virtualización de clientes en Microsoft lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) . De acuerdo con las regulaciones telefónicas estándar, también se incluye compatibilidad con E911. En las siguientes secciones se describen las tecnologías de virtualización que son compatibles con el complemento VDI de Lync y las limitaciones de características conocidas.

<div>

## <a name="support-for-virtualization-technologies"></a>Compatibilidad con tecnologías de virtualización

El complemento de VDI de Lync admite la comunicación remota de escritorio completa en el escenario de escritorio virtual personal, pero no en el escenario de sesión de escritorio remoto. Estos escenarios se pueden describir de la siguiente manera:

  - Se **admite: escritorios virtuales personalizados o infraestructura de escritorio virtual (VDI).**     En este escenario, cada usuario inicia sesión en un escritorio virtual personalizable y puede guardar archivos en el escritorio que se conservan entre sesiones. Los servicios de escritorio remoto de Microsoft, la vista del horizonte de VMware y Citrix XenDesktop son implementaciones que se han probado para su uso con Lync. Para obtener información sobre entornos VDI específicos del proveedor y hardware de cliente que han sido probados por Microsoft, consulte [infraestructura apta para Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).

  - **No admitido: sesiones de escritorio remoto.**     En este escenario, cada usuario inicia sesión en una sesión de escritorio virtual genérica que no se puede personalizar. Las implementaciones de ejemplo incluyen sesiones de escritorio remoto de Microsoft (RDSH) y Citrix XenApp junto con el receptor Citrix.

El complemento de VDI de Lync no admite otras tecnologías de virtualización, como la virtualización de aplicaciones, que permite el uso de una aplicación sin necesidad de instalar la aplicación completa de forma local. Las implementaciones de ejemplo incluyen Citrix XenApp y Microsoft Application Virtualization (App-V). No se admiten la transmisión por secuencias de aplicaciones, la comunicación remota de aplicaciones y los modos mixtos de virtualización (por ejemplo, el acceso remoto de aplicaciones en el entorno remoto de escritorio completo).

Para permitir la extensibilidad, el complemento de VDI de Lync se diseñó para usar API independientes de la plataforma denominadas canales virtuales dinámicos (DVC). Para escenarios que no son compatibles de forma explícita con Lync, consulte las instrucciones de compatibilidad del proveedor de la solución de VDI.

</div>

<div>

## <a name="known-feature-limitations"></a>Limitaciones de las características conocidas

A continuación se indican las limitaciones conocidas al usar Lync 2013 en un entorno de VDI:

  - La delegación de llamadas y las características de anonymization del agente de grupo de respuesta tienen compatibilidad limitada.

  - No se admiten estas características:
    
      - Las páginas de ajuste del dispositivo de audio y de vídeo integrados.
    
      - Vídeo de varias vistas.
    
      - La grabación de las conversaciones.
    
      - Servicios de escritorio remoto (RDS).
    
      - Unirse a reuniones de forma anónima (es decir, unirse a reuniones de Lync hospedadas por una organización que no se federa con la organización).
    
      - Usar el complemento de VDI de Lync junto con un dispositivo de Lync Phone Edition.
    
      - La continuación de llamadas en caso de una interrupción de la red.
    
      - Tonos personalizados y características de música en espera.

  - El complemento de VDI para Lync no es compatible con un entorno de Microsoft 365 o Office 365.

</div>

</div>

<span> </span>

</div>

</div>

</div>

