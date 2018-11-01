---
title: 'Lync Server 2013: Requisitos de la infraestructura de certificados'
TOCTitle: Requisitos de la infraestructura de certificados
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48274225
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos de la infraestructura de certificados para Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Lync Server 2013 requiere una infraestructura de clave pública (PKI) que admita TLS y conexiones Mutual TLS (MTLS).

Lync Server usa certificados en los siguientes casos:

  - Conexiones TLS entre clientes y servidores

  - Conexiones MTLS entre servidores

  - Federación mediante la detección automática basada en DNS de los socios

  - Acceso de usuarios remotos a la mensajería instantánea (IM)

  - Acceso de usuarios externos a sesiones de audio/vídeo (A/V), a uso compartido de aplicaciones y a conferencias

  - Solicitudes móviles mediante detección automática de servicios web

Para Lync Server, se aplican los siguientes requisitos comunes:

  - Todos los certificados de servidor deben admitir la autorización de servidor (EKU de servidor).

  - Todos los certificados de servidor deben contener un punto de distribución CRL (CDP).

  - Todos los certificados deben estar firmados mediante un algoritmo de firma compatible con el sistema operativo. Lync Server 2013 admite un conjunto de aplicaciones con SHA-1 y SHA-2 de tamaños implícitos (224, 256, 384 y 512 bits), y cumple o supera los requisitos del sistema operativo. Para obtener información sobre la compatibilidad con el sistema operativo, consulte [http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002).

  - Se admite la inscripción automática para los servidores internos que ejecutan Lync Server.

  - No se admite la inscripción automática para los servidores perimetrales de Lync Server.

  - Cuando envíe una solicitud de certificado web a una entidad de certificación de Windows Server 2003, deberá hacerlo desde un equipo que ejecute Windows Server 2003 con SP2 o Windows XP.
    
    Tenga en cuenta que aunque KB922706 ofrece soporte técnico para resolver problemas relacionados con los certificados web de inscripción de una inscripción web de los servicios de certificados de Windows Server 2003, no permite el uso de Windows Server 2008, Windows Vista o Windows 7 para solicitar un certificado desde una entidad de certificación de Windows Server 2003.

  - Se admiten longitudes de clave de cifrado de 1024, 2048 y 4096. Se recomienda usar longitudes de clave de 2048 y superiores.

  - El algoritmo de firma hash o implícito predeterminado es RSA. También se admiten los algoritmos ECDH\_P256, ECDH\_P384 y ECDH\_P521. 

## En esta sección

  - [Requisitos de certificado para Servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Requisitos de certificado para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Requisitos de certificados para el servidor de chat persistente en Lync Server 2013](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [Requisitos de certificado para movilidad en Lync Server 2013](lync-server-2013-certificate-requirements-for-mobility.md)

