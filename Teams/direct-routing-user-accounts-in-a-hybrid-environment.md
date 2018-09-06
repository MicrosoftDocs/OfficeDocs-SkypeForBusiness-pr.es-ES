---
title: Cuentas de usuario en un entorno híbrido con conectividad RTC
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Obtenga información sobre diferentes combinaciones de creación de usuarios y qué combinaciones son compatibles o no compatibles.
ms.openlocfilehash: 04f0237dd7df6c856b6fef117f435ea2db052c82
ms.sourcegitcommit: 33966ebb9ca3d922d47aaa9b9e3a2ddd26c320ca
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "23846264"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>Cuentas de usuario en un entorno híbrido con conectividad RTC

## <a name="about-the-environment"></a>Acerca del entorno

En este artículo se aplica a entornos tienen todas las opciones siguientes: 
 
- Skype para Business Server 2015 o Lync Server 2013 
- Un inquilino de Office 365 
- Conectividad híbrida configurada entre el Skype para Business Server y Skype para inquilino empresarial en línea o equipos 
- Usuarios que están habilitados para realizar y recibir llamadas de red pública de telefónica conmutada (RTC) a y desde el cliente

 
Si tiene un entorno diferente (por ejemplo, Skype para Business Edition de conector en la nube), híbrida no está configurado o no se habilitará a los usuarios para las llamadas de RTC, la matriz de compatibilidad de será diferente.  

## <a name="about-the-combinations-and-the-supportability-statement"></a>Acerca de las combinaciones y la declaración de compatibilidad  

Un Skype para entornos híbridos, empresarial con conectividad RTC proporciona flexibilidad con respecto a donde se proporcionan los servicios de usuario y cómo se aprovisiona y administran las cuentas de usuario. Pero la gran cantidad de opciones es posible crear algunas combinaciones no compatibles. En esta sección se explica diferentes combinaciones de creación del usuario, seguido de una instrucción de compatibilidad.


**Definiciones:**   
- **Enterprise Voice:** Opción para proporcionar acceso a RTC para usuarios con Skype local para la cuenta de usuario de negocio. Skype local para el servidor de mediación de negocio proporciona interconectividad a RTC.  
- **Conectividad de voz híbrida:** Opción para proporcionar acceso a RTC para con Skype en línea para la cuenta de empresa. Skype local para el servidor de mediación de negocio proporciona interconectividad a RTC. 
- **Enrutamiento directo:** Opción para proporcionar acceso a RTC para usuarios con Skype en línea para la cuenta de empresa, licencia de Microsoft Teams, utilizando el cliente de Microsoft Teams. La SBC está conectado al Proxy SIP en Office 365 sin necesidad de cualquier software local de Microsoft.

  
**El entorno es compatible con las siguientes combinaciones:**
- **Escenario 1:** Usuario de cuenta de Skype para la empresa local y usará el Skype para clientes empresariales con Enterprise Voice
- **Escenario 2:** Usuario de cuenta de Skype para la empresa en línea y usará el Skype para clientes empresariales con conectividad de voz híbrida
- **Escenario 3:** Usuario de cuenta de Skype para la empresa en línea con licencia de Microsoft Teams y va a usar el cliente de los equipos
 
### <a name="supportability-matrix"></a>Matriz de compatibilidad


|**Objeto de usuario creado en**  |**Skype del usuario para el proveedor de servicios profesionales**|**Cliente del usuario**|**Opción de voz**|**Compatible**|
|---------|---------|---------|---------|--------|
|En AD local| Implementación local |Skype Empresarial   | Telefonía IP empresarial   |Sí|
|En AD local|En línea| Skype Empresarial  | Conectividad de voz híbrida   |Sí |
|En AD local|En línea |Microsoft Teams |Enrutamiento directo  |Sí |
|**Combinaciones admitidas**    | |         |         |
|Azure AD| En local o en línea | Skype para los equipos de negocio y Microsoft|Enterprise Voice de voz híbrida enrutamiento conectividad/Direct  |No, debe crearse el objeto de usuario en AD local en primer lugar |
|En AD local  |Implementación local| Microsoft Teams| Enterprise Voice de voz híbrida enrutamiento conectividad/Direct   |No, el cliente de Microsoft Teams no es compatible con Skype local para la empresa |
|En AD local  |En línea |Skype Empresarial | Enrutamiento directo  | No, Skype para Business client no es compatible con el enrutamiento directo  |
|En AD local  |En línea |Skype Empresarial  | Enrutamiento directo  |No, el enrutamiento directo no es compatible con Skype para cliente de negocio y usuario debe estar habilitado para Enterprise Voice en Skype para la empresa en primer lugar  |
|   |         |         |         ||

### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>Instrucción de compatibilidad para el entorno híbrido con RTC

Para todos los usuarios, el usuario objeto **debe** crearse en el local AD y sincronizados con Azure AD mediante la herramienta de Azure Connect de AD. Habilitación de usuarios para los equipos y Skype para empresarial **no se admite** si se crea el objeto de usuario directamente en Azure AD en una configuración híbrida. Para los nuevos usuarios, como un nuevo empleado, que se habilitará directamente para los equipos, el usuario debe ser alojado en Skype para la empresa local inicialmente y movido a los registradores en línea. Crear usuarios en Skype en línea de negocio o equipos sin habilitar ellos en el grupo de servidores local con Enterprise Voice **no se admite**.
  

El usuario debe estar habilitado para Skype para la empresa y uso de Enterprise Voice local Skype para herramientas de administración de usuario de negocio. Habilitación de usuarios de Skype para profesionales en línea sólo **no se admite**. Consulte [este artículo](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises#special-considerations-when-enabling-users-for-enterprise-voice-on-premises) para obtener más información acerca de cómo habilitar a los usuarios de Skype para la empresa en la configuración híbrida.