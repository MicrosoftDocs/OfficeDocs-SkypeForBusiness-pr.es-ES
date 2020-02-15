---
title: 'Lync Server 2013: requisitos de configuración para el proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration requirements for reverse proxy
ms:assetid: c37d688a-28e4-4822-80cc-6add59c71052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945651(v=OCS.15)
ms:contentKeyID: 51541518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efa0124bb66974755a7cae0ab799dc66cc48fd1e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a>Requisitos de configuración para el proxy inverso en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-05_

Lync Server 2013 impone algunos requisitos en las comunicaciones del cliente externo que luego se pasan a los servicios web externos hospedados en el director, el grupo de directores, el servidor front-end o el grupo de servidores front-end. El proxy inverso también es responsable de publicar el servidor de Office Web Apps, si ofrece conferencias a los usuarios.

<div>


> [!NOTE]  
> Lync Server 2013 no especifica un proxy inverso concreto que debe usar. Lync Server 2013 solo define los requisitos operativos que el proxy inverso debe poder hacer. Normalmente, el proxy inverso que ya ha implementado en su infraestructura puede cumplir los requisitos.



</div>

<div>

## <a name="reverse-proxy-requirements"></a>Requisitos de proxy inverso

Las operaciones funcionales que Lync Server 2013 espera que realice un proxy inverso son:

  - Use la capa de sockets seguros (SSL) y la seguridad de la capa de transporte (TLS) implementada mediante certificados adquiridos de una entidad de certificación pública para conectarse a los servicios web externos publicados del Director, el grupo de servidores de Director, el servidor front-end o el grupo de servidores front-end. El director y el servidor front-end pueden estar en un grupo de carga equilibrada mediante equilibradores de carga de hardware.

  - Posibilidad de publicar sitios Web internos con certificados para cifrado o publicarlos a través de un medio sin cifrar, si es necesario.

  - Puede publicar un sitio web hospedado internamente de forma externa mediante un nombre de dominio completo (FQDN).

  - Puede publicar todo el contenido del sitio web hospedado. De forma predeterminada, puede usar la ** / ** Directiva, que es reconocida por la mayoría de los servidores web para indicar "publicar todo el contenido en el servidor Web". También puede modificar la Directiva, por ejemplo, **/Uwca/\***, que significa "publicar todo el contenido en el directorio virtual Ucwa".

  - Debe poder configurarse para requerir conexiones de capa de sockets seguros (SSL) y seguridad de la capa de transporte (TLS) con clientes que soliciten contenido desde un sitio Web publicado.

  - Debe aceptar certificados con entradas de nombre alternativo de sujeto (SAN).

  - Debe poder permitir el enlace de un certificado a un agente de escucha o a una interfaz a través de la cual se resolverá el FQDN de servicios web externos. Las configuraciones de la escucha son preferibles a las interfaces. Se pueden configurar varios agentes de escucha en una sola interfaz.

  - Debe permitir la configuración de la administración del encabezado de host. A menudo, el encabezado de host original enviado por el cliente que realiza la solicitud debe pasar de forma transparente, en lugar de ser modificado por el proxy inverso.

  - Puentes de tráfico SSL y TLS desde un puerto definido externamente (por ejemplo, TCP 443) a otro puerto definido (por ejemplo, TCP 4443). El proxy inverso puede descifrar el paquete en su recepción y, a continuación, volver a cifrar el paquete en el envío.

  - Puentes de tráfico TCP no cifrado de un puerto (por ejemplo, TCP 80) a otro (por ejemplo, TCP 8080).

  - Permitir la configuración de la autenticación NTLM, o aceptarla, sin autenticación ni autenticación de paso a través.

</div>

</div>

<span> </span>

</div>

</div>

</div>

