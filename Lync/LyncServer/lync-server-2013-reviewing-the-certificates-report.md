---
title: 'Lync Server 2013: revisar el informe certificados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a83167576746d3f90d96658b0dd3d65815f5375
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a>Revisar el informe de certificados en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

El informe certificados contiene todos los certificados necesarios en la implementación recomendada de Lync Server 2013. La herramienta de planeación cuenta con los nombres de asunto y los nombres alternativos de asunto que se escriben. El texto predeterminado que se deja sin editar puede representar un posible desafío para el equipo responsable de solicitar y emitir los certificados. La información del certificado también contiene datos sobre el origen desde el cual puede emitirse normalmente el certificado. Si la infraestructura no dispone de una infraestructura de clave pública (PKI) interna, todos los certificados se pueden solicitar a través de un proveedor de certificados público. Los campos “Uso mejorado de clave (EKU)” y “Asignar a” del informe son muy útiles para comprender el objetivo y la ubicación de cada certificado.

![Informe de administración de certificados] (images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Informe de administración de certificados")

Revise con atención y comprenda completamente el uso y el propósito de cada certificado de la implementación. Si tiene alguna pregunta acerca de la función de un certificado, determine los elementos con los que se comunica un servidor o servicio. Los certificados de Lync Server 2013 se usan para dos propósitos principales:

  - Seguridad de la capa de transporte mutua (MTLS): los equipos que participan en la comunicación presentan un certificado que prueba su identidad al otro equipo; esto se conoce como autenticación del servidor. La comunicación no puede comenzar hasta que ambos equipos confíen mutuamente en la identidad del otro.

  - Cifrado: el cifrado (Capa de sockets seguros, o SSL, y Seguridad de la capa de transporte, o TLS) es un medio fundamental para proteger las comunicaciones y la privacidad, así como para crear comunicaciones de confianza y un sistema de colaboración.

<div>

## <a name="see-also"></a>Vea también


[Revisión de los informes del administrador en Lync Server 2013](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

