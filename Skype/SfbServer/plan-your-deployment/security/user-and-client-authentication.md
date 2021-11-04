---
title: Autenticación de usuario y cliente para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: Un usuario de confianza es uno cuyas credenciales han sido autenticadas por un servidor de confianza en Skype Empresarial Server. Este servidor es, por lo general, un servidor Standard Edition, un servidor front-end Enterprise Edition o un director. Skype Empresarial Server se basa en los Servicios de dominio de Active Directory como el repositorio back-end único y de confianza de las credenciales de usuario.
ms.openlocfilehash: d256efdf69afce16a06b3b055a9446b29deb7cb0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737646"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a>Autenticación de usuario y cliente para Skype Empresarial Server
 
Un usuario de confianza es uno cuyas credenciales han sido autenticadas por un servidor de confianza en Skype Empresarial Server. Este servidor es, por lo general, un servidor Standard Edition, un servidor front-end Enterprise Edition o un director. Skype Empresarial Server se basa en los Servicios de dominio de Active Directory como el repositorio back-end único y de confianza de las credenciales de usuario.
  
La autenticación consiste en proporcionar credenciales de usuario a un servidor de confianza. Skype Empresarial Server los siguientes protocolos de autenticación, según el estado y la ubicación del usuario.
  
- **Protocolo de seguridad MIT Kerberos, versión 5** para los usuarios internos con credenciales de Active Directory. Kerberos requiere la conectividad del cliente a los Servicios de dominio de Active Directory, por lo que no se puede usar para autenticar clientes ubicados fuera del firewall corporativo.
    
- **Protocolo NTLM** para los usuarios con credenciales de Active Directory que se conectan desde un extremo ubicado fuera del firewall corporativo. El servicio perimetral de acceso pasa las solicitudes de inicio de sesión a un director, si lo hay, o a un servidor front-end para la autenticación. El servicio perimetral de acceso no realiza la autenticación.
    
    > [!NOTE]
    > El protocolo NTLM ofrece una protección contra ataques más débil que la de Kerberos, por lo que algunas organizaciones minimizan el uso de NTLM. Como resultado, el acceso a Skype Empresarial Server puede restringirse a clientes internos o conectados a través de una conexión VPN o DirectAccess. 
  
- **Protocolo de autenticación implícita** para los usuarios denominados anónimos. Los usuarios anónimos son usuarios externos que no tienen credenciales de Active Directory reconocidas, pero que han recibido una invitación a una conferencia local y tienen una clave de conferencia válida. La autenticación implícita no se utiliza para otras interacciones del cliente.
    
Skype Empresarial Server autenticación consta de dos fases:
  
1. Se establece una asociación de seguridad entre el cliente y el servidor.
    
2. El cliente y el servidor utilizan la asociación de seguridad existente para firmar los mensajes que envían y comprobar los que reciben. Cuando la autenticación está habilitada en el servidor, no se aceptan los mensajes no autenticados de un cliente.
    
La confianza en un usuario se adjunta a cada mensaje que procede del usuario, no a la identidad del usuario. El servidor comprueba cada mensaje para determinar si las credenciales de usuario son válidas. Si son válidas, no solo el primer servidor en recibir el mensaje no lo desafía, sino que tampoco lo hacen los demás servidores de la nube de servidores de confianza.
  
Los usuarios con credenciales válidas emitidas por un socio federado son de confianza pero, de manera opcional, algunas restricciones adicionales impiden que disfruten de todos los privilegios otorgados a los usuarios internos.
  
Los protocolos ICE y TURN también usan el desafío de autenticación implícita que se describe en la RFC del IETF referente a TURN.
  
Los certificados de cliente proporcionan una forma alternativa para que los usuarios puedan autenticarse mediante Skype Empresarial Server. En vez de proporcionar un nombre de usuario y contraseña, los usuarios tienen un certificado y una clave privada correspondiente al certificado necesario para resolver un desafío criptográfico. (Este certificado debe tener un nombre de sujeto o un nombre alternativo de sujeto que identifique al usuario y debe ser emitido por una CA raíz de confianza de los servidores que ejecutan Skype Empresarial Server, estar dentro del período de validez del certificado y no haber sido revocado). Para autenticarse, los usuarios solo deben escribir un número de identificación personal (PIN). Los certificados son especialmente útiles para teléfonos, teléfonos móviles y otros dispositivos en los que es difícil escribir un nombre de usuario y una contraseña.
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>Requisitos criptográficos debido ASP.NET 4.5 

A partir de Skype Empresarial Server 2015 CU5, AES no es compatible con ASP.NET 4.6 y esto puede provocar que Skype Meetings App no se inicie. Si un cliente usa AES como valor de validación de clave de máquina, deberá restablecer el valor de clave de máquina a SHA-1 u otro algoritmo compatible en el nivel de sitio de la aplicación de reuniones de Skype en IIS. Si es necesario, [vea IIS 8.0 ASP.NET Configuration Management](/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) para obtener instrucciones.
  
Otros valores admitidos son:
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
  Los valores AES, 3DES y MD5 ya no están permitidos, ya que una vez estaban en ASP.NET 4. [Las mejoras criptográficas ASP.NET 4.5, pt. 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) tiene más detalles.
