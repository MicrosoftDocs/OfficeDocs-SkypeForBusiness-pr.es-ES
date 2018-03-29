---
title: Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socio en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 'Resumen: Administrar aplicaciones OAuth y socio en Skype para Business Server 2015.'
ms.openlocfilehash: 41886b0275bd7284f6716c322595f1c360171360
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server-2015"></a>Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socio en Skype Empresarial Server 2015
 
**Resumen:** Administrar aplicaciones OAuth y socio en Skype para Business Server 2015.
  
Skype para el año 2015 de Business Server debe ser capaces de comunicarse de forma segura y sin problemas, con otras aplicaciones y productos de servidor. Por ejemplo, puede configurar Skype para Business Server 2015 para ponerse en contacto con datos y archiving de datos se almacena en Microsoft Exchange Server 2013; Sin embargo, esto sólo es posible si Skype para Business Server y Exchange es capaces de comunicarse de forma segura entre sí. Igualmente, puede programar un Skype para conferencia de Business Server desde dentro de Office Web Apps Server; de nuevo, esto sólo es posible si los servidores (SharePoint y Skype para Business Server) confían entre sí. Aunque es posible usar un mecanismo de autenticación para la comunicación entre Skype para Business Server y Exchange, pero un mecanismo independiente para Skype para la comunicación Business Server y SharePoint, un enfoque mejor y más eficaz es utilizar un método estándar para todos los servidores de autenticación y autorización.
  
Utilizando un único, un método estándar para la autenticación de servidor a servidor es el enfoque adoptado por Skype para Business Server 2015. Para 2013 versión, Skype para Business Server 2015 (así como otros productos de Microsoft Server, incluyendo 2013 de Exchange y SharePoint Server) admiten el protocolo OAuth (Open Authorization) para la autenticación de servidor a servidor y autorización. Con OAuth, un protocolo de autorización estándar utilizado por un número de los principales sitios Web, las credenciales de usuario y las contraseñas no se pasan de un equipo a otro. En su lugar, autenticación y autorización se basa en el intercambio de tokens de seguridad; Estos tokens conceden acceso a un conjunto específico de recursos durante un período específico de tiempo.
  
Autenticación OAuth normalmente implica tres partes: un servidor único de autorización y los dos territorios que necesitan comunicarse entre sí. (Se puede hacer la autenticación de servidor a servidor sin utilizar un servidor de autorización, un proceso que se tratarán más adelante en este documento.) Tokens de seguridad emitidos por el servidor de autorización (también conocido como un servidor testigo de seguridad) a los dos territorios que necesitan comunicarse; Estos tokens Compruebe que deben ser de confianza por el territorio de otro comunicaciones procedentes de un territorio. Por ejemplo, el servidor de autorización podría emitir tokens que compruebe que los usuarios de un determinado Skype para Business Server 2015 territorio tienen acceso a un territorio de 2013 de Exchange especificado y viceversa.
  
> [!NOTE]
> Un dominio es un contenedor de seguridad. De forma predeterminada, Skype para Business Server 2015 utiliza su dominio SIP de forma predeterminada como su territorio OAuth. Se agregan espacios de nombres SIP a la lista Nombre alternativo del sujeto en el certificado OAuth. 
  
Skype para Business Server 2015 admite tres escenarios de autenticación de servidor a servidor. Con Skype para Business Server 2015 puede:
  
- Configurar la autenticación de servidor a servidor entre una instalación local de Skype para Business Server 2015 y una instalación local de 2013 de Exchange o SharePoint Server.
    
- Configurar la autenticación de servidor a servidor entre un par de componentes de Office 365 (por ejemplo, entre Microsoft Exchange Server y Skype para Business Server o entre Skype para Business Server 2015 y SharePoint).
    
- Configurar la autenticación de servidor a servidor en un entorno entre locales (es decir, autenticación de servidor a servidor entre un servidor local y un componente de Office 365).
    
Tenga en cuenta que, en este momento, sólo Exchange 2013, SharePoint Server, Lync Server 2013 y Skype para la autenticación de servidor a servidor de soporte Business Server 2015; Si no se está ejecutando uno de estos servidores, a continuación, no podrá aplicar plenamente la autenticación OAuth.
  
También puede señalar ese servidor a servidor autenticación es opcional: si Skype para Business Server 2015 no necesita comunicarse con otros servidores (por ejemplo, Exchange 2013) y autenticación de servidor a servidor puede omitirse por completo. Si la autenticación de servidor a servidor ya está configurada para 2013 de Lync Server y otras aplicaciones, no es necesario que vuelva a hacerlo por Skype para Business Server 2015. 
  
Sin embargo, se requiere autenticación de servidor a servidor si desea utilizar algunas de las características de Skype para Business Server 2015, como el "unificado almacén de contactos." Con el almacén de contactos unificado, Skype Business Server 2015 información de contacto se almacena en Exchange de 2013, en lugar de en Skype para Business Server; Esto permite a los usuarios tener un único conjunto de contactos que sea fácilmente accesible desde dentro de Skype para negocios, Outlook o Outlook Web Access. Dado que el almacén de contactos unificado requiere Skype para Business Server 2015 compartir información con Exchange 2013, debe utilizar la autenticación de servidor a servidor para implementar la característica. También se requiere la autenticación de servidor a servidor si opta por utilizar Exchange archiving, en el que se guardan las transcripciones de las sesiones de mensajería instantáneas como mensajes de correo electrónico Exchange 2013 en lugar de registros individuales de la base de datos.
  
Para la versión de Office 365 de Skype para Business Server para comunicarse con su contraparte de Exchange, Skype para Business Server 2015 debe obtener un token de seguridad del servidor de autorización. Skype para Business Server utiliza ese símbolo (token) de seguridad para identificarse a sí mismo a Exchange. La versión de Office 365 de Exchange debe atravesar el mismo proceso para comunicarse con Skype para Business Server 2015.
  
Sin embargo, para una autenticación de servidor a servidor local entre dos servidores Microsoft, no es necesario usar ningún servidor de tokens de otro proveedor. Productos de servidor como Skype para Business Server 2015 y 2013 de Exchange tienen un servidor integrado de símbolo (token) que puede utilizarse para la autenticación con otros servidores de Microsoft (como SharePoint Server) que admiten la autenticación de servidor a servidor. Por ejemplo, Skype para Business Server 2015 puede emitir y firmar un token de seguridad por sí mismo, utilizar ese token para comunicarse con Exchange de 2013. En este caso, no es necesario usar ningún servidor de tokens de un tercero.
  
Para configurar la autenticación de servidor a servidor para una implementación local de Skype para Business Server 2015 debe hacer dos cosas:
  
- Asignar un certificado a la Skype integrado para el emisor de tokens Business Server 2015.
    
- Configurar el servidor de Skype para Business Server 2015 se comunicará con una "aplicación de socio". Por ejemplo, si necesita comunicarse con Exchange 2013 Skype para Business Server 2015, a continuación, debe configurar Exchange para que sea una aplicación asociada.
    
> [!NOTE]
> Una aplicación de"socio" es cualquier aplicación que Skype para Business Server 2015 puede intercambiar directamente los tokens de seguridad, sin tener que pasar por un servidor de token de seguridad de otros fabricantes. 
  
Tenga en cuenta que OAuth es una parte fundamental del producto y no se puede desactivar ni eliminar.
  
## <a name="see-also"></a>Vea también

#### 

[Asignar un certificado de autenticación de servidor a servidor a Skype para Business Server 2015](assign-a-server-to-server-certificate.md)
  
[Configurar un entorno híbrido en Skype para Business Server 2015](configure-a-hybrid-environment.md)

