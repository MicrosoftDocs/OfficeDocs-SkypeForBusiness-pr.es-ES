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
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
description: Instrucciones para configurar Azure AD Conectar en un entorno híbrido.
ms.openlocfilehash: cfb290ecc6892001a9e20d9260c54c076a51dfe3
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2021
ms.locfileid: "60887218"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Configuración de Azure AD Connect para Teams y Skype Empresarial

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 
Para usar Teams, las organizaciones con una implementación local de Skype Empresarial Server o Lync Server 2013 deben configurar Azure AD Conectar para sincronizar su directorio local con Microsoft 365. Las organizaciones Skype Empresarial Server locales deben asegurarse de que los atributos msRTCSIP adecuados se sincronicen en Azure AD. En este artículo, cualquier referencia a "Skype Empresarial Server" también se aplica a Lync Server 2013.

> [!NOTE]
> - Para obtener la funcionalidad completa, Teams usuarios existentes que también tienen Skype Empresarial local tendrán que mover su cuenta Skype Empresarial local a la nube. Por ejemplo, para obtener funcionalidades como la capacidad de interoperar con Skype Empresarial usuarios y comunicarse con usuarios de organizaciones federadas. Si el usuario local solo va a usar Teams, debe mover el usuario a la nube para proporcionar una funcionalidad Teams completa como usuario de TeamsOnly. Para que esta migración se lleve a cabo, debe configurar Azure AD Conectar para poder habilitar la implementación híbrida.
> - Si no está planeando mover usuarios de local a la nube pronto, debe configurar Azure AD Conectar para que las cuentas Teams y Skype Empresarial Server coexistieran.
 

## <a name="background-information"></a>Información de contexto

Azure Active Directory Conectar mantiene su Active Directory local sincronizado continuamente con Microsoft 365. El directorio local sigue siendo el origen autoritativo de la identidad, mientras que los cambios del entorno local se sincronizan en Azure AD. Para obtener más información, [vea Azure AD Conectar Sync](/azure/active-directory/hybrid/how-to-connect-sync-whatis).  *Los usuarios de la organización estarán representados en los* directorios locales y en línea.  Todos los usuarios que usan Teams o Skype Empresarial local deben sincronizarse de forma local en Azure AD para garantizar la coexistencia de estas cuentas. Además, puede facilitar la comunicación entre usuarios locales y en línea Skype Empresarial la conectividad híbrida, que también requiere la configuración de Azure AD Conectar.


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Configuración de Azure AD cuando tiene Skype Empresarial Server 

### <a name="general-requirements"></a>Requisitos generales 

Para que una implementación local de Skype Empresarial Server coexista con Teams, ciertos atributos de Active Directory de la implementación local deben sincronizarse en Azure AD mediante Azure AD Conectar. El programa de Azure AD Conectar configura automáticamente los atributos necesarios para sincronizarse de forma predeterminada cuando detecta la presencia de Skype Empresarial Server en el entorno local. Estos atributos incluyen atributos de identidad general, como el nombre principal del usuario, así como atributos precedido de "msRTCSIP", que son específicos de Skype For Business Server. El conjunto completo de atributos se muestra en [Azure AD Conectar sincronización: atributos sincronizados con Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized#teams-and-skype-for-business-online).

Si decide personalizar la configuración de sincronización en Azure AD Conectar, debe asegurarse de que los siguientes atributos se sincronizan para los objetos de usuario:
</br>

|Atributo|Description|
|---|---|
|msRTCSIP-PrimaryUserAddress| Dirección sip del usuario en el entorno local|
|msRTCSIP-DeploymentLocator| Indica si el usuario está en la nube o local|
|msRTCSIP-UserEnabled| Si el usuario está habilitado para la funcionalidad SIP|
|||

</br>
</br>
Además, si administra atributos del sistema telefónico a través de la implementación local, también debe sincronizar los siguientes atributos:

|Atributo|Description|
|:---|:---|
|msRTCSIP-Line| Número de teléfono del usuario|
|msRTCSIP-OptionFlags| Indica si el usuario está habilitado para la funcionalidad de voz|
|msRTCSIP-OwnerUrn| Se usa para identificar puntos de conexión de aplicaciones híbridas|
|||

</br>
Microsoft recomienda sincronizar todos los bosques que contienen identidades de usuario, así como los bosques que contienen Skype Empresarial Server. Si las identidades de los usuarios existen en varios bosques, Azure AD Connect debe realizar la combinación. Al seguir esta guía, Azure AD Connect realizará automáticamente la sincronización de los atributos correctos, siempre y cuando no modifique las reglas de conectores o sincronización en Azure AD Connect. 
  
Si no se sincroniza desde todos los bosques que contienen identidades de usuario y la implementación de Skype Empresarial Server, debe asegurarse de que la identidad relevante y los atributos Skype Empresarial se rellenan correctamente en Azure AD para cualquier usuario que use Teams o Skype Empresarial (ya sea local o en línea). Esto probablemente requerirá una sincronización de directorios local adicional. Para obtener más información, [vea Azure AD Conectar sync: Attributes synchronized to Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized).

Es responsabilidad del cliente garantizar una configuración adecuada para rellenar los atributos en Azure AD. Tenga en cuenta lo siguiente: 

- El uso de una configuración no estándar para sincronizar con Azure AD es arriesgado. Las configuraciones no estándar podrían causar daños en los datos en el directorio en línea.

- A medida que los productos evolucionen, Microsoft seguirá comprobando las configuraciones de sincronización estándar en las que todos los bosques relevantes se sincronizan. Los clientes con configuraciones de sincronización personalizadas son los responsables de garantizar que las configuraciones entregan los atributos y valores correctos en Azure AD. 

Independientemente de si tiene un bosque de Active Directory local o varios bosques, Azure AD Conectar puede usarse en una variedad de topologías admitidas, como se describe en [Topologías](/azure/active-directory/hybrid/plan-connect-topologies)para Azure AD Conectar . Desde la perspectiva de Skype Empresarial Server, hay tres variaciones: 

1. Un solo bosque, que contiene identidades de usuario de autoridad y hospeda Skype Empresarial Server. 

2. Varios bosques, de los cuales solo uno hospeda Skype Empresarial Server, así como uno o más bosques que contienen identidades de usuario de autoridad (los bosques de la cuenta). 

3. Varias implementaciones de Skype Empresarial Server en varios bosques. Siempre que se cumplen ciertos requisitos, las organizaciones pueden consolidar estas implementaciones en una única Microsoft 365 organización.

### <a name="single-forest"></a>Un único bosque 

Si las cuentas de usuario y Skype Empresarial se hospedan en un único bosque, debe asegurarse de que Azure AD Connect está configurado para sincronizar los usuarios de este bosque con Azure AD.  De forma predeterminada, los atributos adecuados se sincronizarán automáticamente en Azure Active Directory. Se recomienda a los clientes que no modifiquen las reglas de sincronización integradas o los conectores que administran la configuración (lo que no es posible desde el asistente de instalación).  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>Varios bosques con una implementación de Skype Empresarial 

Este escenario se suele denominar topología de bosque de recursos. Las identidades de los usuarios de autoridad se hospedan en uno o más bosques de cuentas, y Skype Empresarial se implementa en un bosque de recursos diferente (que, en sí, también puede hospedar identidades de usuario de autoridad). En general, las identidades de autoridad de los usuarios de Skype Empresarial pueden estar en el mismo bosque que Skype Empresarial Server o en otro bosque, siempre que: 

- Los usuarios con identidades autoritativa de los bosques de cuentas se representan en el bosque de recursos (donde Skype Empresarial Server se implementa) como objetos de usuario deshabilitados. El atributo msRTCSIP-OriginatorSID del bosque de recursos debe coincidir con el SID del bosque de cuentas. Para obtener más información, vea [Configure a multi-forest environment for hybrid Skype Empresarial](configure-a-multi-forest-environment-for-hybrid.md).

- El bosque de recursos que hospeda Skype Empresarial Server confía en los bosques de cuentas.  

- Todos los objetos de usuario y atributos relevantes para la identidad (de bosques de cuentas) y Skype Empresarial (del bosque de recursos) se sincronizan en Azure AD con los valores correctos a través de Azure AD Conectar.  

  Para lograr la sincronización correcta de objetos [](configure-a-multi-forest-environment-for-hybrid.md)y atributos en Azure AD en un escenario local de varios bosques, Microsoft recomienda encarecidamente usar Azure AD Conectar para sincronizar todos los bosques que han habilitado cuentas de usuario y el bosque que contiene Skype Empresarial. Si sincroniza desde todos los bosques, debe configurar Azure AD Connect para combinar estas identidades y sincronizar con Azure AD. Azure AD Connect está diseñado para controlar este escenario y proporciona una opción integrada en el asistente de instalación para configurarlo, incluido el establecimiento de delimitadores para unir identidades. Elija lo siguiente: **Las identidades** de usuario existen en varios directorios y Coincide con los atributos **--> ObjectSID y msExchangeMasterAccountSID**.


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>Varias implementaciones de Skype Empresarial Server en varios bosques 

En este escenario, hay varios bosques, cada uno que contiene Skype Empresarial Server y una única Microsoft 365 organización. Cada bosque que contiene Skype Empresarial Server puede sincronizarse en Azure AD para esa organización mediante Azure AD Conectar. A lo sumo, solo se puede configurar un bosque para la implementación híbrida de Skype Empresarial en un momento determinado. Antes de habilitar híbridos en un bosque, todos los dominios SIP de todos los demás bosques deben deshabilitarse mediante [disable-csonlineSipDomain](/powershell/module/skype/disable-csonlinesipdomain). Para obtener más información, vea [Cloud consolidation for Teams and Skype Empresarial](cloud-consolidation.md).


## <a name="related-information"></a>Información relacionada

- [Qué es la identidad híbrida](/azure/active-directory/hybrid/whatis-hybrid-identity)

- sincronización de Azure AD Connect[: entender y personalizar sincronización](/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Topologías de Azure AD Connect](/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure AD Conectar sincronización: atributos sincronizados con Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
