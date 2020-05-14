---
title: Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socio en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 'Resumen: administre OAuth y las aplicaciones de socio en Skype empresarial Server.'
ms.openlocfilehash: f784dd0a2dab05fb3b97497fab7d3866dda1a753
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221674"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socio en Skype empresarial Server
 
**Resumen:** Administre las aplicaciones de asociados y OAuth en Skype empresarial Server.
  
Skype empresarial Server debe ser capaz de comunicarse de forma segura y sin problemas con otras aplicaciones y productos de servidor. Por ejemplo, puede configurar Skype empresarial Server para que los datos de contacto o los datos de archivado se almacenen en Microsoft Exchange Server 2013; sin embargo, esto solo se puede hacer si Skype empresarial Server y Exchange pueden comunicarse entre sí de forma segura. Del mismo modo, puede programar una conferencia de Skype empresarial Server desde Office Web Apps Server; de nuevo, esto solo puede hacerse si los dos servidores (SharePoint y Skype empresarial Server) confían entre sí. Aunque es posible usar un mecanismo de autenticación para la comunicación entre Skype empresarial Server y Exchange, pero un mecanismo independiente para la comunicación de Skype empresarial Server y SharePoint, un enfoque mejor y más eficaz es usar un método estandarizado para toda la autenticación y autorización de servidor a servidor.
  
Usar un único método estandarizado para la autenticación de servidor a servidor es el enfoque que lleva a cabo Skype empresarial Server. En la versión 2013 de los servidores de Office, Skype empresarial Server (así como otros productos de servidor de Microsoft, incluido Exchange Server y SharePoint Server) admiten el protocolo OAuth (Open Authorization) para la autenticación y autorización de servidor a servidor. Con OAuth, un protocolo de autorización estándar usado por varios sitios web principales, las credenciales de usuario y las contraseñas no se pasan de un equipo a otro. En su lugar, la autenticación y la autorización se basan en el intercambio de tokens de seguridad; Estos tokens conceden acceso a un conjunto específico de recursos durante un período de tiempo específico.
  
La autenticación OAuth suele implicar a tres partes: un único servidor de autorización y los dos dominios que deben comunicarse entre sí. (También puede realizar la autenticación de servidor a servidor sin usar un servidor de autorización, un proceso que se tratará más adelante en este documento). El servidor de autorización emite los tokens de seguridad (también conocido como un servidor de token de seguridad) a los dos territorios que deben comunicarse; Estos tokens comprueban que las comunicaciones que se originan en un dominio Kerberos deben ser de confianza para el otro dominio. Por ejemplo, el servidor de autorización puede emitir tokens que comprueban que los usuarios de un dominio Kerberos específico de Skype empresarial Server pueden tener acceso a un dominio Kerberos de Exchange específico y viceversa.
  
> [!NOTE]
> Un dominio es un contenedor de seguridad. De forma predeterminada, Skype empresarial Server usa su dominio SIP predeterminado como su dominio de OAuth. Los espacios de nombres SIP adicionales se agregan a la lista de nombres alternativos de sujeto en el certificado de OAuth. 
  
Skype empresarial Server admite tres escenarios de autenticación de servidor a servidor. Con Skype empresarial Server, puede:
  
- Configure la autenticación de servidor a servidor entre una instalación local de Skype empresarial Server y una instalación local de Exchange y/o SharePoint Server.
    
- Configure la autenticación de servidor a servidor entre un par de componentes de Microsoft 365 u Office 365 (por ejemplo, entre Microsoft Exchange Server y Skype empresarial Server, o entre Skype empresarial Server y SharePoint).
    
- Configure la autenticación de servidor a servidor en un entorno entre locales (es decir, autenticación de servidor a servidor entre un servidor local y un componente de Microsoft 365 u Office 365).
    
Tenga en cuenta que, en este momento, solo Exchange 2013, SharePoint Server, Lync Server 2013, Skype empresarial Server 2015 y Skype empresarial 2019 admiten la autenticación de servidor a servidor; Si no está ejecutando uno de estos servidores, no podrá implementar completamente la autenticación de OAuth.
  
También debe señalarse que la autenticación de servidor a servidor es opcional: si Skype empresarial Server no necesita comunicarse con otros servidores (como Exchange), la autenticación de servidor a servidor se puede omitir por completo. Si la autenticación de servidor a servidor ya está configurada para Lync Server 2013 y otras aplicaciones, no es necesario volver a realizarla en Skype empresarial Server. 
  
Sin embargo, la autenticación de servidor a servidor es necesaria si desea usar algunas de las características de Skype empresarial Server, como el "almacén de contactos unificado". Con el almacén de contactos unificado, la información de contacto de Skype empresarial Server se almacena en Exchange en lugar de en Skype empresarial Server; Esto permite a los usuarios tener un único conjunto de contactos fácilmente accesibles desde dentro de Skype empresarial, Outlook o Outlook Web Access. Debido a que el almacén de contactos unificado requiere Skype empresarial Server para compartir información con Exchange, debe usar la autenticación de servidor a servidor para poder implementar la característica. La autenticación de servidor a servidor también es necesaria si elige usar el archivado de Exchange, en el que las transcripciones de las sesiones de mensajería instantánea se guardan como mensajes de correo electrónico de Exchange en lugar de como registros de base de datos individuales.
  
Para que la versión de Skype empresarial Server para Microsoft 365 o Office 365 se comunique con su contraparte de Exchange, Skype empresarial Server debe obtener primero un token de seguridad del servidor de autorización. A continuación, Skype empresarial Server usa ese token de seguridad para identificarse en Exchange. Las versiones Microsoft 365 o Office 365 de Exchange deben pasar por el mismo proceso para comunicarse con Skype empresarial Server.
  
Sin embargo, no es necesario utilizar ningún servidor de token de terceros para la autenticación local de servidor a servidor entre dos servidores de Microsoft. Los productos de servidor, como Skype empresarial Server y Exchange, tienen un servidor de tokens integrado que se puede usar para fines de autenticación con otros servidores de Microsoft (como SharePoint Server) que admiten la autenticación de servidor a servidor. Por ejemplo, Skype empresarial Server puede emitir y firmar un token de seguridad por sí mismo y, a continuación, usar ese token para comunicarse con Exchange. En un caso como este, no se necesita ningún servidor de tokens de terceros.
  
Para configurar la autenticación de servidor a servidor para una implementación local de Skype empresarial Server, debe hacer dos cosas:
  
- Asigne un certificado al emisor de tokens integrado de Skype empresarial Server.
    
- Configure el servidor con el que se comunicará Skype empresarial Server para que sea una "aplicación de socio". Por ejemplo, si Skype empresarial Server necesita comunicarse con Exchange, tendrá que configurar Exchange para que sea una aplicación de socio.
    
> [!NOTE]
> Una "aplicación de socio" es cualquier aplicación con la que Skype empresarial Server pueda intercambiar directamente tokens de seguridad, sin tener que pasar por un servidor de token de seguridad de terceros. 
  
Tenga en cuenta que OAuth es una parte principal del producto y no se puede deshabilitar ni quitar.
  
## <a name="see-also"></a>Vea también

[Asignar un certificado de autenticación de servidor a servidor a Skype empresarial Server](assign-a-server-to-server-certificate.md)
  
[Configurar un entorno híbrido en Skype empresarial Server](configure-a-hybrid-environment.md)
