---
title: Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socio
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing server-to-server authentication (OAuth) and partner applications
ms:assetid: 38848373-c8c6-4097-bf7f-699fe471348d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204817(v=OCS.15)
ms:contentKeyID: 48183894
ms.date: 05/15/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0d554bc935ea24f7098472a5c893f58dc717839
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a>Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socio en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-05-14_

Microsoft Lync Server 2013 debe ser capaz de comunicarse de forma segura y sin problemas con otras aplicaciones y productos de servidor. Por ejemplo, puede configurar Lync Server 2013 para que los datos de contacto y los datos de archivado se almacenen en Microsoft Exchange Server 2013; sin embargo, esto solo se puede hacer si Lync Server y Exchange pueden comunicarse entre sí de forma segura. Del mismo modo, puede programar una conferencia de Lync Server desde Microsoft SharePoint Server; de nuevo, sin embargo, esto solo se puede hacer si los dos servidores (SharePoint y Lync Server) confían entre sí. Si bien es posible usar un mecanismo de autenticación para la comunicación de Lync a Exchange y un mecanismo independiente para la comunicación entre Lync y SharePoint, un enfoque mejor y más eficaz es usar un método estandarizado para todos los servidores de servidor a servidor. autenticación y autorización.

Usar un único método estandarizado para la autenticación de servidor a servidor es el método que lleva a cabo Lync Server 2013. Para la versión 2013, Lync Server 2013 (así como otros productos de Microsoft Server, incluidos Exchange 2013 y Microsoft SharePoint Server) admiten el protocolo OAuth (Open Authorization) para la autenticación y autorización de servidor a servidor. Con OAuth, un protocolo de autorización estándar usado por varios sitios web principales, las credenciales de usuario y las contraseñas no se pasan de un equipo a otro. En su lugar, la autenticación y la autorización se basan en el intercambio de tokens de seguridad; Estos tokens conceden acceso a un conjunto específico de recursos durante un período de tiempo específico.

La autenticación OAuth suele implicar a tres partes: un único servidor de autorización y los dos dominios que deben comunicarse entre sí. (También puede realizar la autenticación de servidor a servidor sin usar un servidor de autorización, un proceso que se tratará más adelante en este documento). El servidor de autorización emite los tokens de seguridad (también conocido como un servidor de token de seguridad) a los dos territorios que deben comunicarse; Estos tokens comprueban que las comunicaciones que se originan en un dominio Kerberos deben ser de confianza para el otro dominio. Por ejemplo, el servidor de autorización podría emitir tokens que comprueban que los usuarios de un dominio Kerberos 2013 específico de Lync Server pueden obtener acceso a un dominio de Exchange 2013 especificado y viceversa.

<div>


> [!NOTE]
> Un dominio es un contenedor de seguridad. De forma predeterminada, Lync Server 2013 usa su dominio SIP predeterminado como su dominio de OAuth. Los espacios de nombres SIP adicionales se agregan a la lista de nombres alternativos de sujeto en el certificado de OAuth.



</div>

Lync Server 2013 admite tres escenarios de autenticación de servidor a servidor. Con Lync Server 2013 puede:

  - Configure la autenticación de servidor a servidor entre una instalación local de Lync Server 2013 y una instalación local de Exchange 2013 o Microsoft SharePoint Server.

  - Configure la autenticación de servidor a servidor entre un par de componentes de Office 365 (por ejemplo, entre Microsoft Exchange y Microsoft Lync Server, o entre Microsoft Lync Server y Microsoft SharePoint).

  - Configurar la autenticación de servidor a servidor en un entorno de múltiples instalaciones locales (es decir, autenticación de servidor a servidor entre un servidor local y un componente de Office 365).

Tenga en cuenta que, en este momento, solo Exchange 2013, SharePoint Server y Lync Server 2013 admiten la autenticación de servidor a servidor; Si no está ejecutando uno de estos servidores, no podrá implementar completamente la autenticación de OAuth.

También debe señalarse que no es necesario usar la autenticación de servidor a servidor: no se requiere la autenticación de servidor a servidor para implementar Lync Server 2013. Si Lync Server 2013 no necesita comunicarse con otros servidores (como Exchange 2013), no se necesita la autenticación de servidor a servidor.

Sin embargo, la autenticación de servidor a servidor es necesaria si desea usar algunas de las nuevas características de Lync Server, como el "almacén de contactos unificado". Con el almacén de contactos unificado, la información de contacto de Lync Server 2013 se almacena en Exchange 2013 en lugar de en Lync Server; Esto permite a los usuarios tener un único conjunto de contactos fácilmente accesibles desde dentro de Lync, Microsoft Outlook o Microsoft Outlook Web Access. Como el almacén de contactos unificado requiere Lync Server 2013 para compartir información con Exchange 2013, debe usar la autenticación de servidor a servidor para implementar la característica. La autenticación de servidor a servidor también es necesaria si elige usar el archivado de Exchange, en el que las transcripciones de las sesiones de mensajería instantánea se guardan como correos electrónicos de Exchange 2013 en lugar de como registros de base de datos individuales.

Para que la versión de Office 365 de Lync Server se comunique con su homólogo de Exchange, Lync Server 2013 debe obtener primero un token de seguridad del servidor de autorización. Lync Server luego usa ese token de seguridad para identificarse en Exchange. La versión Office 365 de Exchange debe pasar por el mismo proceso para comunicarse con Lync Server 2013.

Sin embargo, no es necesario utilizar ningún servidor de token de terceros para la autenticación local de servidor a servidor entre dos servidores de Microsoft. Los productos de servidor como Lync Server 2013 y Exchange 2013 tienen un servidor de tokens integrado que se puede usar para fines de autenticación con otros servidores de Microsoft (como SharePoint Server) que admiten la autenticación de servidor a servidor. Por ejemplo, Lync Server 2013 puede emitir y firmar un token de seguridad por sí mismo, y después usarlo para comunicarse con Exchange 2013. En un caso como este, no se necesita ningún servidor de tokens de terceros.

Para configurar la autenticación de servidor a servidor para una implementación local de Lync Server 2013, debe hacer dos cosas:

  - Asignar un certificado al emisor de tokens integrado de Lync Server.

  - Configure el servidor con el que se comunicará Lync Server 2013 para que sea una aplicación de socio. Por ejemplo, si Lync Server 2013 necesita comunicarse con Exchange 2013, tendrá que configurar Exchange para que sea una aplicación de socio.

<div>


> [!NOTE]
> Una "aplicación de socio" es cualquier aplicación con la que Lync Server 2013 pueda intercambiar directamente tokens de seguridad, sin tener que pasar por un servidor de token de seguridad de terceros.



</div>

Tenga en cuenta que OAuth es una parte principal del producto y no se puede deshabilitar ni quitar.

<div>

## <a name="see-also"></a>Vea también


[Asignar un certificado de autenticación de servidor a servidor a Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[Configuración de Microsoft Lync Server 2013 en un entorno entre entornos](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

