---
title: Autenticación de usuario y cliente en Lync Server 2013
TOCTitle: Autenticación de usuario y cliente en Lync Server 2013
ms:assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn481132(v=OCS.15)
ms:contentKeyID: 59679371
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Autenticación de usuario y cliente en Lync Server 2013

 

_**Última modificación del tema:** 2013-11-11_

Un usuario de confianza es aquel cuyas credenciales han sido autenticadas por un servidor de confianza en Microsoft Lync Server 2013. En general, este servidor es un Servidor Standard Edition, Enterprise EditionServidor front-end o un director. Lync Server 2013 depende de Servicios de dominio de Active Directory como único repositorio back-end de confianza para las credenciales de usuario.

La autenticación consiste en proporcionar credenciales de usuario a un servidor de confianza. Lync Server 2013 utiliza los siguientes protocolos de autenticación, según el estado y la ubicación del usuario.

  - **Protocolo de seguridad MIT Kerberos, versión 5** para los usuarios internos con credenciales de Active Directory. Kerberos requiere la conectividad del cliente a los Servicios de dominio de Servicios de dominio de Active Directory, por lo que no se puede usar para autenticar clientes ubicados fuera del firewall corporativo.

  - **Protocolo NTLM** para usuarios con credenciales de Active Directory que se conectan desde un extremo ubicado fuera del firewall corporativo. El Servidor perimetral de acceso pasa las solicitudes de inicio de sesión a un director, si lo hay, o a un Servidor front-end para la autenticación. El Servidor perimetral de acceso no realiza la autenticación.
    

    > [!NOTE]
    > El protocolo NTLM ofrece una protección contra ataques más débil que la de Kerberos, por lo que algunas organizaciones minimizan el uso de NTLM. Como consecuencia, es posible que el acceso a Lync Server 2013 esté restringido a usuarios internos o clientes con una conexión VPN o DirectAccess.



  - **Protocolo de autenticación implícita** para los usuarios denominados anónimos. Los usuarios anónimos son usuarios externos que no tienen credenciales de Active Directory reconocidas, pero que han recibido una invitación a una conferencia local y tienen una clave de conferencia válida. La autenticación implícita no se utiliza para otras interacciones del cliente.

La autenticación de Lync Server 2013 consta de dos fases:

1.  Se establece una asociación de seguridad entre el cliente y el servidor.

2.  El cliente y el servidor utilizan la asociación de seguridad existente para firmar los mensajes que envían y comprobar los que reciben. Cuando la autenticación está habilitada en el servidor, no se aceptan los mensajes no autenticados de un cliente.

La confianza en un usuario se adjunta a cada mensaje que procede del usuario, no a la identidad del usuario. El servidor comprueba cada mensaje para determinar si las credenciales de usuario son válidas. Si son válidas, no solo el primer servidor en recibir el mensaje no lo desafía, sino que tampoco lo hacen los demás servidores de la nube de servidores de confianza.

Los usuarios con credenciales válidas emitidas por un socio federado son de confianza pero, de manera opcional, algunas restricciones adicionales impiden que disfruten de todos los privilegios otorgados a los usuarios internos.

Los protocolos ICE y TURN también usan el desafío de autenticación implícita que se describe en la RFC del IETF referente a TURN.

Los certificados de cliente proporcionan una alternativa para autenticar a los usuarios con Lync Server 2013. En vez de proporcionar un nombre de usuario y contraseña, los usuarios cuentan con un certificado y una clave privada correspondiente al certificado necesario para resolver un desafío criptográfico. (Este certificado debe tener un nombre de sujeto o un nombre de sujeto alternativo que identifique al usuario y debe estar emitido por una entidad de certificación raíz que sea de confianza para los servidores que utilizan Lync Server 2013, debe estar dentro del período de validez del certificado y no se debe haber revocado). Para autenticarse, los usuarios solo deben ingresar un número de identificación personal (PIN). Los certificados son particularmente útiles en el caso de teléfonos y otros dispositivos que ejecutan Phone Edition de Microsoft Lync 2013 donde resulta complicado escribir un nombre de usuario o una contraseña.

