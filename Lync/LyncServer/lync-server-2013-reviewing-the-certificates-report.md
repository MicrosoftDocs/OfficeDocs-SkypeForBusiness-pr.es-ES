---
title: 'Lync Server 2013: revisión del informe de certificados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a584f331deaf702305367042c6c40679ffb7099f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a>Revisión del informe de certificados en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

El informe de certificados contiene todos los certificados necesarios en la implementación de Lync Server 2013 recomendada. La herramienta de planeación cuenta con los nombres de sujeto y los nombres alternativos de sujeto que se han especificado. El texto predeterminado que queda sin editar puede representar un desafío potencial para el equipo responsable de solicitar y emitir los certificados. La información de certificados contiene también información sobre dónde puede emitirse normalmente el certificado. Si la infraestructura no dispone de una infraestructura de clave pública (PKI) interna, todos los certificados se pueden solicitar a través de un proveedor de certificados público. Los campos Uso mejorado de clave (EKU) y Asignar a del informe son muy útiles para comprender el objetivo y la ubicación en la que debe estar cada certificado.

![Informe de administración de certificados](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Informe de administración de certificados")

Revise atentamente y asegúrese de comprender el uso y el propósito de cada certificado en la implementación. Si hay una pregunta sobre lo que hace un certificado, determine qué servidor o servicio está hablando con qué. Los certificados en Lync Server 2013 se usan para dos propósitos principales:

  - Seguridad de la capa de transporte mutua (MTLS): los equipos que participan en la comunicación cada uno presentan un certificado que prueba su identidad en otro equipo. Esto se conoce como autenticación de servidor. La comunicación no puede comenzar hasta que cada equipo confíe en la identidad del otro equipo.

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

