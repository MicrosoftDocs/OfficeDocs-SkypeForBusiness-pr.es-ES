---
title: Configurar Azure AD Conectar
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Instrucciones para configurar azure ad Conectar en un entorno híbrido.
ms.openlocfilehash: e9e043e8cded2e9e55741cd0abe37488c4b621c6fb7cbfc5e9fd1e35917f8b84
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54292487"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Configuración de Azure AD Connect para Teams y Skype Empresarial

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 
Las organizaciones que Skype Empresarial Server (o Lync Server) locales y que planean usar Teams deben configurar Azure AD Conectar para sincronizar su directorio local con Microsoft 365. Este requisito incluye organizaciones que se mueven directamente de Skype Empresarial local a Teams. Las organizaciones Skype Empresarial locales deben asegurarse de que los atributos msRTCSIP adecuados se sincronicen en Azure AD.

> [!NOTE]
> Los usuarios de Teams existentes que también tienen Skype Empresarial local tendrán que mover su cuenta Skype Empresarial local a la nube para obtener funcionalidad completa, como la capacidad de interoperar con usuarios de Skype Empresarial y comunicarse con usuarios de organizaciones federadas. Incluso si el usuario solo va a usar Teams, la infraestructura necesita esta cuenta de Skype Empresarial Online para ofrecer la funcionalidad adicional. Para que se produzca esta migración, debe asegurarse de que la configuración de Azure AD Connect es la correcta, de modo que pueda habilitar la implementación híbrida.
 

## <a name="background-information"></a>Información de contexto

Azure Active Directory Conectar mantiene su Active Directory local sincronizado continuamente con Microsoft 365. El directorio local permanece como el origen de autoridad de la identidad y los cambios de su entorno local se sincronizan en Azure AD. Para obtener más información, [vea Azure AD Conectar Sync](/azure/active-directory/hybrid/how-to-connect-sync-whatis).  

Si no va a mover todos los usuarios de local a la nube, todos los usuarios que usan Teams o Skype Empresarial local deben sincronizarse de forma local en Azure AD para garantizar la comunicación entre usuarios locales y en línea. *Los usuarios de la organización tendrán representación en los directorios locales y en línea.*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Configuración de Azure AD cuando tiene Skype Empresarial Server 

Independientemente de si tiene un bosque de Active Directory local o varios bosques, Azure AD Conectar se puede usar en una variedad de topologías admitidas, como se describe en [Topologías](/azure/active-directory/hybrid/plan-connect-topologies)para Azure AD Conectar . Desde la perspectiva de Skype Empresarial Server, hay tres variaciones: 

1. Un solo bosque, que contiene identidades de usuario de autoridad y hospeda Skype Empresarial Server. 

2. Varios bosques, de los cuales solo uno hospeda Skype Empresarial Server, así como uno o más bosques que contienen identidades de usuario de autoridad (los bosques de la cuenta). 

3. Varias implementaciones de Skype Empresarial Server en varios bosques. Siempre que se cumplen ciertos requisitos, las organizaciones pueden consolidar estas implementaciones en una única Microsoft 365 organización.

### <a name="single-forest"></a>Un único bosque 

Si las cuentas de usuario y Skype Empresarial se hospedan en un único bosque, debe asegurarse de que Azure AD Connect está configurado para sincronizar los usuarios de este bosque con Azure AD.  Aunque el asistente para la instalación de Azure AD Connect tiene una amplia variedad de opciones, los atributos adecuados se sincronizarán automáticamente en Azure Active Directory. Se recomienda a los clientes que no modifiquen las reglas de sincronización integradas o los conectores que administran la configuración (lo que no es posible desde el asistente de instalación).  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>Varios bosques con una implementación de Skype Empresarial 

Este escenario se suele denominar topología de bosque de recursos. Las identidades de los usuarios de autoridad se hospedan en uno o más bosques de cuentas, y Skype Empresarial se implementa en un bosque de recursos diferente (que, en sí, también puede hospedar identidades de usuario de autoridad). En general, las identidades de autoridad de los usuarios de Skype Empresarial pueden estar en el mismo bosque que Skype Empresarial Server o en otro bosque, siempre que: 

- Los usuarios con identidades autoritativa de los bosques de cuentas se representan en el bosque de recursos (donde Skype Empresarial Server se implementa) como objetos de usuario deshabilitados. El atributo msRTCSIP-OriginatorSID del bosque de recursos debe coincidir con el SID del bosque de cuentas. Para obtener más información, vea [Configure a multi-forest environment for hybrid Skype Empresarial](configure-a-multi-forest-environment-for-hybrid.md).

- El bosque de recursos que hospeda Skype Empresarial Server confía en los bosques de cuentas.  

- Todos los objetos de usuario y atributos relevantes de identidad (de bosques de cuentas) y Skype Empresarial (del bosque de recursos) se sincronizan en Azure AD con los valores correctos a través de Azure AD Conectar.  

  Para lograr la sincronización correcta de [](configure-a-multi-forest-environment-for-hybrid.md)objetos y atributos en Azure AD en un escenario local de varios bosques, Microsoft recomienda encarecidamente usar Azure AD Conectar para sincronizar desde todos los bosques que han habilitado cuentas de usuario y el bosque que contiene Skype Empresarial. Si sincroniza desde todos los bosques, debe configurar Azure AD Connect para combinar estas identidades y sincronizar con Azure AD. Azure AD Connect está diseñado para controlar este escenario y proporciona una opción integrada en el asistente de instalación para configurarlo, incluido el establecimiento de delimitadores para unir identidades. Elija lo siguiente: **Las identidades** de usuario existen en varios directorios y Coincide con los atributos **--> ObjectSID y msExchangeMasterAccountSID**.


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>Varias implementaciones de Skype Empresarial Server en varios bosques 

En este escenario, hay varios bosques, cada uno con Skype Empresarial Server y una única Microsoft 365 organización. Cada bosque que Skype Empresarial Server puede sincronizarse en Azure AD para esa organización mediante AAD Conectar. A lo sumo, solo se puede configurar un bosque para la implementación híbrida de Skype Empresarial en un momento determinado. Antes de habilitar híbridos en un bosque, todos los dominios SIP de todos los demás bosques deben deshabilitarse mediante [disable-csonlineSipDomain](/powershell/module/skype/disable-csonlinesipdomain). Para obtener más información, vea [Cloud consolidation for Teams and Skype Empresarial](cloud-consolidation.md).

## <a name="general-requirements"></a>Requisitos generales 

Los Teams requieren que los atributos correctos de Active Directory existan y se rellenen en Azure AD. Microsoft recomienda sincronizar todos los bosques que contienen identidades de usuario, así como los bosques que contienen Skype Empresarial Server.

 Si las identidades de los usuarios existen en varios bosques, Azure AD Connect debe realizar la combinación. Al seguir esta guía, Azure AD Connect realizará automáticamente la sincronización de los atributos correctos, siempre y cuando no modifique las reglas de conectores o sincronización en Azure AD Connect. 
  
Si no sincroniza desde todos los bosques que contienen identidades de usuario y la implementación de Skype Empresarial Server, debe asegurarse de que la identidad relevante y los atributos Skype Empresarial se rellenan correctamente en Azure AD para cualquier usuario que use Teams o Skype Empresarial (ya sea local o en línea). Esto probablemente requerirá una sincronización de directorios local adicional. Para obtener más información, vea [Azure AD Conectar sync: Attributes synchronized to Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized).

En estos escenarios, es responsabilidad del cliente garantizar una configuración adecuada para rellenar los atributos en Azure AD. Tenga en cuenta lo siguiente: 

- El uso de una configuración no estándar para sincronizar con Azure AD es arriesgado, ya que podría provocar un error de configuración, lo que podría provocar daños en los datos del directorio en línea.

- A medida que los productos evolucionen, Microsoft seguirá comprobando las configuraciones de sincronización estándar en las que todos los bosques relevantes se sincronizan. Los clientes con configuraciones de sincronización personalizadas son los responsables de garantizar que las configuraciones entregan los atributos y valores correctos en Azure AD. 

## <a name="related-information"></a>Información relacionada

- [Qué es la identidad híbrida](/azure/active-directory/hybrid/whatis-hybrid-identity)

- [Sincronización de Conectar Azure AD: comprender y personalizar la sincronización](/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Topologías de Azure AD Connect](/azure/active-directory/hybrid/plan-connect-topologies)

- [Sincronización de Conectar Azure AD: atributos sincronizados con Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)