---
title: 'Lync Server 2013: Tecnologías de virtualización admitidas y limitaciones comunes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b5c99151be45f70d1d95fa0a89835ebb6f7d352
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a>Tecnologías de virtualización admitidas y limitaciones comunes en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2017-02-06_

El complemento VDI para Lync permite llamadas de audio y vídeo para tecnologías de virtualización compatibles. Esto extiende la funcionalidad descrita para Microsoft Lync Server 2010 en las notas del producto [de virtualización de cliente en Microsoft lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) . Conforme a las normativas estándar para teléfonos, también se incluye compatibilidad con E911. En las siguientes secciones se describen las tecnologías de virtualización admitidas por el complemento VDI de Lync y las limitaciones de las características conocidas.

<div>

## <a name="support-for-virtualization-technologies"></a>Soporte de tecnologías de virtualización

El complemento de VDI para Lync es compatible con el entorno remoto de escritorio completo en el escenario de escritorio virtual personal, pero no en el escenario de sesión de escritorio remoto. Estos entornos pueden describirse así:

  - **Compatible: escritorios virtuales personalizados o infraestructura de escritorio virtual (VDI).**    En este escenario, cada usuario inicia sesión en un escritorio virtual personalizable y puede guardar archivos en el escritorio que permanecen entre sesiones. Los servicios de escritorio remoto de Microsoft, la vista de horizonte de VMware y Citrix XenDesktop son implementaciones probadas para su uso con Lync. Para obtener información sobre los entornos de VDI específicos del proveedor y el hardware de cliente que Microsoft ha probado, consulte [infraestructura cualificada para Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).

  - **No admitido: sesiones de escritorio remoto.**    En este escenario, cada usuario inicia sesión en una sesión de escritorio virtual genérica que no se puede personalizar. Algunos ejemplos de implementaciones son las sesiones de escritorio remoto de Microsoft (RDSH) y Citrix XenApp combinadas con Citrix Receiver.

El complemento de VDI para Lync no admite otras tecnologías de virtualización, como la virtualización de aplicaciones, que permite el uso de una aplicación sin requerir la instalación de la aplicación completa de forma local. Algunos ejemplos de implementaciones son Citrix XenApp y Microsoft Application Virtualization (App-V). El streaming de aplicaciones, la comunicación remota de aplicaciones y los modos mixtos de virtualización (por ejemplo, la comunicación remota de aplicaciones en la comunicación remota de escritorio completa) no se admiten.

Para permitir la extensibilidad, el complemento de VDI para Lync se diseñó para usar las API independientes de la plataforma denominadas canales virtuales dinámicos (DVCs). Para escenarios que no son explícitamente compatibles con Lync, consulte declaraciones de soporte técnico del proveedor de soluciones de VDI.

</div>

<div>

## <a name="known-feature-limitations"></a>Limitaciones comunes de la funciones

A continuación se muestran algunas limitaciones conocidas al usar Lync 2013 en un entorno de VDI:

  - La delegación de llamadas y las características de anonymization de grupo de respuesta son limitadas.

  - No se admiten estas características:
    
      - Las páginas de ajuste del dispositivo de audio y de vídeo integrados.
    
      - El vídeo de múltiples vistas.
    
      - La grabación de las conversaciones.
    
      - Servicios de escritorio remoto (RDS).
    
      - Unirse a reuniones de forma anónima (es decir, unirse a reuniones de Lync hospedadas por una organización que no se federan con su organización).
    
      - Usar el complemento VDI de Lync junto con un dispositivo de Lync Phone Edition.
    
      - La continuación de llamadas en caso de una interrupción de la red.
    
      - Las características de tonos de llamada personalizados y de música en espera.

  - El complemento de VDI para Lync no es compatible en un entorno de Office 365.

</div>

</div>

<span> </span>

</div>

</div>

</div>

