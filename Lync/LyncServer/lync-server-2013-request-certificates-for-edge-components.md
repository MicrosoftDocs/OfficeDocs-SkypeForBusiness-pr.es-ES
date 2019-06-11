---
title: 'Lync Server 2013: Solicitar certificados para componentes perimetrales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Request certificates for edge components
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398708(v=OCS.15)
ms:contentKeyID: 48184779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e848e5fb8ea120bab2251dff776e2c9c27eacca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a>Solicitar certificados para componentes perimetrales en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-07_

Los certificados necesarios para admitir el acceso de usuarios externos incluyen certificados emitidos por una entidad de certificación (CA) pública y certificados emitidos por una entidad de certificación empresarial interna:

  - Los certificados necesarios para la interfaz externa del servidor perimetral y el proxy inverso deben ser emitidos por una entidad de certificación pública.

  - Los certificados necesarios para la interfaz interna pueden ser emitidos por una entidad de certificación pública o por una entidad de certificación empresarial interna. Recomendamos usar una CA interna de Windows Server 2008, Windows Server 2008 R2 CA, Windows Server 2012 CA o Windows Server 2012 R2 CA para crear estos certificados y ahorrar al gasto de usar certificados públicos.

<div>


> [!IMPORTANT]  
> Puede demorar el proceso de procesar las solicitudes de certificado, especialmente las de las entidades de certificación públicas, por lo que debe solicitar certificados para los servidores perimetrales lo suficientemente pronto como para asegurarse de que estén disponibles al iniciar la implementación de los componentes del servidor perimetral. Para obtener un resumen de los requisitos de certificado para servidores perimetrales, consulte <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">requisitos de certificados para el acceso de usuarios externos en Lync Server 2013</A>.



</div>

Aunque puede elegir usar una CA pública para el certificado de contorno interno, le recomendamos que use una CA de empresa interna para esos otros certificados para minimizar el costo de los certificados. Para obtener un resumen de los requisitos de certificado para servidores perimetrales, consulte [requisitos de certificados para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

<div>


> [!NOTE]  
> Al instalar un servidor perimetral, el programa de instalación incluye un asistente de certificados que facilita las tareas de solicitar, asignar e instalar certificados, como se describe en la sección <A href="lync-server-2013-set-up-edge-certificates.md">configurar certificados perimetrales para Lync Server 2013</A> . Si desea solicitar certificados antes de instalar un servidor perimetral (por ejemplo, para ahorrar tiempo durante la implementación real de los componentes del servidor perimetral), puede hacerlo con servidores internos siempre que se asegure de que los certificados son exportables y contienen todos los se necesitan nombres alternativos de asunto. En esta documentación no se proporcionan procedimientos para usar servidores internos con el fin de solicitar certificados.



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a>Solicitar certificados de una entidad de certificación pública

La implementación de su servidor perimetral requiere un único certificado público para las interfaces externas de los servidores perimetrales, que se usa para el servicio perimetral de acceso, el servicio perimetral de conferencias web y para el servicio de autenticación A/V. Este certificado debe tener una clave privada exportable para asegurarse de que el servicio de autenticación A/V use las mismas claves en todos los servidores perimetrales de un grupo. El proxy inverso, que se usa con Microsoft Internet Security and Acceleration (ISA) Server 2006 o Microsoft Forefront Threat Management Gateway 2010, también requiere un certificado público.

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a>Solicitar certificados de una CA de empresa interna

Los certificados necesarios para la interfaz de borde interno pueden ser emitidos por una entidad de certificación pública (CA) o una CA interna. Puede usar una entidad de certificación empresarial interna para ayudar a minimizar el costo de los certificados. Si su organización tiene una CA interna implementada, la entidad de certificación interna debe emitir los certificados para el contorno interno. El uso de una CA de empresa interna para certificados internos puede reducir el costo de los certificados.

Para obtener un resumen de los requisitos de certificado para los componentes de Edge, consulte [requisitos de certificados para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md). Para obtener más información sobre cómo usar una CA pública para obtener certificados, consulte [solicitar certificados para componentes de Edge en Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md). Para obtener más información sobre cómo solicitar, instalar y asignar certificados, consulte [configurar certificados perimetrales para Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

