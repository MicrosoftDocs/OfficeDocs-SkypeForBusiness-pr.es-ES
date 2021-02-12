---
title: Modelos de identidad y autenticación para Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 09/25/2020
ms.topic: reference
ms.service: msteams
ms.reviewer: anwara
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Obtenga información sobre los diferentes modelos de identidad para Microsoft Teams, como solo en la nube y la implementación híbrida. Obtenga también información sobre la autenticación multifactor.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 40a06ce75c3ae7a4f85eb1c93064ba3d80c13fc0
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277120"
---
# <a name="identity-models-and-authentication-for-microsoft-teams"></a>Modelos de identidad y autenticación para Microsoft Teams

Microsoft Teams es compatible con todos los modelos de identidad disponibles en Microsoft 365 y Office 365, entre los que se incluyen:

- **Solo en la** nube: las cuentas de usuario se crean y administran en Microsoft 365 u Office 365 y se almacenan en Azure Active Directory (Azure AD). Las credenciales de inicio de sesión de usuario (nombre de cuenta y contraseña) están validadas por Azure AD.

- **Híbrido:** las cuentas de usuario normalmente se administran en un bosque de Servicios de dominio de Active Directory (AD DS) local. Según la configuración, la validación de credenciales la puede realizar Azure AD, AD DS o un proveedor de identidades federadas. Este modelo usa la sincronización de directorios de AD DS a Azure AD con Azure AD Connect.

Para obtener más información, vea los modelos de [identidad de Microsoft 365 y Azure AD.](https://docs.microsoft.com/microsoft-365/enterprise/about-microsoft-365-identity)

## <a name="configurations"></a>Configuraciones

Según las decisiones de su organización sobre qué modelo de identidad y configuración usa, los pasos de implementación pueden variar.

Si aún no ha implementado Microsoft 365 u Office 365 y un modelo de identidad, use esta tabla. 

|Modelo de identidad |Lista de comprobación de la implementación  |Información adicional  |
|---------|---------|---------|
|Todo     |<ol type="1"><li>Compare las opciones de planes de Microsoft 365 y Office 365 y obtenga una suscripción y un inquilino.</li><li>Cree una organización de Microsoft 365 u Office 365 para su espacio empresarial.</li><li>Comprar licencias de Microsoft 365 u Office 365 para el espacio empresarial</li><li>Configurar dominios y cuentas de usuario de administrador.</li></ol>  |<ul><li>[Opciones de planes de Office 365](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[Comparar planes de Microsoft 365 para empresas](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[Comprar o quitar licencias de suscripción](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[Agregar licencias a una suscripción](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[Configurar Microsoft 365 para empresas](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[Agregar un dominio con el asistente para la configuración](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li></ul><br>[Microsoft FastTrack está](https://www.microsoft.com/fasttrack/microsoft-365) disponible para ayudarte.  |
|Identidad de nube     |<ul><li>Crear cuentas de usuario con el Centro de administración de Microsoft 365</li></ul> |<ul style="list-style-type:none"><li>[Agregar usuarios y asignar licencias](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul> |
|Identidad híbrida     |<ol type="1"><li>Instale Azure AD Connect.</li><li>Configurar la sincronización de directorios.</li><li>Administrar usuarios y grupos con herramientas de AD DS.</li></ol> |<ul style="list-style-type:none"><li>[Configurar la sincronización de directorios](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
|Identidad híbrida con autenticación federada    |<ol type="1"><li>Instale y configure un proveedor de identidades federadas como AD FS.</li><li>Instale Azure AD Connect y configure la sincronización de directorios y la autenticación federada.</li><li>Administrar usuarios y grupos con herramientas de AD DS.</li></ol> |<ul><li>[Planificar su implementación de AD FS](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[Lista de comprobación: Implementar la granja de servidores de federación](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[Configurar el acceso a la extranet para AD FS](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[Configurar una confianza entre AD FS y Azure AD](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[Verificar y administrar el inicio de sesión único con ADFS](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[Configurar la sincronización de directorios](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
||||

## <a name="multi-factor-authentication"></a>Autenticación multifactor

Las contraseñas son el método más común de autenticación para iniciar sesión en un equipo o servicio en línea, pero también son las más vulnerables. Los usuarios pueden elegir contraseñas fáciles y usar las mismas contraseñas para varios inicios de sesión en diferentes equipos y servicios. 

Para proporcionar un nivel adicional de seguridad para los inicios de sesión, use la autenticación multifactor (MFA), que requiere una contraseña y un método de comprobación adicional como:

- Un mensaje de texto enviado a un teléfono que requiere que el usuario escriba un código de verificación.
- Una llamada telefónica.
- La aplicación de teléfonos inteligentes Microsoft Authenticator.
- Otros métodos disponibles con identidad híbrida y autenticación federada.

Mfa es compatible con cualquier plan de Microsoft 365 u Office 365 que incluya Microsoft Teams. Se recomienda encarecidamente que como mínimo requiera MFA para las cuentas que tienen asignados roles de [administrador,](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)como el administrador de servicios de Teams.

También debe realizar la MFA a los usuarios. Una vez que los usuarios se han inscrito en la MFA, la próxima vez que inicien sesión, verán un mensaje en el que se les pedirá que configuren su método de comprobación adicional. 

Para obtener más información, [vea Autenticación multifactor para Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)
