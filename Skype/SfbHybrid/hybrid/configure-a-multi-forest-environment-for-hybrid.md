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
description: Las secciones siguientes proporcionan instrucciones sobre cómo configurar un entorno que tiene varios bosques en un modelo de bosque de recursos/usuarios para proporcionar la funcionalidad de Skype Empresarial en un escenario híbrido.
ms.openlocfilehash: cf3a162001756661afd0f204e9968713d9db0f5b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221484"
---
# <a name="deploy-a-resource-forest-topology"></a>Implementación del recurso de topología entre bosques
 
Las secciones siguientes proporcionan instrucciones sobre cómo configurar un entorno que tiene varios bosques en un modelo de bosque de recursos/usuarios para proporcionar la funcionalidad de Skype Empresarial en un escenario híbrido. 
  
![Entorno de varios bosques para híbrido](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a>Requisitos de la topología

Se admiten varios bosques de usuarios. Tenga en cuenta lo siguiente: 
    
- Para ver las versiones compatibles de Lync Server y [](plan-hybrid-connectivity.md#server-version-requirements) Skype Empresarial Server en una configuración híbrida, consulte Requisitos de versión del servidor en Plan de conectividad híbrida entre Skype Empresarial Server y [Microsoft 365 u Office 365.](plan-hybrid-connectivity.md)
    
- Exchange Server puede implementarse en uno o más bosques, que pueden incluir o no el bosque que contiene Skype Empresarial Server. Asegúrese de que ha aplicado la actualización acumulativa más reciente.
    
- Para obtener más información sobre la coexistencia con Exchange Server, incluidos los criterios de [](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) compatibilidad y las limitaciones en varias combinaciones de local y en línea, vea la compatibilidad con características en plan para integrar Skype Empresarial y [Exchange.](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
    
  
## <a name="user-homing-considerations"></a>Consideraciones sobre la homilía de usuarios

Los usuarios de Skype Empresarial que se alojen localmente pueden tener Exchange local o en línea. Los usuarios de Skype Empresarial Online deben usar Exchange Online para una experiencia óptima; sin embargo, esto no es necesario. Exchange local no es necesario para implementar Skype Empresarial en ninguno de los casos.
  
## <a name="configure-forest-trusts"></a>Configurar confianzas de bosque

En una topología de bosque de recursos, los bosques de recursos que hospedan Skype Empresarial Server deben confiar en cada bosque de cuentas que contenga las cuentas de los usuarios que tendrán acceso a él. Si tiene varios bosques de usuarios, para habilitar la autenticación entre bosques es importante que el enrutamiento de sufijos de nombre esté habilitado para cada una de estas confianzas de bosque. Para obtener instrucciones, vea [Managing Forest Trusts](https://technet.microsoft.com/library/cc772440.aspx). Si ha implementado Exchange Server en otro bosque y proporciona funcionalidad a los usuarios de Skype Empresarial, el bosque que hospeda Exchange debe confiar en el bosque que hospeda Skype Empresarial Server. Por ejemplo, si Exchange se implementó en el bosque de cuentas, esto significaría efectivamente que se requiere una confianza de dos vías entre los bosques de cuenta y skype empresarial en esa configuración.
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>Sincronizar cuentas en el bosque que hospeda Skype Empresarial

Cuando Skype Empresarial Server se implementa en un bosque (un bosque de recursos), pero proporciona funcionalidad a los usuarios de uno o más bosques (bosques de cuentas), los usuarios de los otros bosques deben representarse como objetos de usuario deshabilitados en el bosque donde se implementa Skype Empresarial Server. Un producto de administración de identidades, como Microsoft Identity Manager, debe implementarse y configurarse para aprovisionar y sincronizar los usuarios de los bosques de cuentas en el bosque donde se implementa Skype Empresarial Server. Los usuarios deben sincronizarse en el bosque que hospeda Skype Empresarial Server como objetos de usuario deshabilitados. Los usuarios no se pueden sincronizar como objetos de contacto de Active Directory, porque Azure Active Directory Connect no sincronizará correctamente los contactos en Azure AD para usarlos con Skype.
  
Independientemente de cualquier configuración de varios bosques, el bosque que hospeda Skype Empresarial Server también puede proporcionar funcionalidad para los usuarios habilitados que existen en el mismo bosque.
  
Para obtener una sincronización de identidad correcta, deben sincronizarse los siguientes atributos: 
  
|**Bosques de usuarios**|**Bosques de recursos**|
|:-----|:-----|
|atributo de vínculo de cuenta elegida  <br/> |atributo de vínculo de cuenta elegida  <br/> |
|mail  <br/> |mail  <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
El [atributo de vínculo de cuenta elegido](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts) se usará como delimitador de origen. Si tiene un atributo diferente e inmutable que prefiere usar, puede hacerlo; Asegúrese de editar la regla de notificaciones de AD FS y seleccionar el atributo durante la configuración de AAD Connect.
  
No sincronice los UPN entre los bosques. Durante las pruebas, encontramos que era necesario usar un UPN único para cada bosque de usuarios, ya que no se puede usar el mismo UPN en varios bosques. Como resultado, se nos presentaron dos posibilidades: sincronizar el UPN o no sincronizar. 
  
- Si el UPN único de cada bosque de usuarios no se sincroniza con el objeto deshabilitado asociado en el bosque de recursos, el inicio de sesión único (SSO) se rompería para al menos el intento de inicio de sesión inicial (suponiendo que el usuario haya seleccionado la opción para guardar la contraseña). En el cliente de Skype Empresarial, se supone que los valores sip/UPN son los mismos. Dado que la dirección SIP en este escenario es user@company.com, pero el UPN del objeto habilitado en el bosque de usuarios es de hecho user@contoso.company.com, se producirá un error en el intento de inicio de sesión inicial y se pedirá al usuario que escriba las credenciales. Al escribir el UPN correcto/real, la solicitud de autenticación se completaría con los controladores de dominio del bosque de usuarios y el inicio de sesión se realizaría correctamente.
    
- Si el UPN único de cada bosque de usuarios se sincroniza con el objeto deshabilitado asociado en el bosque de recursos, se produciría un error en la autenticación de AD FS. La regla de coincidencia encontraría el UPN en el objeto del bosque de recursos, que se deshabilitó y no se pudo usar para la autenticación. 
    
## <a name="create-a-microsoft-365-or-office-365-organization"></a>Crear una organización de Microsoft 365 u Office 365

A continuación, deberá aprovisionar una organización de Microsoft 365 u Office 365 para usarla con la implementación. Para obtener más información, vea [Suscripciones, licencias, cuentas](https://docs.microsoft.com/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings)e inquilinos para las ofertas de nube de Microsoft. 
  
## <a name="configure-active-directory-federation-services"></a>Configurar los servicios de federación de Active Directory

Una vez que tenga un inquilino, deberá configurar los Servicios de federación de Active Directory (AD FS) en cada uno de los bosques de usuarios. Se supone que tiene una dirección SIP y SMTP única y un nombre principal de usuario (UPN) para cada bosque. AD FS es opcional y se usa aquí para obtener el inicio de sesión único (SSO). DirSync con sincronización de contraseñas también es compatible y también se puede usar en lugar de AD FS. 
  
Solo se probaron las implementaciones con SIP/SMTP y UPN correspondientes. Si no hay SIP/SMTP/UPN que coincidan, es posible que se reduzca la funcionalidad, como problemas con la integración de Exchange y SSO. 
  
A menos que use un SIP/SMTP/UPN único para los usuarios de cada bosque, aún puede encontrarse con problemas de SSO, independientemente de dónde se implemente AD FS: 
  
- Confianzas uneduarias o dos vías entre bosques de recursos y usuarios con granja de AD FS implementada en cada bosque de usuarios, todos los usuarios comparten un dominio SIP/SMTP común, pero un UPN único para cada bosque de usuarios. 
    
- Confianzas de dos vías entre bosques de recursos y usuarios con granja de AD FS implementada solo en el bosque de recursos, todos los usuarios comparten un dominio SIP/SMTP común pero un UPN único para cada bosque de usuarios. 
    
Al colocar una granja de AD FS en cada bosque de usuarios y usar un SIP/SMTP/UPN único para cada bosque, se resuelven ambos problemas. Solo se buscarían las cuentas de ese bosque de usuarios específico y se buscarían coincidencias durante los intentos de autenticación. Esto le ayudará a proporcionar un proceso de autenticación más fluido. 
  
Esta será una implementación estándar de WINDOWS Server 2012 R2 AD FS y debería estar funcionando antes de continuar. Para obtener instrucciones, [consulte Cómo instalar AD FS 2012 R2 para Microsoft 365 u Office 365.](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx) 
  
Una vez implementada, tendrá que editar la regla de notificaciones para que coincida con el delimitador de origen seleccionado anteriormente. En LA MMC de AD FS, en Confianzas de usuario de confianza, haga clic con el botón secundario en Plataforma de identidad de **Microsoft 365** o plataforma de identidad de **Microsoft Office 365** y, a continuación, seleccione Editar reglas de **notificación.** Edite la primera regla y cambie ObjectSID a **employeeNumber**. 
  
![Pantalla de reglas de edición de varios bosques](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>Configurar AAD Connect

En las topologías de bosque de recursos, es necesario que los atributos de usuario del bosque de recursos y los bosques de cuentas se sincronicen en Azure AD. La forma más sencilla y recomendada de hacerlo es hacer que  Azure AD Connect sincronice y combine las identidades de usuario de todos los bosques que tienen cuentas de usuario habilitadas y el bosque que contiene Skype Empresarial. Para obtener más información, [consulte Configurar Azure AD Connect para Skype Empresarial y Teams.](configure-azure-ad-connect.md)

Tenga en cuenta que AAD Connect no proporciona sincronización local entre la cuenta y los bosques de recursos. Debe configurarse por separado con Microsoft Identity Manager o un producto similar, como se describió anteriormente.
  
Cuando termine y AAD Connect se esté combinando, si observa un objeto en el metaverso, debería ver algo similar a esto: 
  
![Pantalla de objetos de metaverso de varios bosques](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
Los atributos de color verde resaltado se combinaron de Microsoft 365 u Office 365, los amarillos son del bosque de usuarios y los azules del bosque de recursos. 
  
Este es un usuario de prueba y puede ver que AAD Connect ha identificado el sourceAnchor y cloudSourceAnchor del usuario y los objetos del bosque de recursos de Microsoft 365 u Office 365, en nuestro caso 1101, que es el employeeNumber seleccionado anteriormente. A continuación, fue capaz de combinar este objeto en lo que se ve anteriormente. 
  
Para obtener más información, vea [Integrar los directorios locales con Azure Active Directory.](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) 
  
AAD Connect debe instalarse con los valores predeterminados, excepto los siguientes: 
  
1. Inicio de sesión único: con AD FS ya implementado y en funcionamiento: seleccione **No configurar.**
    
2. Conecte los directorios: agregue todos los dominios.
    
3. Identifique a los usuarios en directorios locales: existen identidades de usuario seleccionadas en varios directorios y seleccione los atributos **ObjectSID** y **msExchangeMasterAccountSID.**
    
4. Identificar usuarios en Azure AD: Delimitador de origen: seleccione el atributo que ha elegido después de leer Seleccionar un buen atributo [sourceAnchor](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts#selecting-a-good-sourceanchor-attribute), Nombre principal de usuario - **userPrincipalName**.
    
5.  Características opcionales: seleccione si ha implementado Exchange híbrido.
    
    > [!NOTE]
    >  Si solo tiene Exchange Online, podría haber un problema con errores de OAuth durante la detección automática debido al redireccionamiento CNAME. Para corregir esto, deberá establecer la dirección URL de Detección automática de Exchange ejecutando el siguiente cmdlet desde el Shell de administración de Skype Empresarial Server:
    >
    > ```powershell
    > Set-CsOAuthConfiguration -ExchangeAutoDiscoverURL https://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    > ```
    
6.  Granja de AD FS: seleccione Usar una granja de servidores de AD FS existente de **Windows Server 2012 R2** y escriba el nombre del servidor de AD FS.
    
7.  Finalice el asistente y realice las validaciones necesarias.
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>Configurar la conectividad híbrida para Skype Empresarial Server

Siga los procedimientos recomendados para configurar Skype Empresarial híbrido. Para obtener más información, vea [Planear la conectividad híbrida](plan-hybrid-connectivity.md) y configurar la conectividad [híbrida.](configure-hybrid-connectivity.md) 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>Configurar la conectividad híbrida para Exchange Server

Si es necesario, siga los procedimientos recomendados para configurar Exchange híbrido. Para obtener más información, [vea Exchange Server implementaciones híbridas.](https://docs.microsoft.com/exchange/exchange-hybrid) 
  
