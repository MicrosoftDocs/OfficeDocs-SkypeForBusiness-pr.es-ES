---
title: Implementación de una topología de bosque de recursos
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: En las secciones siguientes se proporcionan instrucciones sobre cómo configurar un entorno con varios bosques en un modelo de bosque de recursos y usuarios para proporcionar funcionalidad de Skype empresarial en un escenario híbrido.
ms.openlocfilehash: f018699040fc202cbe827a2b8b05bd1f4371e190
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726950"
---
# <a name="deploy-a-resource-forest-topology"></a>Implementación de una topología de bosque de recursos
 
En las secciones siguientes se proporcionan instrucciones sobre cómo configurar un entorno con varios bosques en un modelo de bosque de recursos y usuarios para proporcionar funcionalidad de Skype empresarial en un escenario híbrido. 
  
![Entorno de varios bosques para entornos híbridos](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a>Requisitos de la topología

Se admiten varios bosques de usuarios. Tenga en cuenta lo siguiente: 
    
- Para las versiones compatibles de Lync Server y Skype empresarial Server en una configuración híbrida, vea [requisitos](plan-hybrid-connectivity.md#server-version-requirements) de la versión del servidor en [plan Hybrid Connectivity between Skype for Business server y Office 365](plan-hybrid-connectivity.md).
    
- Exchange Server se puede implementar en uno o más bosques, que pueden o no incluir el bosque que contiene Skype empresarial Server. Asegúrese de que ha aplicado la actualización acumulativa más reciente.
    
- Para obtener información detallada sobre la coexistencia con Exchange Server, incluidos los criterios y las limitaciones de la compatibilidad en varias combinaciones de local y en línea, consulte [Feature support](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) in [plan to Integrate Skype for Business and Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
    
  
## <a name="user-homing-considerations"></a>Consideraciones sobre el alojamiento de usuarios

Los usuarios de Skype empresarial hospedados en local pueden tener Exchange hospedado en local o en línea. Los usuarios de Skype empresarial online deben usar Exchange Online para obtener una experiencia óptima; sin embargo, esto no es necesario. Exchange local no es necesario para implementar Skype empresarial en ninguno de los casos.
  
## <a name="configure-forest-trusts"></a>Configurar confianzas de bosque

En una topología de bosque de recursos, los bosques de recursos que hospedan Skype empresarial Server deben confiar en cada bosque de cuentas que contiene las cuentas de los usuarios que tendrán acceso a ella. Si tiene varios bosques de usuarios, para habilitar la autenticación entre bosques es importante que el enrutamiento de sufijo de nombre esté habilitado para cada una de estas confianzas de bosque. Para obtener instrucciones, consulte [Managing Forest trusts](https://technet.microsoft.com/en-us/library/cc772440.aspx). Si tiene Exchange Server implementado en otro bosque y proporciona funcionalidad para los usuarios de Skype empresarial, el bosque que hospeda a Exchange debe confiar en el bosque que hospeda Skype empresarial Server. Por ejemplo, si se implementó Exchange en el bosque de cuentas, esto implicaría que sería necesaria una confianza bidireccional entre la cuenta y los bosques de Skype empresarial en esa configuración.
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>Sincronizar cuentas en el bosque que hospeda Skype empresarial

Cuando Skype empresarial Server se implementa en un bosque (un bosque de recursos), pero proporciona funcionalidad a los usuarios en uno o más bosques (bosques de cuentas), los usuarios de los otros bosques deben representarse como objetos de usuario deshabilitados en el bosque en el que Skype Business Server está implementado. Un producto de administración de identidades, como Microsoft Identity Manager, debe implementarse y configurarse para aprovisionar y sincronizar a los usuarios de los bosques de cuentas en el bosque donde se implementa Skype empresarial Server. Los usuarios deben estar sincronizados en el bosque que hospeda Skype empresarial Server como objetos de usuario deshabilitados. Los usuarios no se pueden sincronizar como objetos de contacto de Active Directory, porque Azure Active Directory Connect no sincronizará correctamente los contactos en Azure AD para usar con Skype.
  
Independientemente de la configuración de varios bosques, el bosque que hospeda Skype empresarial Server también puede proporcionar funcionalidad a todos los usuarios habilitados que existen en el mismo bosque.
  
Para obtener la sincronización de identidades correcta, se deben sincronizar los siguientes atributos: 
  
|**Bosques de usuarios**|**Bosques de recursos**|
|:-----|:-----|
|atributo de vínculo de cuenta elegido  <br/> |atributo de vínculo de cuenta elegido  <br/> |
|mail  <br/> |mail  <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
El [atributo de vínculo de cuenta elegido](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-design-concepts/) se usará como el delimitador de origen. Si tiene un atributo diferente e inmutable que preferiría usar, puede hacerlo; solo tiene que asegurarse de editar la regla de notificaciones de AD FS y seleccionar el atributo durante la configuración de AAD Connect.
  
No sincronice los UPN entre los bosques. Encontramos durante las pruebas que necesitábamos usar un UPN único para cada bosque de usuarios, ya que no se puede usar el mismo UPN en varios bosques. Como resultado, se presentaron dos posibilidades para sincronizar el UPN o no sincronizar. 
  
- Si el UPN único de cada bosque de usuarios no se sincronizó con el objeto deshabilitado asociado en el bosque de recursos, el inicio de sesión único (SSO) se interrumpió por lo menos por el intento de inicio de sesión inicial (suponiendo que el usuario seleccionó la opción para guardar la contraseña). En el cliente de Skype empresarial, se da por sentado que los valores SIP/UPN son los mismos. Como la dirección SIP de este escenario es user@company.com, pero el UPN del objeto habilitado en el bosque de usuarios está en realidad user@contoso.company.com, el intento de inicio de sesión inicial no se realizará correctamente y se le pedirá al usuario que especifique las credenciales. Después de escribir su UPN correcto o real, la solicitud de autenticación se completará en los controladores de dominio del bosque de usuarios y el inicio de sesión se realizaría correctamente.
    
- Si el UPN único de cada bosque de usuarios se ha sincronizado con el objeto deshabilitado asociado en el bosque de recursos, se producirá un error en la autenticación de AD FS. La regla de coincidencia encontraría el UPN en el objeto en el bosque de recursos, que se ha deshabilitado y no se ha podido usar para la autenticación. 
    
## <a name="create-an-office-365-tenant"></a>Crear un inquilino de Office 365

A continuación, deberá aprovisionar un inquilino de Office 365 para usarlo con la implementación de. Para obtener más información, vea [suscripciones, licencias, cuentas e inquilinos para las ofertas de la nube de Microsoft](https://docs.microsoft.com/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings). 
  
## <a name="configure-active-directory-federation-services"></a>Configurar los servicios de Federación de Active Directory

Una vez que tenga un espacio empresarial, tendrá que configurar los servicios de Federación de Active Directory (AD FS) en cada uno de los bosques de usuarios. Esto supone que tiene una dirección SMTP y SIP única y un nombre principal de usuario (UPN) para cada bosque. AD FS es opcional y se usa aquí para obtener el inicio de sesión único (SSO). DirSync también es compatible con la sincronización de contraseña y también se puede usar en vez de AD FS. 
  
Solo se probaron las implementaciones con SIP/SMTP y UPN que coincidan. No tener un SIP/SMTP/UPN que coincida puede dar como resultado una funcionalidad reducida, como problemas con la integración de Exchange y SSO. 
  
A menos que use un SIP/SMTP/UPN único para los usuarios de cada bosque, aún puede ejecutar problemas de SSO, independientemente de dónde se implemente AD FS: 
  
- Confianzas unidireccionales o bidireccionales entre bosques de recursos o usuarios con una granja de AD FS implementada en cada bosque de usuarios, todos los usuarios comparten un dominio SIP/SMTP común, pero único UPN para cada bosque de usuarios. 
    
- Confianzas bidireccionales entre bosques de recursos o usuarios con la granja de AD FS implementada solo en el bosque de recursos, todos los usuarios comparten el dominio SIP/SMTP común, pero el UPN único para cada bosque de usuarios. 
    
Al colocar una granja de AD FS en cada bosque de usuarios y usar un SIP/SMTP/UPN único para cada bosque, se resuelven ambos problemas. Durante los intentos de autenticación, se buscarán y coincidirán solo las cuentas de ese bosque de usuarios específico. Esto le ayudará a proporcionar un proceso de autenticación más transparente. 
  
Se trata de una implementación estándar de AD FS de Windows Server 2012 R2 y debe estar funcionando antes de continuar. Para obtener instrucciones, consulte [How to Install AD FS 2012 R2 for Office 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx). 
  
Una vez implementado, tendrá que editar la regla de notificaciones para que se corresponda con el delimitador de origen seleccionado anteriormente. En la consola MMC de AD FS, en relaciones de confianza para usuarios autenticados, haga clic con el botón secundario en **Microsoft Office 365 Identity Platform**y, a continuación, haga clic en **editar reglas de notificación**. Edite la primera regla y cambie ObjectSID a **employeeNumber**. 
  
![Pantalla de edición de reglas de varios bosques](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>Configurar AAD Connect

En las topologías de bosque de recursos, es necesario que los atributos de usuario del bosque de recursos y los bosques de la cuenta se sincronicen en Azure AD. La forma más sencilla y recomendada de hacerlo es que Azure AD Connect sincronice y combine las identidades de usuario de *todos los* bosques que tengan cuentas de usuario habilitadas y el bosque que contenga Skype empresarial. Para obtener información detallada, vea [configurar Azure ad Connect para Skype empresarial y Teams](configure-azure-ad-connect.md).

Tenga en cuenta que AAD Connect no proporciona sincronización local entre los bosques de cuentas y recursos. Que se deben configurar por separado mediante Microsoft Identity Manager o un producto similar, como se describió anteriormente.
  
Cuando termine y la conexión de AAD se esté combinando, si observa un objeto en el metaverso, verá algo parecido a esto: 
  
![Pantalla de objeto de metaverso de varios bosques](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
Los atributos resaltados verdes se combinaron desde Office 365, el amarillo son del bosque de usuarios y el azul procede del bosque de recursos. 
  
Este es un usuario de prueba y puede ver que AAD Connect ha identificado la sourceAnchor y cloudSourceAnchor del usuario y los objetos de bosque de recursos de Office 365, en nuestro caso 1101, que es la employeeNumber seleccionada anteriormente. A continuación, pudo combinar este objeto en lo que se ve más arriba. 
  
Para obtener más información, consulte [integrar los directorios locales con Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/). 
  
AAD Connect debe instalarse con los valores predeterminados, excepto los siguientes: 
  
1. Inicio de sesión único: AD FS ya se ha implementado y en funcionamiento: seleccione no **configurar**.
    
2. Conecte los directorios: Agregue todos los dominios.
    
3. Identificar a los usuarios en directorios locales: seleccione las **identidades de usuario que existen en varios directorios**y seleccione los atributos **ObjectSID** y **msExchangeMasterAccountSID** .
    
4. Identificar usuarios en Azure AD: delimitador de origen: seleccione el atributo que ha elegido después de leer [seleccionando un buen atributo de sourceAnchor](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-design-concepts/), nombre principal de usuario- **userPrincipalName**.
    
5.  Características opcionales: Seleccione si tiene implementado Exchange híbrido.
    
    > [!NOTE]
    >  Si solo tiene Exchange Online, podría haber un problema con los errores de OAuth durante la detección automática debido a la redirección de CNAME. Para corregir esto, tendrá que establecer la dirección URL de detección automática de Exchange mediante la ejecución del siguiente cmdlet desde el shell de administración de Skype empresarial Server:
  
    Set-CsOAuthConfiguration-ExchangeAutoDiscoverURL https://<span>Autodiscover-s.Outlook.com/Autodiscover/Autodiscover.SVC 
    
6.  Granja de AD FS: seleccione usar una granja de servidores de ad **FS existente de Windows Server 2012 R2** y escriba el nombre del servidor de AD FS.
    
7.  Finalice el asistente y realice las validaciones necesarias.
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>Configurar la conectividad híbrida para Skype empresarial Server

Siga los procedimientos recomendados para configurar el entorno híbrido de Skype empresarial. Para obtener más información, consulte [planear la conectividad híbrida](plan-hybrid-connectivity.md) y [configurar la conectividad híbrida](configure-hybrid-connectivity.md). 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>Configurar la conectividad híbrida para Exchange Server

Si es necesario, siga los procedimientos recomendados para configurar la implementación híbrida de Exchange. Para obtener más información, consulte [implementaciones híbridas de Exchange Server](https://docs.microsoft.com/en-us/exchange/exchange-hybrid). 
  

