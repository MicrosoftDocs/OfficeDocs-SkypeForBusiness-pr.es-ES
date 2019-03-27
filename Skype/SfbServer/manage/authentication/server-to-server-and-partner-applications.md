---
title: Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones asociadas en Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 'Resumen: Administrar aplicaciones de OAuth y socio de Skype para Business Server.'
ms.openlocfilehash: 77fd070ace850035d129dc247decdcf7988219cf
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893149"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones asociadas en Skype para Business Server
 
**Resumen:** Administrar aplicaciones de OAuth y socio de Skype para Business Server.
  
Skype para Business Server debe ser capaz de forma segura y sin ningún problema, comunicarse con otras aplicaciones y productos de servidor. Por ejemplo, puede configurar Skype para Business Server por lo ponerse en contacto con datos o datos de archivado se almacena en Microsoft Exchange Server 2013; Sin embargo, esto sólo es posible si Skype para Business Server y Exchange es capaces de forma segura comunicarse entre sí. Del mismo modo, puede programar una Skype para conferencia de Business Server desde dentro de Office Web Apps Server; una vez más, esto sólo es posible si confían en los dos servidores (SharePoint y Skype para Business Server) entre sí. Aunque es posible usar un mecanismo de autenticación para la comunicación entre Skype para Business Server y Exchange, pero un mecanismo independiente para Skype para la comunicación de Business Server y SharePoint, un enfoque mejor y más eficiente consiste en usar un método estándar para todos los de autorización y autenticación de servidor a servidor.
  
Mediante una sola, el método estándar para la autenticación de servidor a servidor es el enfoque tomado por Skype para Business Server. Introducción a los servidores de Office 2013 versión, Skype para Business Server (así como otros productos de Microsoft Server, incluido Exchange Server y SharePoint Server) admite el protocolo OAuth (Open Authorization) para la autenticación de servidor a servidor y autorización. Con OAuth, un protocolo de autorización estándar utilizado por un número de sitios Web principales, las credenciales de usuario y contraseñas no se pasan de un equipo a otro. En su lugar, autenticación y autorización se basa en el intercambio de tokens de seguridad; Estos tokens conceden acceso a un conjunto específico de recursos para un período de tiempo específico.
  
Normalmente, la autenticación de OAuth implica tres partes: un servidor único de autorización y los dos dominios que necesitan comunicarse entre sí. (Se puede hacer autenticación de servidor a servidor sin usar un servidor de autorización, un proceso que se tratarán más adelante en este documento.) Los tokens de seguridad emitidos por el servidor de autorización (también conocido como un servidor token de seguridad) a los dos dominios que necesitan comunicarse; Estos tokens comprobación que las comunicaciones que se originan desde un territorio deben ser de confianza por el otro dominio. Por ejemplo, el servidor de autorización podría emitir tokens que comprobación que los usuarios de un Skype específico para el dominio Kerberos de Business Server tienen acceso a un dominio Kerberos de Exchange especificado y viceversa.
  
> [!NOTE]
> Un dominio es un contenedor de seguridad. De forma predeterminada, Skype para Business Server usa su dominio SIP de forma predeterminada como su territorio OAuth. Se agregan espacios de nombres SIP a la lista Nombre alternativo del sujeto en el certificado OAuth. 
  
Skype para Business Server es compatible con tres escenarios de autenticación de servidor a servidor. Con Skype para Business Server, se puede:
  
- Configurar la autenticación de servidor a servidor entre una instalación local de Skype para Business Server y una instalación local de Exchange o del servidor de SharePoint.
    
- Configurar la autenticación de servidor a servidor entre un par de componentes de Office 365 (por ejemplo, entre Microsoft Exchange Server y Skype para Business Server, o entre Skype para Business Server y SharePoint).
    
- Configurar la autenticación de servidor a servidor en un entorno entre locales (es decir, autenticación de servidor a servidor entre un servidor local y un componente de Office 365).
    
Tenga en cuenta, en este momento, sólo Exchange 2013, SharePoint Server, Lync Server 2013, Skype para Business Server 2015 y Skype para profesionales 2019 admiten la autenticación de servidor a servidor; Si no está ejecutando uno de estos servidores, no podrá implementar completamente la autenticación de OAuth.
  
Debe también se señaló ese servidor a servidor autenticación es opcional: si Skype para Business Server no es necesario para comunicarse con otros servidores (por ejemplo, Exchange), a continuación, se puede omitir totalmente autenticación de servidor a servidor. Si la autenticación de servidor a servidor ya está configurada para Lync Server 2013 y otras aplicaciones, no es necesario para volver a hacerlo por Skype para Business Server. 
  
Sin embargo, se requiere autenticación de servidor a servidor si desea utilizar algunas de las características de Skype para Business Server, como "almacén de contactos unificados." Con el almacén de contactos unificados, Skype para obtener información de contacto de Business Server se almacena en Exchange en lugar de hacerlo en Skype para Business Server; Esto permite a los usuarios tener un único conjunto de contactos es accesible desde dentro de Skype para profesionales, Outlook o Outlook Web Access. Debido a que el almacén de contactos unificados requiere Skype para Business Server compartir información con Exchange, debe usar la autenticación de servidor a servidor para poder implementar la característica. Autenticación de servidor a servidor también es necesaria si decide utilizar el intercambio de archivado, en la que se guardan las transcripciones de sesiones de mensajería instantánea como mensajes de correo electrónico de Exchange, en lugar de como registros de la base de datos individual.
  
Para la versión de Office 365 de Skype para Business Server para comunicarse con su homólogo de Exchange, Skype para Business Server debe obtener un token de seguridad desde el servidor de autorización. Skype para Business Server usa, a continuación, ese token de seguridad que se identifique a Exchange. La versión de Office 365 de Exchange debe pasar por el mismo proceso para que pueda comunicarse con Skype para Business Server.
  
Sin embargo, para una autenticación de servidor a servidor local entre dos servidores Microsoft, no es necesario usar ningún servidor de tokens de otro proveedor. Productos de servidor como Skype para Business Server y Exchange dispone de un servidor de token integrado que se puede usar con fines de autenticación con otros servidores de Microsoft (por ejemplo, SharePoint Server) que admiten la autenticación de servidor a servidor. Por ejemplo, Skype para Business Server puede emitir y firmar un token de seguridad por sí mismo, a continuación, utilizar ese token para comunicarse con Exchange. En este caso, no es necesario usar ningún servidor de tokens de un tercero.
  
Con el fin de configurar la autenticación de servidor a servidor para una implementación local de Skype para Business Server, debe hacer dos cosas:
  
- Asignar un certificado a la Skype integrado para el emisor de tokens de Business Server.
    
- Configurar el servidor que se Skype para Business Server se comunican con como "aplicación de socio". Por ejemplo, si necesita Skype para Business Server para comunicarse con Exchange, necesitará configurar Exchange para que sea una aplicación de socio.
    
> [!NOTE]
> Una "aplicación de socio" es cualquier aplicación que Skype para Business Server puede intercambiar directamente tokens de seguridad, sin tener que pasar por un servidor de token de seguridad de otros fabricantes. 
  
Tenga en cuenta que OAuth es una parte fundamental del producto y no se puede desactivar ni eliminar.
  
## <a name="see-also"></a>Consulte también

[Asignar un certificado de autenticación de servidor a servidor a Skype para Business Server](assign-a-server-to-server-certificate.md)
  
[Configuración de un entorno híbrido en Skype para Business Server](configure-a-hybrid-environment.md)
