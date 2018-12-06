---
title: "Autenticación servidor a servidor (Oauth) y aplicaciones de socio en Lync Server 2013"
TOCTitle: "Gest. de l’auth. serv. à serv. (Oauth) et des app. partenaires dans LS 2013"
ms:assetid: 38848373-c8c6-4097-bf7f-699fe471348d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204817(v=OCS.15)
ms:contentKeyID: 48274931
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Administración de la autenticación servidor a servidor (Oauth) y las aplicaciones de socio en Lync Server 2013

 

_**Última modificación del tema:** 2015-05-14_

Microsoft Lync Server 2013 debe permitir la comunicación segura y sin problemas con el resto de aplicaciones y productos de servidor. Por ejemplo, puede configurar Lync Server 2013 para que los datos de archivado y de contactos se almacenen en Microsoft Exchange Server 2013; sin embargo, esto solo es posible si Lync Server y Exchange pueden comunicarse entre sí de forma segura. Del mismo modo, puede programar una conferencia de Lync Server desde Microsoft SharePoint Server. Sin embargo, de nuevo esto solo es posible si los dos servidores (SharePoint y Lync Server) tienen una relación de confianza mutua. Aunque es posible utilizar un mecanismo de autenticación para la comunicación de Lync a Exchange y otro mecanismo distinto para la comunicación de Lync a SharePoint, el uso de un método estándar para todas las autorizaciones y autenticaciones de servidor a servidor es un enfoque mucho más eficaz.

El uso de un único método estándar para la autenticación de servidor a servidor es el enfoque que adopta Lync Server 2013. En la versión de 2013, Lync Server 2013 (así como para el resto de productos de servidor de Microsoft, incluidos Exchange 2013 y Microsoft SharePoint Server) admite el protocolo Open Authorization (OAuth) para la autorización y la autenticación de servidor a servidor. OAuth permite utilizar un protocolo de autorización estándar en un gran número de sitios web principales, ya que las contraseñas y las credenciales de los usuarios no se transmiten entre los equipos. En su lugar, la autenticación y la autorización se basan en el intercambio de tokens de seguridad. Dichos tokens facilitan el acceso a un conjunto de recursos específicos durante un periodo específico.

La autenticación OAuth implica a tres partes: un único servidor de autorización y dos dominios que deben comunicarse entre sí. (También se puede llevar a cabo la autenticación de servidor a servidor a través de un servidor de autorización, proceso que se tratará más adelante en este documento.) El servidor de autorización (también conocido como servidor de tokens de seguridad) emite tokens de seguridad a los dos dominios que se comunican entre sí. Dichos tokens comprueban que las comunicaciones procedentes de un dominio son de confianza para el otro dominio. Por ejemplo, el servidor de autorización puede emitir tokens que comprueben que los usuarios de un dominio de Lync Server 2013 específico puedan tener acceso a un dominio de Exchange 2013 determinado y viceversa.


> [!NOTE]
> Un dominio es un contenedor de seguridad. De forma predeterminada, Lync Server 2013 usa el dominio SIP predeterminado como dominio OAuth.



Lync Server 2013 admite tres escenarios de autenticación de servidor a servidor. Con Lync Server 2013 puede llevar a cabo lo siguiente:

  - Configurar la autenticación de servidor a servidor entre una instalación local de Lync Server 2013 y una instalación local de Exchange 2013 y/o Microsoft SharePoint Server.

  - Configurar la autenticación de servidor a servidor entre un par de componentes de Office 365 (por ejemplo, entre Microsoft Exchange y Microsoft Lync Server; o entre Microsoft Lync Server y Microsoft SharePoint).

  - Configurar la autenticación de servidor a servidor en un entorno de múltiples instalaciones locales (es decir, autenticación de servidor a servidor entre un servidor local y un componente de Office 365).

Tenga en cuenta que en estos momentos, solo Exchange 2013, SharePoint Server y Lync Server 2013 admiten la autenticación de servidor a servidor. Si no ejecuta ninguno de estos servidores, no podrá implementar completamente la autenticación OAuth.

También debe tenerse en cuenta que no es necesario utilizar la autenticación de servidor a servidor, ya que no es necesaria para la implementación de Lync Server 2013. Si Lync Server 2013 no necesita comunicarse con otros servidores (como, por ejemplo Exchange 2013), no será necesaria la autenticación de servidor a servidor.

Sin embargo, la autenticación de servidor a servidor es necesaria si desea utilizar algunas de las nuevas características de Lync Server como, por ejemplo, el "almacén de contactos unificado". Con el almacén de contactos unificado, la información de contactos de Lync Server 2013 se almacena en Exchange 2013 en lugar de en Lync Server. Esto permite a los usuarios disponer de un único conjunto de contactos disponibles desde Lync, Microsoft Outlook o Microsoft Outlook Web Access. Puesto que el almacén de contactos unificado requiere que Lync Server 2013 comparta información con Exchange 2013, debe utilizar la autenticación de servidor a servidor para implementar esta característica. La autenticación de servidor a servidor también es necesaria si opta por utilizar el archivado en Exchange, donde las transcripciones de las sesiones de mensajería instantánea se guardan como mensajes de correo electrónico de Exchange 2013 y no como registros individuales de bases de datos.

Para que la versión de Office 365 de Lync Server se comunique con la otra parte de Exchange, Lync Server 2013 deberá obtener antes un token de seguridad del servidor de autorización. Lync Server utilizará dicho token de seguridad para identificarse en Exchange. La versión de Office 365 de Exchange debe seguir el mismo proceso para comunicarse con Lync Server 2013.

Sin embargo, no es necesario utilizar ningún servidor de token de terceros para la autenticación local de servidor a servidor entre dos servidores de Microsoft. Los productos de servidor como, por ejemplo, Lync Server 2013 y Exchange 2013 disponen de un servidor de tokens integrado que puede utilizarse para la autenticación con otros servidores de Microsoft (como, por ejemplo, el servidor de SharePoint) que admite la autenticación de servidor a servidor. Por ejemplo, Lync Server 2013 puede emitir y firmar un token de seguridad por sí mismo para, a continuación, utilizarlo para comunicarse con Exchange 2013. No se necesita ningún servidor de tokens de terceros para casos similares a este.

Para configurar la autenticación de servidor a servidor en implementaciones locales de Lync Server 2013, debe llevar a cabo dos tareas:

  - Asignar un certificado al emisor de tokens integrado de Lync Server.

  - Configurar el servidor con el que se comunicará Lync Server 2013 como "aplicación de socio". Por ejemplo, si Lync Server 2013 necesita comunicarse con Exchange 2013, necesitará configurar Exchange como aplicación de socio.


> [!NOTE]
> Una "aplicación de socio" es una aplicación con la que Lync Server 2013 puede intercambiar directamente tokens de seguridad, sin tener que pasar por ningún servidor de tokens de seguridad de terceros.



Tenga en cuenta que OAuth es una parte fundamental del producto y no se puede desactivar ni eliminar.

## Vea también

#### Conceptos

[Asignación de un certificado de autenticación servidor a servidor a Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[Configuración de Microsoft Lync Server 2013 en un entorno externo](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)

