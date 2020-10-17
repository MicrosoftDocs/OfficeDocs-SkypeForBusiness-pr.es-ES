---
title: 'Lync Server 2013: autenticación de usuario y cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User and client authentication for Lync Server 2013
ms:assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481132(v=OCS.15)
ms:contentKeyID: 59893868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f32ca61178d6bf15791f81e64279e7f1076828e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530207"
---
# <a name="user-and-client-authentication-for-lync-server-2013"></a>Autenticación de usuario y cliente para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-11_

Un usuario de confianza es aquel cuyas credenciales han sido autenticadas por un servidor de confianza en Microsoft Lync Server 2013. Este servidor es, por lo general, un servidor Standard Edition, un servidor front-end Enterprise Edition o un director. Lync Server 2013 depende de los servicios de dominio de Active Directory como el repositorio back-end único y de confianza de las credenciales de usuario.

La autenticación consiste en proporcionar credenciales de usuario a un servidor de confianza. Lync Server 2013 usa los siguientes protocolos de autenticación, en función del estado y la ubicación del usuario.

  - **Protocolo de seguridad MIT Kerberos, versión 5** para los usuarios internos con credenciales de Active Directory. Kerberos requiere la conectividad del cliente a los Servicios de dominio de Active Directory, por lo que no se puede usar para autenticar clientes ubicados fuera del firewall corporativo.

  - **Protocolo NTLM** para los usuarios con credenciales de Active Directory que se conectan desde un extremo ubicado fuera del firewall corporativo. El servicio perimetral de acceso pasa las solicitudes de inicio de sesión a un director, si lo hay, o a un servidor front-end para la autenticación. El servicio perimetral de acceso no realiza la autenticación.
    
    <div>
    

    > [!NOTE]  
    > El protocolo NTLM ofrece una protección contra ataques más débil que la de Kerberos, por lo que algunas organizaciones minimizan el uso de NTLM. Como resultado, el acceso a Lync Server 2013 puede estar restringido a interno o a los clientes conectados a través de una conexión VPN o DirectAccess.

    
    </div>

  - **Protocolo de autenticación implícita** para los usuarios denominados anónimos. Los usuarios anónimos son usuarios externos que no tienen credenciales de Active Directory reconocidas, pero que han recibido una invitación a una conferencia local y tienen una clave de conferencia válida. La autenticación implícita no se utiliza para otras interacciones del cliente.

La autenticación de Lync Server 2013 consta de dos fases:

1.  Se establece una asociación de seguridad entre el cliente y el servidor.

2.  El cliente y el servidor utilizan la asociación de seguridad existente para firmar los mensajes que envían y comprobar los que reciben. Cuando la autenticación está habilitada en el servidor, no se aceptan los mensajes no autenticados de un cliente.

La confianza en un usuario se adjunta a cada mensaje que procede del usuario, no a la identidad del usuario. El servidor comprueba cada mensaje para determinar si las credenciales de usuario son válidas. Si son válidas, no solo el primer servidor en recibir el mensaje no lo desafía, sino que tampoco lo hacen los demás servidores de la nube de servidores de confianza.

Los usuarios con credenciales válidas emitidas por un socio federado son de confianza pero, de manera opcional, algunas restricciones adicionales impiden que disfruten de todos los privilegios otorgados a los usuarios internos.

Los protocolos ICE y TURN también usan el desafío de autenticación implícita que se describe en la RFC del IETF referente a TURN.

Los certificados de cliente proporcionan una forma alternativa para que los usuarios se autentiquen mediante Lync Server 2013. En vez de proporcionar un nombre de usuario y contraseña, los usuarios tienen un certificado y una clave privada correspondiente al certificado necesario para resolver un desafío criptográfico. (Este certificado debe tener un nombre de sujeto o un nombre alternativo de sujeto que identifique al usuario y debe ser emitido por una entidad de certificación raíz de confianza para los servidores que ejecutan Lync Server 2013, que esté dentro del período de validez del certificado y que no se haya revocado). Para autenticarse, los usuarios solo deben escribir un número de identificación personal (PIN). Los certificados son particularmente útiles para teléfonos y otros dispositivos que ejecutan Microsoft Lync 2013 Phone Edition donde es difícil escribir un nombre de usuario o una contraseña.

</div>

<span> </span>

</div>

</div>

</div>

