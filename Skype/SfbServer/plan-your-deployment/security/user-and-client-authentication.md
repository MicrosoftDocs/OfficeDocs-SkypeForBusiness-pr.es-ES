---
title: Autenticación de usuario y el cliente para Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: Un usuario de confianza es aquel cuyas credenciales se han autenticado por un servidor de confianza en Skype para Business Server. Este servidor suele ser un servidor Standard Edition, Director o servidor Front-End de Enterprise Edition. Skype para Business Server se basa en los servicios de dominio de Active Directory como el repositorio back-end confianza único de credenciales de usuario.
ms.openlocfilehash: f8f006ac3f727553f612070ea9bdbf696d81a97e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883238"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a>Autenticación de usuario y el cliente para Skype para Business Server
 
Un usuario de confianza es aquel cuyas credenciales se han autenticado por un servidor de confianza en Skype para Business Server. Este servidor suele ser un servidor Standard Edition, Director o servidor Front-End de Enterprise Edition. Skype para Business Server se basa en los servicios de dominio de Active Directory como el repositorio back-end confianza único de credenciales de usuario.
  
La autenticación consiste en proporcionar credenciales de usuario a un servidor de confianza. Skype para Business Server utiliza los siguientes protocolos de autenticación, según el estado y la ubicación del usuario.
  
- **Protocolo de MIT Kerberos versión 5 seguridad** para los usuarios internos con credenciales de Active Directory. Kerberos requiere la conectividad del cliente a los servicios de dominio de Active Directory, que es la razón por la que no se puede usar para autenticar clientes ubicados fuera del firewall corporativo.
    
- **Protocolo NTLM** para los usuarios con credenciales de Active Directory que se conectan desde un extremo ubicado fuera del firewall corporativo. El servicio de servidor perimetral de acceso pasa las solicitudes de inicio de sesión a un Director, si está presente, o un servidor Front-End para la autenticación. El propio servicio de servidor perimetral de acceso no realiza la autenticación.
    
    > [!NOTE]
    > El protocolo NTLM ofrece una protección contra ataques más débil que la de Kerberos, por lo que algunas organizaciones minimizan el uso de NTLM. Como resultado, acceso a Skype para Business Server puede estar restringido a interno o los clientes conectan a través de una conexión VPN o DirectAccess. 
  
- **Protocolo de autenticación** implícita para los usuarios denominados anónimos. Los usuarios anónimos son usuarios externos que no tienen credenciales de Active Directory reconocidas, pero que han recibido una invitación a una conferencia local y tienen una clave de conferencia válida. La autenticación implícita no se utiliza para otras interacciones del cliente.
    
Skype para autenticación de servidor empresarial consta de dos fases:
  
1. Se establece una asociación de seguridad entre el cliente y el servidor.
    
2. El cliente y el servidor utilizan la asociación de seguridad existente para firmar los mensajes que envían y comprobar los que reciben. Cuando la autenticación está habilitada en el servidor, no se aceptan los mensajes no autenticados de un cliente.
    
La confianza en un usuario se adjunta a cada mensaje que procede del usuario, no a la identidad del usuario. El servidor comprueba cada mensaje para determinar si las credenciales de usuario son válidas. Si lo son, no solo el primer servidor en recibir el mensaje no lo desafía, sino que tampoco lo hacen los demás servidores de la nube de servidores de confianza.
  
Los usuarios con credenciales válidas emitidas por un socio federado son de confianza pero, de manera opcional, algunas restricciones adicionales impiden que disfruten de todos los privilegios otorgados a los usuarios internos.
  
Los protocolos ICE y TURN también usan el desafío de autenticación implícita que se describe en la RFC del IETF referente a TURN.
  
Certificados de cliente proporcionan un método alternativo para que los usuarios se autentiquen mediante Skype para Business Server. En vez de proporcionar un nombre de usuario y una contraseña, los usuarios cuentan con un certificado y una clave privada correspondiente al certificado necesario para resolver un desafío criptográfico. (Este certificado debe tener un nombre de sujeto o nombre alternativo del sujeto que identifica al usuario y debe ser emitido por una entidad de certificación raíz que sea de confianza por los servidores que ejecutan Skype para Business Server, estar dentro del período de validez del certificado y no ha sido revocado.) Para ser autenticados, los usuarios sólo tiene que escribir un número de identificación personal (PIN). Los certificados son particularmente útiles en el caso de teléfonos fijos, teléfonos móviles y otros dispositivos donde resulta complicado escribir un nombre de usuario y una contraseña.
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>Requisitos de cifrado debido a ASP .NET 4.5 

A partir de Skype para Business Server 2015 CU5, AES no es compatible con ASP.NET 4.6 y esto puede causar la aplicación de las reuniones de Skype que se inicie. Si un cliente usa AES como el valor de la clave de validación de máquina debe restablecer el valor de clave de máquina a SHA-1 u otro algoritmo compatible en el nivel de sitio de la aplicación de las reuniones de Skype en IIS. Si es necesario, vea [Administración de la configuración de ASP.NET de IIS 8.0](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) para obtener instrucciones.
  
Otros valores admitidos son:
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
  Los valores de MD5, 3DES y AES son ya no se permite, tal como se administraban una vez en ASP.NET 4. [Mejoras criptográficas en ASP.NET 4.5, pt 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) tiene información más detallada.
  
