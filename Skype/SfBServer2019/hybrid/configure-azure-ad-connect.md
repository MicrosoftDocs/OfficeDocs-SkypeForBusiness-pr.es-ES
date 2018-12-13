---
title: Configurar Azure AD conectarse
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instrucciones para configurar Azure Connect AD en un entorno híbrido.
ms.openlocfilehash: 5d27de4786c588d5d2f2a276dc20c25436bada98
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2018
ms.locfileid: "27244119"
---
# <a name="configure-azure-ad-connect-for-skype-for-business-and-teams"></a>Configurar Azure AD Connect para Skype para profesionales y los equipos 
 
Las organizaciones que tienen Skype para Business Server (o Lync Server) local y quién va a utilizar los equipos o Skype para profesionales Online deben configurar Azure Connect de AD para sincronizar su directorio local con Office 365, tal como se describe en este documento.  Esto incluye las organizaciones que mover directamente de Skype para empresarial local a los equipos. En particular, las organizaciones con Skype para empresarial local deben asegurarse de que se sincronizan los atributos msRTCSIP adecuados en Azure AD. 

> [!NOTE]
> Los usuarios existentes de los equipos que tienen también Skype para empresarial local necesitará tener su Skype para empresarial local cuenta movido a la nube con el fin de obtener la funcionalidad completa--como la capacidad para interoperar con Skype para usuarios profesionales y para comunicarse con los usuarios de organizaciones federadas. Incluso si el usuario sólo va a utilizar los equipos, se requiere este Skype en línea para la cuenta de empresa por la infraestructura para ofrecer la funcionalidad adicional.  Para que tenga lugar esta migración, debe asegurarse de que Azure Connect AD está configurado correctamente para que puede habilitar híbrida.
 

## <a name="background-information"></a>Información general

Azure Active Directory conectar mantiene su Active Directory local sincronizado continuamente con Office 365.  El directorio local permanece el origen de autoridad de identidad, y los cambios de su entorno local se sincronizan en Azure AD. Para obtener más información, consulte [Sincronización de conectarse de Azure AD](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis).  Incluso si no se mueven todos los usuarios de local a la nube, todos los usuarios que usan equipos, Skype para empresarial local o Skype para profesionales Online deben sincronizarse desde local en Azure AD para asegurar la comunicación entre los usuarios en línea y local . *Los usuarios de su organización se representará en los directorios en línea y local.*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Configuración de Azure Active Directory cuando tenga Skype para Business Server 

Si tiene un bosque de Active Directory local o de varios bosques, Azure Connect AD puede usarse en una gran variedad de topologías admitidas, tal como se describe en [topologías para conectar de Azure AD](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies).  Desde la perspectiva de Skype para Business Server, hay tres variantes principales: 

1. Un solo bosque, que contiene las identidades de usuario relevantes y hospeda Skype para Business Server. 

2. Varios bosques, solo uno de los cuales hospeda Skype para Business Server, así como uno o varios otros bosques que contienen las identidades de usuario relevantes (bosques de cuentas). 

3. Varias implementaciones de Skype para Business Server en varios bosques. Siempre que se cumplan determinados requisitos, las organizaciones pueden consolidar estas implementaciones de varios en un único inquilino de Office 365.

### <a name="single-forest"></a>Bosque único 

Si las cuentas de usuario y Skype para la empresa se hospedan en un solo bosque, debe asegurarse de que Azure Connect AD está configurado para sincronizar los usuarios de este bosque en Azure AD.  Aunque el Asistente para instalación de Azure Connect AD tiene una gran variedad de opciones, los atributos apropiados se sincronizan automáticamente en Azure Active Directory. Se recomienda a los clientes contra la modificación de las reglas de sincronización integrada o conectores que administración la configuración (que no es posible desde el Asistente para la instalación).  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>Varios bosques con una Skype para la implementación empresarial 

En este escenario se denomina a menudo una topología de bosque de recursos. Las identidades de los usuarios relevantes se hospedan en uno o más bosques de cuenta y Skype para la empresa se implementa en un bosque de recursos independiente (que a su vez puede hospedar las identidades de usuario autorizado). En general, Skype para las identidades de los usuarios empresariales relevantes puede ser en el mismo bosque que Skype para Business Server o en otro bosque, proporcionado: 

- Los usuarios con identidades relevantes de la cuenta encuentran se representan en el bosque de recursos (donde se implementa Skype para Business Server) como objetos de usuario deshabilitados, y el atributo msRTCSIP-OriginatorSID en el bosque de recursos coincide con el SID en el bosque de cuentas. Para obtener más información, vea [configurar un entorno de varios bosque para entornos híbridos Skype para la empresa](configure-a-multi-forest-environment-for-hybrid.md).

- El bosque de recursos hospedar Skype para Business Server confía en la cuenta encuentran.  

- Todos los objetos de usuario relevantes y los atributos de identidad tanto (de bosques de cuentas) y Skype para la empresa (bosque de recursos) se sincronizan en Azure AD con los valores correctos a través de Azure Connect de AD.  

 Para lograr el objeto apropiado y sincronización de los atributos en Azure AD en un [con varios bosques local escenario](configure-a-multi-forest-environment-for-hybrid.md), Microsoft recomienda encarecidamente el uso de Azure Connect de AD para sincronizar desde todos los bosques que han habilitado las cuentas de usuario y del bosque que contiene Skype para la empresa.  Suponiendo que sincronizar desde todos los bosques, a continuación, debe configurar Azure Connect de AD para combinar estas identidades y sincronizar a Azure AD. Conectar de Azure AD está diseñado para controlar este escenario y proporciona una opción en el Asistente para la instalación integrada para configurar esto, incluyendo la configuración de los anclajes para unirse a las identidades.  Elija lo siguiente: las identidades de usuario existen en varios directorios. Coincidencia con--> atributos ObjectSID y msExchangeMasterAccountSID.


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>Varios Skype para las implementaciones de Business Server en varios bosques 

En este escenario, hay varios bosques, cada contenedor Skype para Business Server y un único inquilino de Office 365.  Cada bosque que contiene Skype para Business Server puede sincronizarse en Azure AD para ese inquilino con AAD conectar. Como máximo, un solo bosque puede configurarse para Skype para entornos híbridos de negocio en un momento dado. Antes de habilitar híbrida en un bosque, se deben deshabilitar todos los dominios SIP de todos los otros bosques utilizando [disable-csonlineSipDomain](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain). Para obtener más información acerca de cómo consolidar un entorno de este tipo en Office 365, consulte [la consolidación en la nube para equipos y Skype para la empresa](cloud-consolidation.md).

## <a name="general-requirements"></a>Requisitos generales 

Los equipos y la Skype para servicios en línea de negocio requieren que los atributos de Active Directory correctos existen y que se rellenan en Azure AD.  Recomendación general de Microsoft es para sincronizar todos los bosques que contienen las identidades de usuario, así como en los bosques que contienen Skype para Business Server.

 Si existen las identidades de los usuarios en varios bosques, Azure Connect AD debe realizar la combinación. Cuando se sigue esta guía, Azure Connect AD sincronizará automáticamente los atributos correctos, siempre que no modifique los conectores o la reglas de sincronización en Azure Connect de AD. 
  
Si no se sincronizan desde todos los bosques que contienen las identidades de usuario y la Skype para la implementación de servidor empresarial, aún debe asegurarse de la identidad relevante y Skype para los atributos de negocio se rellena correctamente en Azure AD para cualquier usuario con los equipos o Skype para la empresa (si local o en línea)--que probablemente requerirá adicionales local de sincronización de directorios. Para obtener más información, vea [sincronización de Azure Connect AD: atributos que se sincronizan con Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized).

En estos casos, es responsabilidad del cliente para garantizar la configuración adecuada para rellenar los atributos en Azure AD. Tenga en cuenta lo siguiente: 

- Con una configuración no estándar para la sincronización de Azure AD es arriesgado porque podría llevar a una configuración incorrecta, lo que puede provocar daños en los datos en el directorio en línea.

- Como productos evolucionan, Microsoft seguirá comprobar las configuraciones de sincronización estándar en el que se sincronizan todos los bosques relevantes. Los clientes con las configuraciones de sincronización personalizados son responsables para garantizar que se que sus configuraciones de entregan los atributos correctos y los valores en Azure AD. 

## <a name="related-information"></a>Información relacionada

- [¿Qué es la identidad híbrida](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/whatis-hybrid-identity?toc=%2Fen-us%2Fazure%2Factive-directory%2Fhybrid%2FTOC.json&bc=%2Fen-us%2Fazure%2Fbread%2Ftoc.json)

- [Sincronización de Azure AD Connect: comprender y personalizar la sincronización](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Conectan de topologías para Azure AD](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies)

- [Sincronización de Azure AD Connect: atributos que se sincronizan con Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
