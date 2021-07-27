---
title: Implementación del recurso de topología entre bosques
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
description: Las siguientes secciones descrbien cómo configurar un entorno que tiene varios bosques en un modelo de bosque de recursos o usuarios para proporcionar funcionalidad en un escenario híbrido.
ms.openlocfilehash: 3de0309681842eabe2924e6b489a6acbdc71c1b7
ms.sourcegitcommit: 3f1635d1915561798ea764c3e33d7db55f7e49da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2021
ms.locfileid: "53574115"
---
# <a name="deploy-a-resource-forest-topology"></a>Implementación del recurso de topología entre bosques

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 
En las secciones siguientes se describe cómo configurar un entorno que tiene varios bosques en un modelo de bosque de recursos o usuarios para proporcionar funcionalidad en un escenario híbrido. 
  
![Entorno de varios bosques para híbrido](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a>Requisitos de la topología

Se admiten varios bosques de usuarios. Tenga en cuenta lo siguiente: 
    
- Para obtener versiones compatibles de Lync Server y Skype Empresarial Server en una configuración híbrida, vea [Plan hybrid connectivity](plan-hybrid-connectivity.md).
    
- Exchange Server puede implementarse en uno o más bosques, lo que puede incluir o no el bosque que contiene Skype Empresarial Server. Asegúrese de que ha aplicado la actualización acumulativa más reciente.
    
- Para obtener información detallada sobre la coexistencia con Exchange Server, incluidos los criterios de soporte técnico y las limitaciones en varias combinaciones de locales y en línea, vea [Feature support](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) in Plan to integrate Skype Empresarial [and Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
    
  
## <a name="user-homing-considerations"></a>Consideraciones sobre la homilía de usuarios

Skype Empresarial los usuarios locales pueden tener Exchange local o en línea. Teams usuarios deben usar Exchange Online para una experiencia óptima; sin embargo, esto no es necesario. Exchange local no es necesario implementar Skype Empresarial en ambos casos.
  
## <a name="configure-forest-trusts"></a>Configurar confianzas de bosque

En una topología de bosque de recursos, los bosques de recursos que hospedan Skype Empresarial Server deben confiar en cada bosque de cuentas que contenga las cuentas de los usuarios que tendrán acceso a él. 

Si tiene varios bosques de usuarios, para habilitar la autenticación entre bosques, es importante que el enrutamiento de sufijos de nombre esté habilitado para cada una de estas confianzas de bosque. Para obtener instrucciones, vea [Managing Forest Trusts](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772440(v=ws.11)). 

Si ha implementado Exchange Server en otro bosque y Exchange proporciona funcionalidad a los usuarios de Skype Empresarial, el Exchange de hospedaje del bosque debe confiar en el Skype Empresarial Server. Por ejemplo, si Exchange se implementaron en el bosque de cuentas, se requiere una confianza de dos vías entre la cuenta y Skype Empresarial bosques.
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>Sincronizar cuentas en el bosque que hospeda Skype Empresarial

Suponga Skype Empresarial Server se implementa en un bosque (un bosque de recursos), pero proporciona funcionalidad a los usuarios de uno o más bosques (bosques de cuentas). En este caso, los usuarios de los demás bosques deben representarse como objetos de usuario deshabilitados en el bosque donde Skype Empresarial Server se implementa.

Debe usar un producto de administración de identidades, como Microsoft Identity Manager, para aprovisionar y sincronizar los usuarios de los bosques de cuentas en el bosque donde Skype Empresarial Server se implementa. Los usuarios deben sincronizarse en el bosque que hospeda Skype Empresarial Server como objetos de usuario deshabilitados. Los usuarios no se pueden sincronizar como objetos de contacto de Active Directory, ya que Azure Active Directory Conectar sincronizará correctamente los contactos en Azure AD para usarlos con Skype.
  
Independientemente de cualquier configuración de varios bosques, el Skype Empresarial Server también puede proporcionar funcionalidad para los usuarios habilitados que existen en el mismo bosque.
  
Para obtener la sincronización de identidades adecuada, es necesario sincronizar los siguientes atributos: 
  
|**Bosques de usuarios**|**Bosques de recursos**|
|:-----|:-----|
|atributo de vínculo de cuenta elegido  <br/> |atributo de vínculo de cuenta elegido  <br/> |
|mail  <br/> |mail  <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
El [atributo de vínculo de cuenta elegido](/azure/active-directory/hybrid/plan-connect-design-concepts) se usará como delimitador de origen. Si tiene un atributo diferente e inmutable que prefiere usar, puede hacerlo; solo asegúrate de editar la regla de notificaciones de AD FS y seleccionar el atributo durante la configuración Conectar AAD.
  
No sincronice los UPN entre los bosques. Debe usar un UPN único para cada bosque de usuarios, ya que no puede usar el mismo UPN en varios bosques. Como resultado, hay dos posibilidades: sincronizar el UPN o no sincronizar. 
  
- Si el UPN único de cada bosque de usuarios no se sincronice con el objeto deshabilitado asociado en el bosque de recursos, el inicio de sesión único (SSO) se rompería para al menos el intento de inicio de sesión inicial (suponiendo que el usuario haya seleccionado la opción para guardar la contraseña). En el Skype Empresarial, se supone que los valores SIP/UPN son los mismos. Dado que la dirección SIP de este escenario es user@company.com, pero el UPN del objeto habilitado en el bosque de usuarios es de hecho user@contoso.company.com, se producirá un error en el intento de inicio de sesión inicial y se pedirá al usuario que escriba las credenciales. Al escribir su UPN correcto, la solicitud de autenticación se completaría con los controladores de dominio del bosque de usuarios y el inicio de sesión se realizaría correctamente.
    
- Si el UPN único de cada bosque de usuarios se sincronice con el objeto deshabilitado asociado en el bosque de recursos, se producirá un error en la autenticación de AD FS. La regla de coincidencia encontraría el UPN en el objeto del bosque de recursos, que estaba deshabilitado y no se podía usar para la autenticación. 
    
## <a name="create-a-microsoft-365-or-office-365-organization"></a>Crear una Microsoft 365 o Office 365 organización

Deberá aprovisionar una organización Microsoft 365 usar con la implementación. Para obtener más información, consulte [Suscripciones, licencias, cuentas](/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings)e inquilinos para las ofertas en la nube de Microsoft. 
  
## <a name="configure-active-directory-federation-services"></a>Configurar los servicios de federación de Active Directory

Una vez que tenga un inquilino, deberá configurar los Servicios de federación de Active Directory (AD FS) en cada uno de los bosques de usuarios. Esto supone que tiene una dirección SIP y SMTP única y un nombre principal de usuario (UPN) para cada bosque. AD FS es opcional y se usa aquí para obtener el inicio de sesión único (SSO). DirSync con sincronización de contraseñas también es compatible y también se puede usar en lugar de AD FS. 
  
Solo se probaron las implementaciones con SIP/SMTP y UPN que coincidan. Si no hay SIP/SMTP/UPN que coincidan, puede que se reduzca la funcionalidad, como problemas con Exchange integración y SSO. 
  
A menos que uses un SIP/SMTP/UPN único para los usuarios de cada bosque, aún puedes encontrar problemas de SSO, independientemente de dónde se implemente AD FS: 
  
- Confianzas uneduarias o de dos vías entre bosques de recursos/usuarios con granja de ad FS implementada en cada bosque de usuarios, todos los usuarios comparten un dominio SIP/SMTP común, pero UPN único para cada bosque de usuarios. 
    
- Confianzas en dos direcciones entre bosques de recursos y usuarios con la granja de AD FS implementada solo en el bosque de recursos, todos los usuarios comparten un dominio SIP/SMTP común, pero UPN único para cada bosque de usuarios. 
    
Al colocar una granja de AD FS en cada bosque de usuarios y usar un SIP/SMTP/UPN único para cada bosque, resolvemos ambos problemas. Solo se buscarán y coincidirán las cuentas de ese bosque de usuarios específico durante los intentos de autenticación. Esto ayudará a proporcionar un proceso de autenticación más fluido. 
  
Esta implementación será una implementación estándar del Windows Server 2012 R2 AD FS y debe funcionar antes de continuar. Para obtener instrucciones, [consulta Cómo instalar AD FS 2012 R2 Para](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx)obtener Microsoft 365 o Office 365 . 
  
Una vez implementado, debe editar la regla de notificaciones para que coincida con el delimitador de origen seleccionado anteriormente. En LA MMC de AD FS, en Confianzas de usuario de confianza, haga clic con el botón secundario en **Microsoft 365 Identity Platform** o Microsoft Office 365 Identity Platform y, **a** continuación, seleccione Editar **reglas de** notificación. Edite la primera regla y cambie ObjectSID a **employeeNumber**. 
  
![Pantalla De reglas de edición de varios bosques](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>Configurar AAD Conectar

En las topologías de bosque de recursos, es necesario que los atributos de usuario del bosque de recursos y los bosques de cuentas se sincronicen en Azure AD. Microsoft recomienda que Azure AD Conectar y combine las  identidades de usuario de todos los bosques que tienen cuentas de usuario habilitadas y el bosque que contiene Skype Empresarial. Para obtener más información, vea [Configure Azure AD Conectar for Skype Empresarial and Teams](configure-azure-ad-connect.md).

Tenga en cuenta que Azure AD Conectar no proporciona sincronización local entre los bosques de cuentas y recursos. Esto debe configurarse mediante Microsoft Identity Manager o un producto similar, como se describió anteriormente.
  
Cuando termine y azure AD Conectar se combina, si observa un objeto en el metaverso, debería ver algo similar a lo siguiente: 
  
![Pantalla de objetos metaverso de varios bosques](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
Los atributos resaltados en verde se combinaron Microsoft 365, los amarillos son del bosque de usuarios y el azul del bosque de recursos. 
  
En este ejemplo, Azure AD Conectar ha identificado el sourceAnchor y el cloudSourceAnchor del usuario y los objetos de bosque de recursos de Microsoft 365, en este caso 1101, el employeeNumber seleccionado anteriormente. Azure AD Conectar pudieron combinar este objeto con lo que ves anteriormente. 
  
Para obtener más información, vea [Integrar los directorios](/azure/active-directory/hybrid/whatis-hybrid-identity)locales con Azure Active Directory . 
  
Azure AD Conectar debe instalarse con los valores predeterminados, excepto por lo siguiente: 
  
1. Inicio de sesión único: con AD FS ya implementado y funcionando: seleccione **No configurar**.
    
2. Conectar directorios: agregue todos los dominios.
    
3. Identificar usuarios en directorios locales: seleccione Identidades de usuario existen en varios **directorios** y seleccione los atributos **ObjectSID** y **msExchangeMasterAccountSID.**
    
4. Identificar usuarios en Azure AD: Delimitador de origen: seleccione el atributo que ha elegido después de leer Seleccionar un atributo [sourceAnchor](/azure/active-directory/hybrid/plan-connect-design-concepts#selecting-a-good-sourceanchor-attribute)bueno , Nombre principal de usuario - **userPrincipalName**.
    
5.  Características opcionales: seleccione si ha implementado Exchange híbrida.
    
    > [!NOTE]
    >  Si solo ha Exchange Online, podría haber un problema con errores de OAuth durante la detección automática debido al redireccionamiento CNAME. Para corregir esto, deberá establecer la dirección URL de detección Exchange mediante la ejecución del siguiente cmdlet desde el Shell de administración de Skype Empresarial Server:
    >
    > ```powershell
    > Set-CsOAuthConfiguration -ExchangeAutoDiscoverURL https://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    > ```
    
6.  Granja de servidores de AD FS: seleccione Usar una granja de **servidores Windows Server 2012 de R2 AD FS** y escriba el nombre del servidor de AD FS.
    
7.  Finalice el asistente y realice las validaciones necesarias.
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>Configurar la conectividad híbrida para Skype Empresarial Server

Siga los procedimientos recomendados para configurar Skype Empresarial híbrido. Para obtener más información, vea [Plan hybrid connectivity y](plan-hybrid-connectivity.md) Configure hybrid [connectivity](configure-hybrid-connectivity.md). 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>Configurar la conectividad híbrida para Exchange Server

Si es necesario, siga los procedimientos recomendados para configurar Exchange híbrido. Para obtener más información, [vea Exchange Server Hybrid Deployments](/exchange/exchange-hybrid). 
