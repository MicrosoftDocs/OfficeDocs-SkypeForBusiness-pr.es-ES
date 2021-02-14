---
title: Autenticación en salas de Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo configurar la autenticación moderna para salas de Microsoft Teams
ms.openlocfilehash: 41a65743e5da851dd8e0197e9382deaf696cd9ec
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662585"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Autenticación en salas de Microsoft Teams

La administración de cuentas de los dispositivos de Salas de Microsoft Teams se controla en el nivel de la aplicación. La aplicación se conecta a Microsoft Teams, Skype Empresarial y Exchange para obtener recursos para la cuenta de la sala para habilitar las experiencias de llamada y reunión. El dispositivo se mantiene por cuenta agnóstica para permitir las funcionalidades siempre disponibles, escenarios de llamadas (para dispositivos configurados con un plan de llamadas) y mecanismos de bloqueo personalizados implementados en estos dispositivos. Esto significa que la autenticación para estos dispositivos se hace de una manera diferente a la de los dispositivos de usuario final.  

Se recomienda usar autenticación moderna para todos los clientes que usen dispositivos de Salas de Microsoft Teams con Microsoft 365 u Office 365. Si tiene una implementación local de Exchange Server o [](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview) Skype Empresarial Server, configure la autenticación moderna híbrida con Azure Active Directory (Azure AD) para habilitar el uso de la autenticación moderna.

La autenticación moderna es compatible con la versión 4.4.25.0 y posteriores de Microsoft Teams Rooms.

## <a name="modern-authentication"></a>Autenticación moderna

Cuando utiliza la autenticación moderna con la aplicación Salas de Microsoft Teams, la Biblioteca de autenticación de Active Directory (ADAL) se usa para conectarse a Microsoft Teams, Exchange y Skype Empresarial. Un dispositivo de Microsoft Teams Rooms es un dispositivo compartido y realiza un reinicio nocturno para garantizar un funcionamiento correcto y obtener actualizaciones críticas del sistema operativo, el controlador, el firmware o la aplicación. El mecanismo de [](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth-ropc) autenticación moderna usa el tipo de autorización de autorización de credenciales de contraseña del propietario del recurso en OAuth 2.0, lo que no requiere intervención del usuario. Esta es una de las diferencias clave entre el funcionamiento de la autenticación moderna para las cuentas de usuario y las cuentas de recursos que se usan en la aplicación Salas de Microsoft Teams. Por este problema, las cuentas de recursos de salas de Microsoft Teams no deben configurarse para usar autenticación multifactor (MFA), autenticación de tarjeta inteligente o autenticación basada en certificados de cliente (que están disponibles para los usuarios finales).

La otra diferencia clave entre el funcionamiento de la autenticación moderna en los dispositivos de Salas de Microsoft Teams y los dispositivos de usuario final es que no puede usar una cuenta de recursos para aplicar directivas de acceso condicional a nivel de dispositivo en Azure Active Directory y Endpoint Manager ya que no se pasa la información del dispositivo al usar este tipo de concesión. En su lugar, puede inscribir un dispositivo en Microsoft Endpoint Manager y aplicar directivas de cumplimiento mediante las instrucciones que se proporcionan en La administración de salas de reuniones de [Teams con Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>Habilitar la autenticación moderna en un dispositivo de Salas de Microsoft Teams

Para que los salas de Microsoft Teams usen la autenticación moderna con Skype Empresarial y Exchange, habilite la configuración del lado cliente para la autenticación moderna en el dispositivo de Salas de Microsoft Teams. Puede hacerlo en la configuración del dispositivo o en el archivo de configuración XML.

> [!NOTE]
> Antes de habilitar la configuración del lado cliente para la autenticación moderna, asegúrese de que su entorno está configurado correctamente para usar la autenticación moderna.

### <a name="using-device-settings"></a>Usar la configuración del dispositivo

1. En el dispositivo de Salas de equipo de Microsoft, vaya a **Más** (**...**).
    
2. Seleccione **Configuración y,** a continuación, escriba el nombre de usuario y la contraseña del administrador del dispositivo.
3. Vaya a la **pestaña Cuenta,** active **la** autenticación moderna y, a continuación, seleccione Guardar y **salir.**

### <a name="using-the-xml-config-file"></a>Usar el archivo de configuración XML

En el SkypeSettings.xml actual, establezca el elemento XML de autenticación moderna en **True,** tal y como se muestra a continuación.

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

Para aplicar la configuración, consulte Administrar de forma remota una configuración de consola de salas de [Microsoft Teams con un archivo de configuración XML.](xml-config-file.md)

## <a name="prepare-your-environment-for-modern-authentication"></a>Preparar el entorno para la autenticación moderna

Antes de empezar, asegúrese de comprender los modelos de identidad que se usarán con Office 365 y Azure AD. Puede encontrar más información en los modelos de identidad de [Office 365](https://docs.microsoft.com/Office365/Enterprise/about-office-365-identity) y Azure Active Directory, así como en Identidad híbrida y sincronización de directorios para [Microsoft 365 u Office 365.](https://docs.microsoft.com/Office365/Enterprise/plan-for-directory-synchronization)

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Habilitar la autenticación moderna en Microsoft 365 u Office 365

Para activar la autenticación moderna para Exchange Online, vea [Habilitar la autenticación moderna en Exchange Online.](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) Si usa Skype Empresarial Online, también debe asegurarse de que está activada la autenticación moderna para Skype Empresarial Online. Para obtener más información, [consulte Skype Empresarial Online: Habilite su inquilino para la autenticación moderna.](https://aka.ms/SkypeModernAuth)

Le recomendamos que no quite las directivas de autenticación básicas para Exchange Online o deshabilite la autenticación básica para su inquilino hasta que haya validado que los dispositivos de salas de Microsoft Teams pueden iniciar sesión correctamente con Exchange Online, Teams y Skype Empresarial Online.

Para obtener más información sobre cómo deshabilitar la autenticación básica en Exchange Online, vea [Deshabilitar autenticación básica en Exchange Online.](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)

## <a name="hybrid-modern-authentication"></a>Autenticación moderna híbrida

Para garantizar que la autenticación al servidor de Exchange local o al servidor de Skype Empresarial sea correcta, debe asegurarse de que la cuenta de recursos que se usa con Salas de Microsoft Teams esté configurada para obtener autorización de Azure AD. 

Los flujos de autenticación de los salas de Teams varían según la configuración de autenticación. Para los clientes que usan un dominio administrado, salas de Teams usa credenciales de contraseña de propietario de recurso [de OAuth 2.0](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth-ropc) con Azure Active Directory. Sin embargo, para los clientes que usan un dominio federado, se usa el flujo de aserción del portador [de OAuth 2.0 SAML.](https://docs.microsoft.com/azure/active-directory/develop/v2-saml-bearer-assertion)

> [!NOTE]
> Es posible que su proveedor de identidades necesite configuraciones o configuraciones específicas para la integración con Azure Active Directory u Office 365. Póngase en contacto con su proveedor de identidades si necesita ayuda para configurar la autenticación con Salas de Teams.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Requisitos previos específicos de Salas de Microsoft Teams

Los requisitos previos para habilitar la autenticación moderna en la topología híbrida están cubiertos en la información general de la autenticación moderna híbrida y en los [requisitos previos](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview)para su uso con servidores locales de Skype Empresarial y Exchange. Son de aplicación todos los requisitos previos analizados en el artículo.

Sin embargo, como [](https://tools.ietf.org/html/rfc6749#section-1.3.3) Salas de Microsoft Teams usa autorización de credenciales de contraseña de propietario de recursos y las API de REST subyacentes para la autenticación moderna, las siguientes son diferencias importantes que hay que tener en cuenta que son específicas de Salas de Microsoft Teams.

- Debe tener la versión Exchange Server 2016 CU8 o posterior, o Exchange Server 2019 CU1 o posterior.
- Debe tener Skype Empresarial Server 2015 CU5 o posterior, o Skype Empresarial Server 2019 o posterior.
- La MFA no es compatible independientemente de la topología que tenga.
- Los salas de Microsoft Teams no admiten errores de coincidencia de SIP y UPN. Debe crear una cuenta de Salas de Microsoft Teams con los mismos UPN y SIP para que funcione.
- Si usa un proveedor de autenticación de terceros compatible con Azure AD, este debe admitir un flujo de autenticación activa a través de WS-Trust.
- No use directivas de acceso condicional a nivel de dispositivo para una cuenta de recursos configurada con la aplicación. Si lo hace, se provocarán errores en el inicio de sesión. En su lugar, inscriba un dispositivo en Microsoft Intune y aplique directivas de cumplimiento mediante las instrucciones publicadas en Administrar salas de reuniones de [Teams con Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)

### <a name="configure-exchange-server"></a>Configurar Exchange Server

Para habilitar la autenticación moderna híbrida Exchange Server, consulte Cómo configurar Exchange Server local para [usar la autenticación moderna híbrida.](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="configure-skype-for-business-server"></a>Configurar Skype Empresarial Server

Para habilitar la autenticación moderna híbrida con Skype Empresarial Server, consulte Cómo configurar Skype Empresarial local [para usar la autenticación moderna híbrida.](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Quitar o deshabilitar Skype Empresarial y Exchange

Si su configuración no permite la autenticación moderna híbrida o necesita quitar o deshabilitar la autenticación moderna híbrida para Exchange o Skype Empresarial, consulte Quitar o deshabilitar la autenticación moderna híbrida de Skype Empresarial y [Exchange.](https://docs.microsoft.com/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)

### <a name="azure-ad-conditional-access"></a>Acceso condicional de Azure AD

Puede configurar una cuenta de recursos usada con salas de Microsoft Teams para acceso basado en ubicación o IP. Para obtener más información, [vea Acceso condicional: Bloquear el acceso por ubicación.](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-location)

No se admiten otras directivas de acceso condicional. Para obtener más información sobre el cumplimiento de dispositivos, consulte [Administrar salas de reuniones de Teams con Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)  
