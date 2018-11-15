---
title: Configurar un entorno de varios bosque para entornos híbridos Skype para la empresa
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/17/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 960ab8a3-352d-4b18-bc01-55b35f30ca0d
description: En las secciones siguientes se proporcionan instrucciones acerca de cómo configurar un entorno que tiene varios bosques en un modelo de bosque de usuario o recurso para proporcionar funcionalidad empresarial en un escenario híbrido de Skype.
ms.openlocfilehash: ca3cd4bfe324690c41fbd045af967e57cab5fe36
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531555"
---
# <a name="configure-a-multi-forest-environment-for-hybrid-skype-for-business"></a>Configurar un entorno de varios bosque para entornos híbridos Skype para la empresa
 
En las secciones siguientes se proporcionan instrucciones acerca de cómo configurar un entorno que tiene varios bosques en un modelo de bosque de usuario o recurso para proporcionar funcionalidad empresarial en un escenario híbrido de Skype. 
  
![Entorno de varios bosques para Hybrid](../../media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="validate-the-forest-topology"></a>Validar la topología de bosque

Se admiten varios bosques de usuarios. Tenga en cuenta lo siguiente:   
  
- Para un bosque único usuario o en la implementación de bosque de varios usuarios, debe haber una implementación única de Skype para Business Server.
    
- Las versiones compatibles de Lync Server y Skype para Business Server en una configuración híbrida, vea [requisitos de topología](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md#BKMK_Topology) en la [planeación de la conectividad híbrida entre Skype para Business Server y Skype para profesionales en línea](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).
    
- Exchange Server se pueden implementar en uno o más bosques, que pueden o no incluir el bosque que contiene Skype para Business Server. Asegúrese de que ha aplicado la actualización acumulativa más reciente.
    
- Para obtener información detallada sobre la coexistencia con Exchange Server, incluidos los criterios y las limitaciones de la compatibilidad en distintas combinaciones de implementaciones locales y en línea, vea [Compatibilidad con la característica](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) en [Plan to integrate Skype for Business and Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
    
Para obtener más información, consulte [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).
  
## <a name="user-homing-considerations"></a>Consideraciones sobre el hospedaje de usuarios

Skype para los usuarios empresariales alojados en local puede tener Exchange hospedado en local o en línea. Skype para los usuarios en línea de negocio debe usar Exchange Online para obtener una experiencia óptima; Sin embargo, esto no es necesario. No se requiere Exchange local para implementar Skype para la empresa en cualquier caso.
  
## <a name="configure-forest-trusts"></a>Configurar confianzas de bosque

Las confianzas necesarias son confianzas transitivas bidireccionales entre el bosque de recursos y cada uno de los bosques de usuarios. Si tiene varios bosques de usuarios, para habilitar la autenticación entre bosques es importante que el enrutamiento de sufijo de nombre esté habilitado para cada una de estas confianzas de bosque. Para ver las instrucciones, consulte [Administrar confianzas de bosque](https://technet.microsoft.com/en-us/library/cc772440.aspx). 
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>Sincronizar las cuentas en el bosque de Skype para la empresa de hospedaje

Cuando Skype para Business Server se implementa en uno de los bosques (un bosque de recursos), pero proporciona funcionalidad a los usuarios de uno o varios otros bosques (bosques de cuentas), los usuarios de los otros bosques deben estar representados como objetos de usuario deshabilitadas en el bosque donde Skype para Business Server se ha implementado. Un producto de administración de identidad, como Microsoft Identity Manager, debe estar implementado y configurado para aprovisionar y sincronización de los usuarios de los bosques de cuenta en el bosque donde se implementa Skype para Business Server. Los usuarios deben sincronizarse en el bosque de hospedaje Skype para Business Server como objetos de usuario deshabilitados. No se puede sincronizar usuarios como objetos de contacto de Active Directory, ya que Azure Active Directory Connect no correctamente sincronizará contactos en Azure AD para su uso con Skype.
  
Con independencia de cualquier configuración con varios bosque, del bosque que aloja Skype para Business Server también puede proporcionar funcionalidad para los usuarios habilitados que existen en el mismo bosque.
  
Para obtener una sincronización de identidades adecuada, deben sincronizarse los siguientes atributos: 
  
|**Bosques de usuarios**|**Bosques de recursos**|
|:-----|:-----|
|atributo de vínculo de cuenta elegida  <br/> |atributo de vínculo de cuenta elegida  <br/> |
|mail   <br/> |mail   <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
El [atributo de vínculo de cuenta elegida](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-design-concepts/) se usará como el delimitador de origen. Si tiene un atributo distinto e inmutable que prefiere usar, puede hacerlo, pero asegúrese de editar la regla de notificaciones de AD FS y seleccionar el atributo durante la configuración de AAD Connect.
  
No sincronizar el UPN entre los bosques. Durante las pruebas, detectamos que era necesario un UPN único para cada bosque de usuarios, ya que no se puede usar el mismo UPN en varios bosques. Como resultado, se nos presentaron dos posibilidades: sincronizar el UPN o no sincronizarlo. 
  
- Si el UPN único de cada bosque de usuarios no se sincroniza con el objeto deshabilitado asociado en el bosque de recursos, el inicio de sesión único no podría usarse, como mínimo, durante el intento de inicio de sesión inicial (siempre que el usuario seleccione la opción para guardar la contraseña). En el cliente de Skype Empresarial, se da por supuesto que los valores de SIP/UPN son los mismos. Como la dirección SIP en este escenario es usuario@empresa.com, pero el UPN del objeto habilitado en el bosque de usuarios es en realidad usuario@contoso.empresa.com, el intento de inicio de sesión inicial produciría errores y al usuario se le solicitarían las credenciales. Después de especificar el UPN correcto/real, la solicitud de autenticación se completaría en los controladores de dominio del bosque de usuarios y el inicio de sesión se realizaría correctamente.
    
- Si el UPN único de cada bosque de usuarios se sincroniza con el objeto deshabilitado asociado en el bosque de recursos, la autenticación de AD FS produciría errores. La regla de coincidencia encontraría el UPN en el objeto del bosque de recursos, que estaba deshabilitado y no se pudo usar para la autenticación. 
    
## <a name="create-an-office-365-tenant"></a>Crear un inquilino de Office 365

A continuación, deberá facilitar un inquilino de Office 365 que vaya a usar con la implementación. Para obtener más información, vea [Pasos de aprovisionamiento para Office 365](https://social.technet.microsoft.com/wiki/contents/articles/22808.office-365-provisioning-steps.aspx). 
  
## <a name="configure-ad-fs"></a>Configurar AD FS

Una vez tenga un inquilino, deberá configurar los Servicios de federación de Active Directory (AD FS) en cada uno de los bosques de usuarios. Se presupone que tiene un SIP, una dirección SMTP y un nombre principal de usuario (UPN) únicos para cada bosque. AD FS es opcional y aquí se usa para obtener un inicio de sesión único. También se admite Dirsync con la sincronización de contraseñas, y también se puede usar en lugar de AD FS. 
  
Solo se probaron implementaciones con SIP/SMTP y UPN coincidentes. No tener SIP/SMTP/UPN que coincidan puede tener como resultado una funcionalidad reducida, como por ejemplo, problemas con la integración de Exchange y el inicio de sesión único. 
  
A menos que utilice un SIP, SMTP/UPN único para los usuarios de cada bosque, aún puede ejecutar en el inicio de sesión único (SSO) problemas - independientemente de donde se implementa AD FS: 
  
- En confianzas unidireccionales o bidireccionales entre bosques de usuarios/recursos con una granja de AD FS implementada en cada bosque de usuarios, todos los usuarios comparten un mismo dominio SIP/SMTP, pero un único UPN para cada bosque de usuarios. 
    
- En confianzas bidireccionales entre bosques de usuarios con una granja de AD FS implementada únicamente en bosque de recursos, todos los usuarios comparten un mismo dominio SIP/SMTP, pero un único UPN para cada bosque de usuarios. 
    
Al colocar una granja de AD FS en cada bosque de usuarios y un SIP/SMTP/UPN único para cada bosque, se solucionan dos problemas. Durante los intentos de autenticación, solo se buscarían e identificarían las cuentas del bosque de usuarios específico. Esto ayudará a proporcionar un proceso de autenticación sin errores. 
  
Esta será una implementación estándar de AD FS de Windows Server 2012 R2 y debería estar funcionando antes de continuar. Para ver las instrucciones, consulte [Cómo instalar AD FS 2012 R2 para Office 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx). 
  
Una vez que se haya implementado, se tiene que editar la regla de notificaciones para que coincida con la regla de delimitador de origen que haya escogido antes. En la MMC de AD FS, en Confianzas para Usuarios autenticados, haga clic con el botón secundario en Plataforma de identidad de Microsoft Office 365 y, a continuación, haga clic en Editar reglas de notificaciones. Edite la primera regla y cambie ObjectSID por employeeNumber. 
  
![Pantalla Editar reglas de varios bosques](../../media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>Configurar AAD Connect

AAD Connect se usará para combinar las cuentas entre los diferentes bosques y entre los bosques y Office 365. Debe implementar AAD Connect en el bosque de recursos. Es necesario para poder sincronizar varios bosques y Office 365, lo cual no es compatible con Dirsync. 
  
AAD Connect no sincroniza las cuentas entre bosques locales. Usa conectores de AD para leer objetos que ya están sincronizados entre bosques locales (por FIM o productos similares). A continuación, aprovecha las reglas de filtrado para crear una representación única que coincida al mismo tiempo con el objeto habilitado y deshabilitado en su metaverso y, a continuación, replica ese único objeto combinado en Office 365. 
  
Cuando haya terminado y AAD Connect se esté combinando, si observa un objeto en el metaverso, debería ver algo parecido a esto: 
  
![Pantalla del objeto en el metaverso de varios bosques](../../media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
Los atributos resaltados en verde se han combinado de los atributos de Office 365, los amarillos son del bosque de usuarios y los azules son del bosque de recursos. 
  
Este es un usuario de prueba, y puede ver que AAD Connect identificó los sourceAnchor y cloudSourceAnchor del usuario y los objetos del bosque de recursos, y de Office 365, en nuestro caso, 1101 que es el employeeNumber seleccionado antes. Después, fue capaz de combinar este objeto en lo que se ve arriba. 
  
Para más información, vea [Integración de las identidades locales con Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/). 
  
AAD Connect debe instalarse usando mayoritariamente los valores predeterminados. Excepto para los siguientes pasos: 
  
1.  Único inicio de sesión - con AD FS ya ha implementado y trabajo, no seleccione Configurar
    
2. Conectar los directorios, agregue todos los dominios 
    
3.  Identificar a los usuarios en los directorios locales: seleccione **las identidades de usuario existen en varios directorios** y seleccione atributos **ObjectSID** y **msExchangeMasterAccountSID**
    
4. Identificar a los usuarios en Azure AD: origen de anclaje - seleccione el atributo que se ha elegido después de leer la [selección de un atributo de buena sourceAnchor](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-design-concepts/), nombre Principal de usuario - **userPrincipalName**
    
5.  Las características opcionales - seleccione si tienen híbrida de Exchange implementado o no.
    
    > [!NOTE]
    >  Si solo tiene Exchange Online, es posible que haya un problema con errores de OAuth durante la detección automática debido a la redirección de CNAME. Para corregir este problema, debe establecer la dirección URL de detección automática de Exchange ejecutando el cmdlet siguiente desde el Skype para Shell de administración de servidor empresarial:
  
    Set-CsOAuthConfiguration - ExchangeAutoDiscoverURLhttps://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    
6.  Granja de AD FS: seleccione **Usar una granja de AD FS existente de Windows Server 2012 R2** y escriba el nombre del servidor de AD FS.
    
7.  Finalice el asistente y realice las validaciones necesarias.
    
## <a name="configure-hybrid-mode-for-skype-for-business-server"></a>Configurar el modo híbrido de Skype Empresarial Server

Siga los procedimientos recomendados para la configuración de Skype para entornos híbridos de negocio. Para obtener más información, vea [Planear la implementación híbrida para Skype Empresarial Server 2015](https://technet.microsoft.com/en-us/library/jj205403.aspx) y, para la información de configuración, vea [Realizar una configuración híbrida para Skype Empresarial Online](https://technet.microsoft.com/en-us/library/jj204669.aspx). 
  
## <a name="configure-hybrid-mode-for-exchange-server"></a>Configurar el modo híbrido de Exchange Server

Si es necesario, siga los procedimientos recomendados para realizar la configuración híbrida de Exchange. Para obtener más información, vea [Implementaciones híbridas de Exchange Server](https://technet.microsoft.com/en-us/library/jj200581%28v=exchg.150%29.aspx). 
  

