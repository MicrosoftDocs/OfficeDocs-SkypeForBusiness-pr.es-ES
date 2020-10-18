---
title: 'Lync Server 2013: solicitar certificados para componentes perimetrales'
description: 'Lync Server 2013: solicitar certificados para componentes perimetrales.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates for edge components
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398708(v=OCS.15)
ms:contentKeyID: 48184779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 461e40921c88f26ce56141a8782ef2a04ce99667
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579016"
---
# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a>Solicitar certificados para componentes perimetrales en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-07_

Los certificados requeridos para admitir el acceso de usuarios externos incluyen los certificados emitidos por una entidad de certificación (CA) pública y los certificados emitidos por una CA empresarial interna:

  - Los certificados necesarios para la interfaz externa del servidor perimetral y el proxy inverso deben ser emitidos por una entidad de certificación pública.

  - Los certificados requeridos para la interfaz interna puede emitirlos tanto una CA pública como una CA empresarial interna. Se recomienda usar una CA interna de Windows Server 2008, una CA de Windows Server 2008 R2, una CA de Windows Server 2012 o una CA de Windows Server 2012 R2 para crear estos certificados y ahorrarse en el gasto del uso de certificados públicos.

<div>


> [!IMPORTANT]  
> El procesamiento de las solicitudes de certificado pueden tardar, en especial las solicitudes a CA públicas, por lo que deberá solicitar los certificados para sus servidores perimetrales con la suficiente anterioridad para que estén disponibles al iniciar la implementación de los componentes de servidor perimetral. Para obtener un resumen de los requisitos de certificado para servidores perimetrales, consulte <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">requisitos de certificados para el acceso de usuarios externos en Lync Server 2013</A>.



</div>

Aunque puede optar por usar una CA pública para el certificado perimetral interno, se recomienda usar una CA empresarial interna para esos otros certificados, para minimizar el coste de los certificados. Para obtener un resumen de los requisitos de certificado para servidores perimetrales, consulte [requisitos de certificados para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

<div>


> [!NOTE]  
> Al instalar un servidor perimetral, el programa de instalación incluye un asistente para certificados que facilita las tareas de solicitud, asignación e instalación de certificados, tal como se describe en la sección <A href="lync-server-2013-set-up-edge-certificates.md">configurar certificados perimetrales para Lync Server 2013</A> . Si desea solicitar certificados antes de instalar un servidor perimetral (por ejemplo, para ahorrar tiempo durante la implementación real de los componentes del servidor perimetral), puede hacerlo con servidores internos siempre que garantice que los certificados son exportables y contienen todos los nombres alternativos de sujeto necesarios. Esta documentación no indica los procedimientos de uso de los servidores internos para solicitar certificados.



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a>Solicitar certificados a una CA pública

La implementación del servidor perimetral requiere un único certificado público para las interfaces externas de los servidores perimetrales, que se usa para el servicio perimetral de acceso, el servicio perimetral de conferencia web y para el servicio de autenticación A/V. Este certificado debe tener una clave privada exportable para asegurarse de que el servicio de autenticación A/V usa las mismas claves en todos los servidores perimetrales de un grupo. El proxy inverso, que se usa con Microsoft Internet Security and Acceleration (ISA) Server 2006 o Microsoft Forefront Threat Management Gateway 2010, también requiere un certificado público.

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a>Solicitar certificados a una CA empresarial interna

Los certificados necesarios para la interfaz perimetral interna pueden proceder de una entidad de certificación pública o de una entidad de certificación interna. Se puede usar una entidad de certificación empresarial interna para que el costo de los certificados sea menor. Si la organización tiene implementada una entidad de certificación interna, es la que debe emitir los certificados para la red perimetral interna. Si se recurre a una entidad de certificación empresarial interna para obtener los certificados internos, el costo de los certificados se verá reducido.

Para obtener un resumen de los requisitos de certificado para los componentes perimetrales, consulte [Certificate Requirements for external User Access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md). Para obtener información detallada sobre cómo usar una CA pública para obtener certificados, consulte [solicitar certificados para componentes perimetrales en Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md). Para obtener más información sobre cómo solicitar, instalar y asignar certificados, consulte [configurar los certificados perimetrales para Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

