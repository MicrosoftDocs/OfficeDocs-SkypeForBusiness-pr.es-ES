---
title: Marco de seguridad de Lync Server 2013
TOCTitle: Marco de seguridad de Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59682857
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Marco de seguridad de Lync Server 2013

 

_**Última modificación del tema:** 2013-11-08_

Esta sección ofrece información general acerca de los elementos fundamentales que conforman el marco de seguridad para Microsoft Lync Server 2013. Comprender cómo estos elementos funcionen en conjunto es esencial para tomar decisiones con fundamento con relación a la seguridad de la implementación de su Lync Server 2013 particular.

Dichos elementos son los siguientes:

  - Servicios de dominio de Active Directory (AD DS) proporciona un único repositorio back-end de confianza para las cuentas de usuario y los recursos de red.

  - El control de acceso basado en roles (RBAC) le permite delegar tareas administrativas y mantener, al mismo tiempo, altos estándares de seguridad.

  - La infraestructura de clave pública (PKI) utiliza certificados emitidos por entidades de certificación (CA) de confianza para autenticar los servidores y garantizar la integridad de los datos.

  - La Seguridad de la capa de transporte (TLS), HTTPS sobre SSL (HTTPS) y Mutual TLS (MTLS) permiten la autenticación de los extremos y el cifrado de la mensajería instantánea. las secuencias de audio, vídeo y uso compartido de aplicaciones punto a punto se cifran con el protocolo de transporte seguro en tiempo real (SRTP).

  - Para la autenticación del usuario se usan los protocolos estándar de la industria, siempre que sea posible.

  - Windows PowerShell proporciona funciones de seguridad habilitadas de forma predeterminada para que los usuarios no puedan ejecutar scripts fácilmente o sin darse cuenta.

Estos elementos fundamentales de seguridad funcionan en conjunto para definir usuarios, servidores, conexiones y operaciones de confianza y, de ese modo, ayudar a garantizar una base protegida para Lync Server 2013.

## En esta sección

En los temas de esta sección se describe cómo funciona cada uno de estos elementos fundamentales para mejorar la seguridad de la infraestructura de Lync Server.

  - [Servicios de dominio de Active Directory para Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [Control de acceso basado en roles (RBAC) para Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md)

  - [Infraestructura de clave pública de Lync Server 2013](lync-server-2013-public-key-infrastructure.md)

  - [TLS y MTLS para Lync Server 2013](lync-server-2013-tls-and-mtls.md)

  - [Cifrado para Lync Server 2013](lync-server-2013-encryption.md)

  - [Autenticación de usuario y cliente en Lync Server 2013](lync-server-2013-user-and-client-authentication.md)

  - [Herramientas de administración de Windows PowerShell y Lync Server 2013](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

