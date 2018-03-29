---
title: Autenticación de usuarios y clientes para Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: Un usuario confianza es aquel cuyas credenciales se han autenticado por un servidor de confianza en Skype para Business Server 2015. Este servidor suele ser un servidor Standard Edition, servidor Enterprise Edition de Front-End o Director. Skype para Business Server se basa en servicios de dominio de Active Directory como repositorio de fondo único, confianza de credenciales de usuario.
ms.openlocfilehash: d8fa9265a4c27432dd4c2dba6e15c07e39f348b8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="user-and-client-authentication-for-skype-for-business-server-2015"></a>Autenticación de usuarios y clientes para Skype Empresarial Server 2015
 
Un usuario confianza es aquel cuyas credenciales se han autenticado por un servidor de confianza en Skype para Business Server 2015. Este servidor suele ser un servidor Standard Edition, servidor Enterprise Edition de Front-End o Director. Skype para Business Server se basa en servicios de dominio de Active Directory como repositorio de fondo único, confianza de credenciales de usuario.
  
La autenticación consiste en proporcionar credenciales de usuario a un servidor de confianza. Skype para Business Server utiliza los siguientes protocolos de autenticación, según el estado y la ubicación del usuario.
  
- **Protocolo de MIT Kerberos versión 5 seguridad** para los usuarios internos con credenciales de Active Directory. Kerberos requiere conectividad de cliente para servicios de dominio de Active Directory, por eso no puede utilizarse para autenticar a clientes fuera del firewall corporativo.
    
- **Protocolo NTLM** para los usuarios con credenciales de Active Directory que se conecten desde un extremo fuera del firewall corporativo. El servicio de servidor perimetral de acceso pasa las solicitudes de inicio de sesión a un Director, si está presente, o un servidor Front-End para la autenticación. El servicio de servidor perimetral de acceso no realiza autenticación.
    
    > [!NOTE]
    > El protocolo NTLM ofrece una protección contra ataques más débil que la de Kerberos, por lo que algunas organizaciones minimizan el uso de NTLM. Como resultado, puede estar restringido el acceso a Skype para Business Server 2015 internos o los clientes conectados a través de una conexión VPN o de DirectAccess. 
  
- **Protocolo de autenticación** implícita para los usuarios denominados anónimos. Los usuarios anónimos son usuarios externos que no tienen credenciales de Active Directory reconocidas, pero que han recibido una invitación a una conferencia local y tienen una clave de conferencia válida. La autenticación implícita no se utiliza para otras interacciones del cliente.
    
Skype para la autenticación de servidor de negocios 2015 consta de dos fases:
  
1. Se establece una asociación de seguridad entre el cliente y el servidor.
    
2. El cliente y el servidor utilizan la asociación de seguridad existente para firmar los mensajes que envían y comprobar los que reciben. Cuando la autenticación está habilitada en el servidor, no se aceptan los mensajes no autenticados de un cliente.
    
La confianza en un usuario se adjunta a cada mensaje que procede del usuario, no a la identidad del usuario. El servidor comprueba cada mensaje para determinar si las credenciales de usuario son válidas. Si lo son, no solo el primer servidor en recibir el mensaje no lo desafía, sino que tampoco lo hacen los demás servidores de la nube de servidores de confianza.
  
Los usuarios con credenciales válidas emitidas por un socio federado son de confianza pero, de manera opcional, algunas restricciones adicionales impiden que disfruten de todos los privilegios otorgados a los usuarios internos.
  
Los protocolos ICE y TURN también usan el desafío de autenticación implícita que se describe en la RFC del IETF referente a TURN.
  
Certificados de cliente ofrecen un método alternativo para que los usuarios se autentiquen mediante Skype para Business Server 2015. En vez de proporcionar un nombre de usuario y una contraseña, los usuarios cuentan con un certificado y una clave privada correspondiente al certificado necesario para resolver un desafío criptográfico. (Este certificado debe tener un nombre de asunto o nombre alternativo del sujeto que identifica al usuario y debe ser emitido por una CA raíz de confianza en servidores que ejecuten Skype para Business Server 2015, estar dentro del período de validez del certificado y no ha sido revocado.) Para ser autenticados, los usuarios sólo tiene que escribir en un número de identificación personal (PIN). Los certificados son particularmente útiles en el caso de teléfonos fijos, teléfonos móviles y otros dispositivos donde resulta complicado escribir un nombre de usuario y una contraseña.
  

