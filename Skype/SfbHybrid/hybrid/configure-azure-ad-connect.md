---
title: Configurar Azure AD Connect
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
description: Instrucciones para configurar Azure AD Connect en un entorno híbrido.
ms.openlocfilehash: 7a0c458692da1381f2ed3f52dfef8c1d360d74e2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221474"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Configuración de Azure AD Connect para Teams y Skype Empresarial
 
Las organizaciones que tienen Skype Empresarial Server (o Lync Server) local y que planean usar Teams o Skype Empresarial Online deben configurar Azure AD Connect para sincronizar su directorio local con Microsoft 365 u Office 365, como se describe en este documento.  Esto incluye las organizaciones que se mueven directamente de Skype Empresarial local a Teams. En particular, las organizaciones con Skype Empresarial local deben garantizar que los atributos msRTCSIP adecuados estén sincronizados con Azure AD. 

> [!NOTE]
> Los usuarios de Teams existentes que también tienen Skype Empresarial local necesitan trasladar su cuenta local de Skype Empresarial a la nube para obtener todas las funcionalidades, como la capacidad de interactuar con los usuarios de Skype Empresarial, así como para comunicarse con los usuarios de organizaciones federadas. Incluso si el usuario solo va a usar Teams, la infraestructura necesita esta cuenta de Skype Empresarial Online para ofrecer la funcionalidad adicional.  Para que se produzca esta migración, debe asegurarse de que la configuración de Azure AD Connect es la correcta, de modo que pueda habilitar la implementación híbrida.
 

## <a name="background-information"></a>Información general

Azure Active Directory Connect mantiene su Active Directory local sincronizado continuamente con Microsoft 365 u Office 365.  El directorio local permanece como el origen de autoridad de la identidad y los cambios de su entorno local se sincronizan en Azure AD. Para obtener más información, [vea Sincronización de Azure AD Connect.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)  Incluso si no va a mover todos los usuarios de local a la nube, todos los usuarios que usan Teams, Skype Empresarial local o Skype Empresarial Online deben sincronizarse de forma local en Azure AD para garantizar la comunicación entre los usuarios locales y en línea. *Los usuarios de la organización tendrán representación en los directorios locales y en línea.*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Configuración de Azure AD cuando tiene Skype Empresarial Server 

Tanto si tiene un bosque de Active Directory local como varios bosques, Azure AD Connect puede usarse en una variedad de topologías admitidas, como se describe en Topologías para [Azure AD Connect.](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies)  Desde el punto de vista de Skype Empresarial Server, hay tres variantes principales: 

1. Un solo bosque, que contiene identidades de usuario de autoridad y hospeda Skype Empresarial Server. 

2. Varios bosques, de los cuales solo uno hospeda Skype Empresarial Server, así como uno o más bosques que contienen identidades de usuario de autoridad (los bosques de la cuenta). 

3. Varias implementaciones de Skype Empresarial Server en varios bosques. Siempre que se cumplen ciertos requisitos, las organizaciones pueden consolidar estas implementaciones múltiples en una sola organización de Microsoft 365 u Office 365.

### <a name="single-forest"></a>Un único bosque 

Si las cuentas de usuario y Skype Empresarial se hospedan en un único bosque, debe asegurarse de que Azure AD Connect está configurado para sincronizar los usuarios de este bosque con Azure AD.  Aunque el asistente para la instalación de Azure AD Connect tiene una amplia variedad de opciones, los atributos adecuados se sincronizarán automáticamente en Azure Active Directory. Se recomienda a los clientes que no modifiquen las reglas de sincronización integradas o los conectores que administran la configuración (lo cual no es posible desde el asistente para la instalación).  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>Varios bosques con una implementación de Skype Empresarial 

Este escenario se suele denominar topología de bosque de recursos. Las identidades de los usuarios de autoridad se hospedan en uno o más bosques de cuentas, y Skype Empresarial se implementa en un bosque de recursos diferente (que, en sí, también puede hospedar identidades de usuario de autoridad). En general, las identidades de autoridad de los usuarios de Skype Empresarial pueden estar en el mismo bosque que Skype Empresarial Server o en otro bosque, siempre que: 

- Los usuarios con identidades de autoridad de los bosques de cuentas tengan representación en el bosque de recursos (donde está implementado Skype Empresarial Server) como objetos de usuario deshabilitados y el atributo msRTCSIP-OriginatorSID en el bosque de recursos coincida con el SID del bosque de cuentas. Para obtener más información, consulte [Configurar un entorno de varios bosques para Skype Empresarial híbrido.](configure-a-multi-forest-environment-for-hybrid.md)

- El bosque de recursos que hospeda Skype Empresarial Server confía en los bosques de cuentas.  

- Todos los objetos de usuario y atributos relevantes para la identidad (desde bosques de cuentas) y Skype Empresarial (desde bosques de recursos) se sincronizan en Azure AD con los valores correctos a través de Azure AD Connect.  

 Para lograr una sincronización adecuada de [](configure-a-multi-forest-environment-for-hybrid.md)objetos y atributos en Azure AD en un escenario local de varios bosques, Microsoft recomienda encarecidamente usar Azure AD Connect para sincronizarse desde todos los bosques que tienen cuentas de usuario habilitadas y el bosque que contiene Skype Empresarial.  Si sincroniza desde todos los bosques, debe configurar Azure AD Connect para combinar estas identidades y sincronizar con Azure AD. Azure AD Connect está diseñado para controlar este escenario y proporciona una opción integrada en el asistente de instalación para configurarlo, incluido el establecimiento de delimitadores para unir identidades.  Elija lo siguiente: Existen identidades de usuario en varios directorios. Coincide con los atributos --> ObjectSID y msExchangeMasterAccountSID.


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>Varias implementaciones de Skype Empresarial Server en varios bosques 

En este escenario, hay varios bosques, cada uno con Skype Empresarial Server y una sola organización de Microsoft 365 u Office 365.  Cada bosque que contiene Skype Empresarial Server se puede sincronizar en Azure AD para esa organización mediante AAD Connect. A lo sumo, solo se puede configurar un bosque para la implementación híbrida de Skype Empresarial en un momento determinado. Antes de habilitar la implementación híbrida en un bosque, todos los dominios SIP de todos los demás bosques deben deshabilitarse mediante [disable-csonlineSipDomain](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain). Para obtener más información sobre cómo consolidar un entorno de este tipo en Microsoft 365 u Office 365, consulte Consolidación de la nube para [Teams y Skype Empresarial.](cloud-consolidation.md)

## <a name="general-requirements"></a>Requisitos generales 

Tanto los servicios de Teams como los de Skype Empresarial Online requieren que los atributos correctos de Active Directory existan y se rellenen en Azure AD.  La recomendación general de Microsoft es sincronizar todos los bosques que contienen identidades de usuario, así como los bosques que contienen Skype Empresarial Server.

 Si las identidades de los usuarios existen en varios bosques, Azure AD Connect debe realizar la combinación. Cuando se sigue esta guía, Azure AD Connect sincronizará automáticamente los atributos correctos, siempre que no modifique los conectores ni las reglas de sincronización en Azure AD Connect. 
  
Si no sincroniza desde todos los bosques que contienen identidades de usuario y la implementación de Skype Empresarial Server, debe asegurarse de que la identidad relevante y los atributos de Skype Empresarial se rellenan correctamente en Azure AD para cualquier usuario que use Teams o Skype Empresarial (ya sea local o en línea), lo que probablemente requerirá una sincronización de directorios local adicional. Para obtener más información, [vea Sincronización de Azure AD Connect: Atributos sincronizados con Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

En estos escenarios, es responsabilidad del cliente garantizar una configuración adecuada para rellenar los atributos en Azure AD. Tenga en cuenta lo siguiente: 

- El uso de una configuración no estándar para sincronizar con Azure AD es arriesgado, ya que podría provocar un error de configuración, lo que podría provocar daños en los datos del directorio en línea.

- A medida que los productos evolucionen, Microsoft seguirá comprobando las configuraciones de sincronización estándar en las que todos los bosques relevantes se sincronizan. Los clientes con configuraciones de sincronización personalizadas son los responsables de garantizar que las configuraciones entregan los atributos y valores correctos en Azure AD. 

## <a name="related-information"></a>Información relacionada

- [Qué es la identidad híbrida](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)

- [Sincronización de Azure AD Connect: comprender y personalizar la sincronización](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Topologías de Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies)

- [Sincronización de Azure AD Connect: atributos sincronizados con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
