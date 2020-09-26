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
description: Obtenga más información sobre los diferentes modelos de identidad de Microsoft Teams, como Cloud-only y híbrido. Además, Obtén más información sobre la autenticación multifactor.
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

Microsoft Teams es compatible con todos los modelos de identidad disponibles con Microsoft 365 y Office 365, que incluyen:

- **Solo en la nube**: las cuentas de usuario se crean y administran en Microsoft 365 u Office 365 y se almacenan en Azure Active Directory (Azure ad). Azure AD valida las credenciales de inicio de sesión del usuario (nombre de cuenta y contraseña).

- **Híbrido**: las cuentas de usuario normalmente se administran en un bosque local de servicios de dominio de Active Directory (AD DS). Según la configuración, Azure AD, AD DS o un proveedor de identidad federada puede realizar la validación de las credenciales. Este modelo usa la sincronización de directorios de AD DS a Azure AD con Azure AD Connect.

Para obtener más información, consulte [modelos de identidad de Microsoft 365 y Azure ad](https://docs.microsoft.com/microsoft-365/enterprise/about-microsoft-365-identity).

## <a name="configurations"></a>Configuraciones

En función de las decisiones de la organización sobre el modelo de identidad y la configuración que use, los pasos de implementación pueden variar.

Si aún no ha implementado Microsoft 365 u Office 365 y un modelo de identidad, use esta tabla. 

|Modelo de identidad |Lista de comprobación de la implementación  |Información adicional  |
|---------|---------|---------|
|Todo     |<ol type="1"><li>Compare las opciones de plan de Microsoft 365 y Office 365 y obtenga una suscripción y un inquilino.</li><li>Cree una organización de Microsoft 365 u Office 365 para su inquilino.</li><li>Comprar licencias de Microsoft 365 o de Office 365 para el inquilino</li><li>Configurar dominios y cuentas de usuario de administrador.</li></ol>  |<ul><li>[Opciones del plan 365 de Office](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[Comparar los planes de 365 para empresas de Microsoft](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[Comprar o quitar licencias de suscripción](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[Agregar licencias a una suscripción](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[Configurar Microsoft 365 para empresas](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[Agregar un dominio con el Asistente de configuración](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li></ul><br>[Microsoft FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) está disponible para ayudarle.  |
|Identidad de nube     |<ul><li>Crear cuentas de usuario con el centro de administración de Microsoft 365</li></ul> |<ul style="list-style-type:none"><li>[Agregar usuarios y asignar licencias](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul> |
|Identidad híbrida     |<ol type="1"><li>Instale Azure AD Connect.</li><li>Configurar la sincronización de directorios.</li><li>Administre usuarios y grupos con las herramientas de AD DS.</li></ol> |<ul style="list-style-type:none"><li>[Configurar la sincronización de directorios](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
|Identidad híbrida con autenticación federada    |<ol type="1"><li>Instalar y configurar un proveedor de identidad federado, como AD FS.</li><li>Instale Azure AD Connect y configure la sincronización de directorios y la autenticación federada.</li><li>Administre usuarios y grupos con las herramientas de AD DS.</li></ol> |<ul><li>[Planificar su implementación de AD FS](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[Lista de comprobación: Implementar la granja de servidores de federación](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[Configurar el acceso a la extranet para AD FS](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[Configurar una confianza entre AD FS y Azure AD](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[Verificar y administrar el inicio de sesión único con ADFS](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[Configurar la sincronización de directorios](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
||||

## <a name="multi-factor-authentication"></a>Autenticación multifactor

Las contraseñas son el método de autenticación más común para iniciar sesión en un equipo o servicio en línea, pero también son los más vulnerables. Los usuarios pueden elegir contraseñas fáciles y usar las mismas contraseñas para varios inicios de sesión en diferentes equipos y servicios. 

Para proporcionar un nivel adicional de seguridad para los inicios de sesión, use la autenticación multifactor (MFA), que requiere una contraseña y un método de verificación adicional, como por ejemplo:

- Mensaje de texto enviado a un teléfono que requiere que el usuario escriba un código de comprobación.
- Una llamada de teléfono.
- La aplicación de Microsoft Authenticator Smart Phone.
- Otros métodos disponibles con la autenticación híbrida y la autenticación federada.

MFA es compatible con cualquier plan de Microsoft 365 u Office 365 que incluya Microsoft Teams. Se recomienda encarecidamente que, al menos, solicite MFA para las cuentas que tienen [asignados roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide), como el administrador de servicios de equipo.

También debe implementar MFA a los usuarios. Una vez que los usuarios se hayan inscrito para MFA, la próxima vez que inicien sesión, verán un mensaje en el que se les pedirá que configuren su método de verificación adicional. 

Para obtener más información, consulte [autenticación multifactor para Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365).
