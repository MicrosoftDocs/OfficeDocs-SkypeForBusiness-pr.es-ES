---
title: 'Lync Server 2013: Compatibilidad con infraestructura de certificados'
TOCTitle: Compatibilidad con infraestructura de certificados
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48275159
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Compatibilidad con infraestructura de certificados en Lync Server 2013

 

_**Última modificación del tema:** 2013-11-07_

Lync Server 2013Lync Server 2013 requiere una infraestructura de clave pública (PKI) que admita Seguridad de la capa de transporte (TLS) y conexiones Mutual TLS (MTLS). De forma predeterminada, nm-ocs-14-2nd está configurado para usar TLS en las conexiones de cliente a servidor. MTLS se usa para las conexiones entre servidores.

Los certificados MTLS deben ser emitidos por entidades de certificación de confianza (CA) para Lync Server 2013. Lync Server admite certificados emitidos por las siguientes entidades de certificación:

  - Certificados emitidos por una entidad de certificación interna:
    
      - La CA de Sistema operativo Windows Server 2003
    
      - La CA de Sistema operativo Windows Server 2008
    
      - La CA de Sistema operativo Windows Server 2008 R2
    
      - La CA del sistema operativo Windows Server 2012
    
      - La CA del sistema operativo Windows Server 2012 R2

  - Certificados emitidos por una entidad de certificación pública

La comunicación con el resto de aplicaciones y servidores como, por ejemplo, Exchange 2013, requiere el uso de un certificado compatible con las otras aplicaciones y productos. Para la versión de 2013, Lync Server 2013 y el resto de productos de servidor de Microsoft, incluidos Exchange 2013 y SharePoint Server, admiten el protocolo Open Authorization (OAuth) para la autorización y la autenticación de servidor a servidor. Para obtener más detalles, vea [Administración de la autenticación servidor a servidor (Oauth) y las aplicaciones de socio en Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) en la documentación sobre implementación o sobre operaciones.

Para conexiones desde clientes que ejecuten Sistema operativo Windows 7, Sistema operativo Windows Server 2008 R2 y Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 incluye compatibilidad (pero no la necesita) con certificados firmados mediante la función de hash de cifrado SHA-256. Para permitir el acceso externo mediante SHA-256, una entidad de certificación pública que usa SHA-256 emite el certificado externo.

Para más información sobre los requerimientos de certificados, consulte [Requisitos de la infraestructura de certificados para Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) en la documentación de planeamiento. Para más información sobrel uso de caracteres de comodines con certificados, consulte [Compatibilidad de certificado de comodín en Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) en la documentación sobre compatibilidad.

