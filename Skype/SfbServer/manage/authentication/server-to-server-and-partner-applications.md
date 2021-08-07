---
title: Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones asociadas en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 'Resumen: Administrar OAuth y aplicaciones de partners en Skype Empresarial Server.'
ms.openlocfilehash: 9f463a02c21cf21ced5c42c87d604923038a429a603380b3a043d1423bded785
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305452"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones asociadas en Skype Empresarial Server
 
**Resumen:** Administrar OAuth y aplicaciones de partners en Skype Empresarial Server.
  
Skype Empresarial Server ser capaz de comunicarse de forma segura y sin problemas con otras aplicaciones y productos de servidor. Por ejemplo, puede configurar los Skype Empresarial Server para que los datos de contacto o los datos de archivado se almacenen en Microsoft Exchange Server 2013; sin embargo, esto solo se puede hacer si Skype Empresarial Server y Exchange pueden comunicarse de forma segura entre sí. Del mismo modo, puede programar una conferencia Skype Empresarial Server desde Office Web Apps Server; de nuevo, esto solo se puede hacer si los dos servidores (SharePoint y Skype Empresarial Server) confían entre sí. Aunque es posible usar un mecanismo de autenticación para la comunicación entre Skype Empresarial Server y Exchange pero un mecanismo independiente para la comunicación Skype Empresarial Server y SharePoint, un enfoque mejor y más eficaz es usar un método estandarizado para toda la autenticación y autorización de servidor a servidor.
  
El uso de un único método estandarizado para la autenticación de servidor a servidor es el enfoque que Skype Empresarial Server. Iniciada con la versión de Office Servers 2013, Skype Empresarial Server (así como otros productos de Microsoft Server, incluido Exchange Server y SharePoint Server) admiten el protocolo OAuth (Open Authorization) para la autenticación y autorización de servidor a servidor. Con OAuth, un protocolo de autorización estándar usado por varios sitios web principales, las credenciales de usuario y las contraseñas no se pasan de un equipo a otro. En su lugar, la autenticación y la autorización se basan en el intercambio de tokens de seguridad; estos tokens conceden acceso a un conjunto específico de recursos durante un período de tiempo específico.
  
La autenticación de OAuth suele implicar tres partes: un único servidor de autorización y los dos dominios que necesitan comunicarse entre sí. (También puede realizar la autenticación de servidor a servidor sin usar un servidor de autorización, un proceso que se analizará más adelante en este documento). El servidor de autorización (también conocido como servidor de tokens de seguridad) emite tokens de seguridad a los dos dominios que necesitan comunicarse; estos tokens comprueban que las comunicaciones procedentes de un dominio deben ser de confianza para el otro dominio. Por ejemplo, el servidor de autorización puede emitir tokens que comprueben que los usuarios de un dominio de Skype Empresarial Server específico puedan tener acceso a un dominio Exchange específico y viceversa.
  
> [!NOTE]
> Un dominio es un contenedor de seguridad. De forma predeterminada, Skype Empresarial Server el dominio SIP predeterminado como su dominio de OAuth. Los espacios de nombres SIP adicionales se agregan a la lista Nombre alternativo del sujeto en el certificado de OAuth. 
  
Skype Empresarial Server admite tres escenarios de autenticación de servidor a servidor. Con Skype Empresarial Server, puede:
  
- Configure la autenticación de servidor a servidor entre una instalación local de Skype Empresarial Server y una instalación local de Exchange y/o SharePoint Server.
    
- Configure la autenticación de servidor a servidor entre un par de componentes Microsoft 365 o Office 365 (por ejemplo, entre Microsoft Exchange Server y Skype Empresarial Server, o entre Skype Empresarial Server y SharePoint).
    
- Configure la autenticación de servidor a servidor en un entorno entre locales (es decir, la autenticación de servidor a servidor entre un servidor local y un Microsoft 365 o Office 365 servidor).
    
Tenga en cuenta que, en este momento, solo Exchange 2013, SharePoint Server, Lync Server 2013, Skype Empresarial Server 2015 y Skype Empresarial 2019 admiten la autenticación de servidor a servidor; si no ejecuta uno de estos servidores, no podrá implementar completamente la autenticación de OAuth.
  
También debe señalarse que la autenticación de servidor a servidor es opcional: si Skype Empresarial Server no necesita comunicarse con otros servidores (como Exchange), la autenticación de servidor a servidor se puede omitir por completo. Si la autenticación de servidor a servidor ya está configurada para Lync Server 2013 y otras aplicaciones, no es necesario volver a hacerlo para Skype Empresarial Server. 
  
Sin embargo, la autenticación de servidor a servidor es necesaria si desea usar algunas de las características de Skype Empresarial Server, como el "almacén de contactos unificado". Con el almacén de contactos unificado, Skype Empresarial Server información de contacto se almacena en Exchange en lugar de en Skype Empresarial Server; esto permite a los usuarios tener un único conjunto de contactos que sea fácilmente accesible desde dentro de Skype Empresarial, Outlook o Outlook Web Access. Dado que el almacén de contactos unificado requiere Skype Empresarial Server compartir información con Exchange, debe usar la autenticación de servidor a servidor para implementar la característica. La autenticación de servidor Exchange servidor también es necesaria si decide usar el archivado de Exchange, en el que las transcripciones de las sesiones de mensajería instantánea se guardan como correos electrónicos Exchange en lugar de como registros de base de datos individuales.
  
Para que la Microsoft 365 o Office 365 de Skype Empresarial Server se comunique con su equivalente Exchange, Skype Empresarial Server primero debe obtener un token de seguridad del servidor de autorización. Skype Empresarial Server luego usa ese token de seguridad para identificarse para Exchange. Las Microsoft 365 o Office 365 de Exchange deben pasar por el mismo proceso para comunicarse con Skype Empresarial Server.
  
Sin embargo, no es necesario utilizar ningún servidor de token de terceros para la autenticación local de servidor a servidor entre dos servidores de Microsoft. Los productos de servidor como Skype Empresarial Server y Exchange tienen un servidor de tokens integrado que se puede usar con fines de autenticación con otros servidores de Microsoft (como SharePoint Server) que admiten la autenticación de servidor a servidor. Por ejemplo, Skype Empresarial Server emitir y firmar un token de seguridad por sí mismo y, a continuación, usar ese token para comunicarse con Exchange. En un caso como este, no se necesita ningún servidor de tokens de terceros.
  
Para configurar la autenticación de servidor a servidor para una implementación local de Skype Empresarial Server, debe hacer dos cosas:
  
- Asigne un certificado al emisor de tokens Skype Empresarial Server integrado.
    
- Configure el servidor con Skype Empresarial Server se comunicará para que sea una "aplicación de socio". Por ejemplo, si Skype Empresarial Server debe comunicarse con Exchange, deberá configurar Exchange para que sea una aplicación asociada.
    
> [!NOTE]
> Una "aplicación de socio" es cualquier aplicación con la que Skype Empresarial Server intercambiar tokens de seguridad directamente sin tener que pasar por un servidor de tokens de seguridad de terceros. 
  
Tenga en cuenta que OAuth es una parte principal del producto y no se puede deshabilitar ni quitar.
  
## <a name="see-also"></a>Consulte también

[Asignar un certificado de autenticación de servidor a servidor a Skype Empresarial Server](assign-a-server-to-server-certificate.md)
  
[Configurar un entorno híbrido en Skype Empresarial Server](configure-a-hybrid-environment.md)
