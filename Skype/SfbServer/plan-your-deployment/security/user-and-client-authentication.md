---
title: Autenticación de usuarios y clientes para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: Un usuario de confianza es aquel cuyas credenciales han sido autenticadas por un servidor de confianza en Skype empresarial Server. Este servidor suele ser un servidor Standard Edition, Enterprise Edition o director. Skype empresarial Server depende de los servicios de dominio de Active Directory como el único repositorio back-end de confianza de las credenciales de usuario.
ms.openlocfilehash: 2ffabce6546bf8b542503f8c80fe5cb2b952c568
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815588"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a>Autenticación de usuarios y clientes para Skype empresarial Server
 
Un usuario de confianza es aquel cuyas credenciales han sido autenticadas por un servidor de confianza en Skype empresarial Server. Este servidor suele ser un servidor Standard Edition, Enterprise Edition o director. Skype empresarial Server depende de los servicios de dominio de Active Directory como el único repositorio back-end de confianza de las credenciales de usuario.
  
La autenticación consiste en proporcionar credenciales de usuario a un servidor de confianza. Skype empresarial Server usa los siguientes protocolos de autenticación, según el estado y la ubicación del usuario.
  
- **Protocolo de seguridad MIT Kerberos versión 5** para usuarios internos con credenciales de Active Directory. Kerberos requiere conectividad de cliente con los servicios de dominio de Active Directory, motivo por el cual no se puede usar para autenticar clientes fuera del firewall de la empresa.
    
- **Protocolo NTLM** para usuarios con credenciales de Active Directory que se conectan desde un extremo fuera del Firewall corporativo. El servicio perimetral de acceso pasa las solicitudes de inicio de sesión a un director, si está presente, o a un servidor front-end para la autenticación. El servicio perimetral de acceso en sí no realiza ninguna autenticación.
    
    > [!NOTE]
    > El protocolo NTLM ofrece una protección contra ataques más débil que la de Kerberos, por lo que algunas organizaciones minimizan el uso de NTLM. Como resultado, es posible que el acceso a Skype empresarial Server esté restringido a los clientes internos o a los que se conectan a través de una conexión VPN o DirectAccess. 
  
- **Protocolo de autenticación** implícita para los usuarios denominados anónimos. Los usuarios anónimos son usuarios externos que no tienen credenciales de Active Directory reconocidas, pero que han recibido una invitación a una conferencia local y tienen una clave de conferencia válida. La autenticación implícita no se utiliza para otras interacciones del cliente.
    
La autenticación de Skype empresarial Server consta de dos fases:
  
1. Se establece una asociación de seguridad entre el cliente y el servidor.
    
2. El cliente y el servidor utilizan la asociación de seguridad existente para firmar los mensajes que envían y comprobar los que reciben. Cuando la autenticación está habilitada en el servidor, no se aceptan los mensajes no autenticados de un cliente.
    
La confianza en un usuario se adjunta a cada mensaje que procede del usuario, no a la identidad del usuario. El servidor comprueba cada mensaje para determinar si las credenciales de usuario son válidas. Si lo son, no solo el primer servidor en recibir el mensaje no lo desafía, sino que tampoco lo hacen los demás servidores de la nube de servidores de confianza.
  
Los usuarios con credenciales válidas emitidas por un socio federado son de confianza pero, de manera opcional, algunas restricciones adicionales impiden que disfruten de todos los privilegios otorgados a los usuarios internos.
  
Los protocolos ICE y TURN también usan el desafío de autenticación implícita que se describe en la RFC del IETF referente a TURN.
  
Los certificados de cliente proporcionan una forma alternativa para que los usuarios puedan ser autenticados por Skype empresarial Server. En vez de proporcionar un nombre de usuario y una contraseña, los usuarios cuentan con un certificado y una clave privada correspondiente al certificado necesario para resolver un desafío criptográfico. (Este certificado debe tener un nombre de asunto o un nombre alternativo de asunto que identifique al usuario y debe ser emitido por una entidad de certificación raíz en la que confíen los servidores con Skype empresarial Server, estar dentro del período de validez del certificado y no haberse revocado). Para ser autenticado, los usuarios solo tienen que escribir un número de identificación personal (PIN). Los certificados son particularmente útiles en el caso de teléfonos fijos, teléfonos móviles y otros dispositivos donde resulta complicado escribir un nombre de usuario y una contraseña.
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>Requisitos criptográficos debido a la 4,5 de ASP.net 

A partir de Skype empresarial Server 2015 CU5, AES no es compatible con ASP.NET 4,6 y esto puede provocar errores en la aplicación reuniones de Skype. Si un cliente usa AES como valor de validación de clave de equipo, tendrá que restablecer el valor de la clave de equipo a SHA-1 u otro algoritmo admitido en el nivel de sitio de la aplicación reuniones de Skype en IIS. Si es necesario, consulte la administración de la [configuración de IIS 8,0 ASP.net](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) para obtener instrucciones.
  
Otros valores admitidos son:
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
  Ya no se permiten los valores AES, 3DES y MD5, ya que cuando se encontraban en ASP.NET 4. Las [mejoras en el cifrado de ASP.NET 4,5, PT. 2,](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) más detalles.
  
