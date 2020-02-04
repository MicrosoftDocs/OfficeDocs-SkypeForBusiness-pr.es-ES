---
title: Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socios
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
ms.openlocfilehash: 01de2856b8923fff76cf33dda7d7e6ba21889c2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a>Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socio en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-05-14_

Microsoft Lync Server 2013 debe ser capaz de comunicarse de manera segura y sin problemas con otras aplicaciones y productos de servidor. Por ejemplo, puede configurar Lync Server 2013 para que los datos de los contactos o los datos de archivado se almacenen en Microsoft Exchange Server 2013; sin embargo, esto solo se puede hacer si Lync Server y Exchange pueden comunicarse con seguridad entre sí. Del mismo modo, puede programar una conferencia de Lync Server desde Microsoft SharePoint Server; de nuevo, sin embargo, esto solo se puede hacer si los dos servidores (SharePoint y Lync Server) confían entre sí. Aunque es posible usar un mecanismo de autenticación para la comunicación entre usuarios de Lync y un mecanismo independiente para la comunicación entre usuarios de Lync, un enfoque mejor y más eficaz es usar un método estándar para todos los servidores autenticación y autorización.

Usar un único método estándar para la autenticación de servidor a servidor es el método que toma Lync Server 2013. En el caso de la versión 2013, Lync Server 2013 (así como otros productos de Microsoft Server, incluidos Exchange 2013 y Microsoft SharePoint Server) son compatibles con el protocolo OAuth (Open Authorization) para la autenticación y la autorización de servidor a servidor. Con OAuth, un protocolo de autorización estándar usado por varios sitios web grandes, las credenciales de usuario y las contraseñas no pasan de un equipo a otro. En su lugar, la autenticación y la autorización se basan en el intercambio de tokens de seguridad; Estos tokens conceden acceso a un conjunto de recursos específico durante un período de tiempo específico.

Por lo general, la autenticación de OAuth implica tres partes: un único servidor de autorización y los dos territorios que necesitan comunicarse entre sí. (También puede realizar la autenticación de servidor a servidor sin usar un servidor de autorización, un proceso que se tratará más adelante en este documento). El servidor de autorización emite los tokens de seguridad (también conocido como servidor de token de seguridad) a los dos territorios que necesitan comunicarse; Estos tokens verifican que el otro dominio confía en las comunicaciones que se originan en un dominio. Por ejemplo, es posible que el servidor de autorización emita tokens que comprueben que los usuarios de un territorio específico de Lync Server 2013 pueden tener acceso a un dominio Kerberos 2013 específico y viceversa.

<div>


> [!NOTE]
> Un dominio es un contenedor de seguridad. De forma predeterminada, Lync Server 2013 usa su dominio SIP predeterminado como su dominio de OAuth. Se agregan espacios de nombres SIP a la lista Nombre alternativo del sujeto en el certificado OAuth.



</div>

Lync Server 2013 admite tres escenarios de autenticación de servidor a servidor. Con Lync Server 2013 puede:

  - Configure la autenticación de servidor a servidor entre una instalación local de Lync Server 2013 y una instalación local de Exchange 2013 o Microsoft SharePoint Server.

  - Configure la autenticación de servidor a servidor entre un par de componentes de Office 365 (por ejemplo, entre Microsoft Exchange y Microsoft Lync Server, o entre Microsoft Lync Server y Microsoft SharePoint).

  - Configurar la autenticación de servidor a servidor en un entorno entre locales (es decir, la autenticación de servidor a servidor entre un servidor local y un componente de Office 365).

Tenga en cuenta que, en este momento, solo Exchange 2013, SharePoint Server y Lync Server 2013 son compatibles con la autenticación de servidor a servidor; Si no está ejecutando uno de estos servidores, no podrá implementar completamente la autenticación de OAuth.

También debe señalarse que no es necesario usar autenticación de servidor a servidor: la autenticación de servidor a servidor no es necesaria para implementar Lync Server 2013... Si Lync Server 2013 no necesita comunicarse con otros servidores (como Exchange 2013), no se necesita la autenticación de servidor a servidor.

Sin embargo, se necesita la autenticación de servidor a servidor si desea usar algunas de las nuevas características de Lync Server, como el "almacén de contactos unificado". Con el almacenamiento de contactos unificado, la información de contacto de Lync Server 2013 se almacena en Exchange 2013 en lugar de en Lync Server; Esto permite que los usuarios tengan un único conjunto de contactos accesible fácilmente desde Lync, Microsoft Outlook o Microsoft Outlook Web Access. Puesto que el almacén de contactos unificado requiere Lync Server 2013 para poder compartir información con Exchange 2013, debe usar la autenticación de servidor a servidor para implementar la característica. También se necesita la autenticación de servidor a servidor si elige usar el archivado de Exchange, en el que las transcripciones de las sesiones de mensajería instantánea se guardan como correos electrónicos de Exchange 2013 en lugar de como registros de base de datos individuales.

Para que la versión de Office 365 de Lync Server se comunique con su equivalente de Exchange, Lync Server 2013 primero debe obtener un token de seguridad del servidor de autorización. A continuación, Lync Server usa ese token de seguridad para identificarse en Exchange. La versión de Office 365 de Exchange debe pasar por el mismo proceso para poder comunicarse con Lync Server 2013.

Sin embargo, para una autenticación de servidor a servidor local entre dos servidores Microsoft, no es necesario usar ningún servidor de tokens de otro proveedor. Los productos de servidor, como Lync Server 2013 y Exchange 2013, tienen un servidor de tokens integrado que se puede usar para fines de autenticación con otros servidores de Microsoft (como SharePoint Server) que admiten autenticación de servidor a servidor. Por ejemplo, Lync Server 2013 puede emitir e iniciar por sí mismo un token de seguridad y, a continuación, usar ese token para comunicarse con Exchange 2013. En este caso, no es necesario usar ningún servidor de tokens de un tercero.

Para configurar la autenticación de servidor a servidor para una implementación local de Lync Server 2013 debe hacer dos cosas:

  - Asigne un certificado al emisor de token integrado de Lync Server.

  - Configure el servidor al que se comunicará Lync Server 2013 para que sea una "aplicación asociada". Por ejemplo, si Lync Server 2013 necesita comunicarse con Exchange 2013, tendrá que configurar Exchange para que sea una aplicación de socio.

<div>


> [!NOTE]
> Una "aplicación asociada" es cualquier aplicación con la que Lync Server 2013 pueda intercambiar directamente tokens de seguridad con, sin tener que pasar por un servidor de token de seguridad de terceros.



</div>

Tenga en cuenta que OAuth es una parte fundamental del producto y no se puede desactivar ni eliminar.

<div>

## <a name="see-also"></a>Vea también


[Asignación de un certificado de autenticación de servidor a servidor a Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[Configuración de Microsoft Lync Server 2013 en un entorno entre entornos](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

