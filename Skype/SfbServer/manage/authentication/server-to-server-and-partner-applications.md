---
title: Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socios en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 'Resumen: administre aplicaciones de socios y OAuth en Skype empresarial Server.'
ms.openlocfilehash: 37c2af8a089bcae4b974761616e1ecd67c9e500b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297571"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socios en Skype empresarial Server
 
**Resumen:** Administre aplicaciones de socios y OAuth en Skype empresarial Server.
  
Skype empresarial Server debe poder comunicarse de manera segura y sin problemas con otras aplicaciones y productos de servidor. Por ejemplo, puede configurar Skype empresarial Server para que los datos de los contactos o los datos de archivado se almacenen en Microsoft Exchange Server 2013; sin embargo, esto solo se puede hacer si Skype empresarial Server y Exchange pueden comunicarse con seguridad entre sí. Del mismo modo, puede programar una conferencia de Skype empresarial Server desde Office Web Apps Server; de nuevo, esto solo se puede hacer si los dos servidores (SharePoint y Skype empresarial Server) confían entre sí. Aunque es posible usar un mecanismo de autenticación para la comunicación entre Skype empresarial Server y Exchange, pero un mecanismo separado para Skype empresarial Server y la comunicación de SharePoint, un enfoque mejor y más eficaz es usar una método estándar para todas las autenticaciones y autorizaciones de servidor a servidor.
  
Usar un único método estándar para la autenticación de servidor a servidor es el enfoque que toma Skype empresarial Server. A partir de la versión 2013 de Office servers, Skype empresarial Server (así como otros productos de Microsoft Server, incluidos Exchange Server y SharePoint Server) admiten el protocolo OAuth (Open Authorization) para la autenticación de servidor a servidor y autorización. Con OAuth, un protocolo de autorización estándar usado por varios sitios web grandes, las credenciales de usuario y las contraseñas no pasan de un equipo a otro. En su lugar, la autenticación y la autorización se basan en el intercambio de tokens de seguridad; Estos tokens conceden acceso a un conjunto de recursos específico durante un período de tiempo específico.
  
Por lo general, la autenticación de OAuth implica tres partes: un único servidor de autorización y los dos territorios que necesitan comunicarse entre sí. (También puede realizar la autenticación de servidor a servidor sin usar un servidor de autorización, un proceso que se tratará más adelante en este documento). El servidor de autorización emite los tokens de seguridad (también conocido como servidor de token de seguridad) a los dos territorios que necesitan comunicarse; Estos tokens verifican que el otro dominio confía en las comunicaciones que se originan en un dominio. Por ejemplo, es posible que el servidor de autorización emita tokens que comprueben que los usuarios de un territorio específico de Skype empresarial Server pueden obtener acceso a un dominio específico de Exchange y viceversa.
  
> [!NOTE]
> Un dominio es un contenedor de seguridad. De forma predeterminada, Skype empresarial Server usa su dominio SIP predeterminado como su territorio OAuth. Se agregan espacios de nombres SIP a la lista Nombre alternativo del sujeto en el certificado OAuth. 
  
Skype empresarial Server admite tres escenarios de autenticación de servidor a servidor. Con Skype empresarial Server, puede hacer lo siguiente:
  
- Configure la autenticación de servidor a servidor entre una instalación local de Skype empresarial Server y una instalación local de Exchange o de SharePoint Server.
    
- Configure la autenticación de servidor a servidor entre un par de componentes de Office 365 (por ejemplo, entre Microsoft Exchange Server y Skype empresarial Server, o entre Skype empresarial Server y SharePoint).
    
- Configurar la autenticación de servidor a servidor en un entorno entre locales (es decir, la autenticación de servidor a servidor entre un servidor local y un componente de Office 365).
    
Tenga en cuenta que, en este momento, solo Exchange 2013, SharePoint Server, Lync Server 2013, Skype empresarial Server 2015 y Skype empresarial 2019 son compatibles con la autenticación de servidor a servidor; Si no está ejecutando uno de estos servidores, no podrá implementar completamente la autenticación de OAuth.
  
También se debe señalar que la autenticación de servidor a servidor es opcional: si Skype empresarial Server no necesita comunicarse con otros servidores (como Exchange), la autenticación de servidor a servidor se puede omitir por completo. Si la autenticación de servidor a servidor ya está configurada para Lync Server 2013 y otras aplicaciones, no es necesario volver a realizarla en Skype empresarial Server. 
  
Sin embargo, se necesita la autenticación de servidor a servidor si desea usar algunas de las características de Skype empresarial Server, como "almacén de contactos unificado". Con el almacenamiento de contactos unificado, la información de contacto de Skype empresarial Server se almacena en Exchange en lugar de en Skype empresarial Server; Esto permite a los usuarios tener un único conjunto de contactos con acceso fácil desde dentro de Skype empresarial, Outlook o Outlook Web Access. Debido a que el almacén de contactos unificado requiere Skype empresarial Server para compartir información con Exchange, debe usar la autenticación de servidor a servidor para implementar la característica. También se necesita la autenticación de servidor a servidor si elige usar el archivado de Exchange, en el que las transcripciones de las sesiones de mensajería instantánea se guardan como correos electrónicos de Exchange en lugar de como registros de la base de datos individual.
  
Para que la versión de Office 365 de Skype empresarial Server se comunique con su equivalente de Exchange, Skype empresarial Server primero debe obtener un token de seguridad del servidor de autorización. Después, Skype empresarial Server usa ese token de seguridad para identificarse en Exchange. La versión de Office 365 de Exchange debe pasar por el mismo proceso para poder comunicarse con Skype empresarial Server.
  
Sin embargo, para una autenticación de servidor a servidor local entre dos servidores Microsoft, no es necesario usar ningún servidor de tokens de otro proveedor. Los productos de servidor, como Skype empresarial Server y Exchange, tienen un servidor de tokens integrado que se puede usar para fines de autenticación con otros servidores de Microsoft (como SharePoint Server) que admiten la autenticación de servidor a servidor. Por ejemplo, Skype empresarial Server puede emitir e iniciar por sí mismo un token de seguridad y, a continuación, usar ese token para comunicarse con Exchange. En este caso, no es necesario usar ningún servidor de tokens de un tercero.
  
Para configurar la autenticación de servidor a servidor para una implementación local de Skype empresarial Server, debe hacer dos cosas:
  
- Asigne un certificado al emisor de tokens integrado de Skype empresarial Server.
    
- Configure el servidor con el que se comunicará Skype empresarial Server para que sea una "aplicación asociada". Por ejemplo, si Skype empresarial Server necesita comunicarse con Exchange, tendrá que configurar Exchange para que sea una aplicación de socio.
    
> [!NOTE]
> Una "aplicación asociada" es cualquier aplicación en la que Skype empresarial Server pueda intercambiar directamente tokens de seguridad con, sin tener que pasar por un servidor de token de seguridad de terceros. 
  
Tenga en cuenta que OAuth es una parte fundamental del producto y no se puede desactivar ni eliminar.
  
## <a name="see-also"></a>Vea también

[Asignar un certificado de autenticación de servidor a servidor a Skype empresarial Server](assign-a-server-to-server-certificate.md)
  
[Configurar un entorno híbrido en Skype empresarial Server](configure-a-hybrid-environment.md)
