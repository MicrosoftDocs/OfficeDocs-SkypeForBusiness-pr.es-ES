---
title: 'Lync Server 2013: requisitos de configuración para el proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuration requirements for reverse proxy
ms:assetid: c37d688a-28e4-4822-80cc-6add59c71052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945651(v=OCS.15)
ms:contentKeyID: 51541518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0367ea79a0f3de6ad716f18aab980e9d9442e148
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a>Requisitos de configuración para el proxy inverso en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-05_

Lync Server 2013 impone algunos requisitos en las comunicaciones del cliente externo que, a continuación, se transfieren a los servicios web externos alojados en el director, el grupo de directores, el servidor front-end o el grupo front-end. El proxy inverso también es responsable de publicar el servidor de Office Web Apps, si ofrece conferencias a los usuarios.

<div>


> [!NOTE]  
> Lync Server 2013 no especifica un proxy inverso determinado que deba usarse. Lync Server 2013 solo define los requisitos operativos que el proxy inverso debe poder hacer. Normalmente, el proxy inverso que ya ha implementado en su infraestructura puede cumplir los requisitos.



</div>

<div>

## <a name="reverse-proxy-requirements"></a>Requisitos del proxy inverso

Las operaciones funcionales en las que Lync Server 2013 esperan que se realice un proxy inverso son las siguientes:

  - Use la capa de sockets seguros (SSL) y la seguridad de la capa de transporte (TLS) implementada mediante certificados adquiridos de una entidad de certificación pública para conectarse a los servicios web externos publicados del Director, grupo de directores, servidor front-end o grupo front-end. El director y el servidor front-end pueden estar en un grupo de equilibrio de carga con equilibradores de carga de hardware.

  - Posibilidad de publicar sitios Web internos mediante certificados para el cifrado, o publicarlos a través de un medio sin cifrar, si es necesario.

  - Puede publicar un sitio web hospedado internamente de forma externa usando un nombre de dominio completo (FQDN).

  - Puede publicar todo el contenido del sitio web hospedado. De forma predeterminada, puede usar la ** / ** Directiva, que es reconocida por la mayoría de los servidores web para indicar "publicar todo el contenido en el servidor Web". También puede modificar la Directiva, por ejemplo, **/Uwca/\***, lo que significa "publicar todo el contenido del directorio virtual Ucwa".

  - Debe ser configurable para requerir conexiones de capa de sockets seguros (SSL) o seguridad de la capa de transporte (TLS) con los clientes que solicitan contenido de un sitio Web publicado.

  - Debe aceptar certificados con entradas de nombre alternativo del sujeto (SAN).

  - Debe poder permitir el enlace de un certificado a un agente de escucha o a una interfaz a través de la cual se resolverá el FQDN de servicios web externos. Se prefiere una configuración de agente de escucha a una de interfaz. Se pueden configurar varios agentes de escucha en una sola interfaz.

  - Debe permitir la configuración de la administración de encabezados de host. A menudo, el encabezado de host original enviado por el cliente solicitante debe transferirse de forma transparente, en lugar de ser modificado por el proxy inverso.

  - Puentes de tráfico SSL y TLS de un puerto definido externamente (por ejemplo, TCP 443) a otro puerto definido (por ejemplo, TCP 4443). El proxy inverso puede descifrar el paquete en el recibo y, después, volver a cifrar el paquete al enviarlo.

  - Puentes de tráfico TCP no cifrado de un puerto (por ejemplo, TCP 80) a otro (por ejemplo, TCP 8080).

  - Permitir la configuración de autenticación NTLM o aceptarla, sin autenticación ni autenticación de acceso directo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

