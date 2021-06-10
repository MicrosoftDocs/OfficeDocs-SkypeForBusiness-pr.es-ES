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
description: Obtenga información sobre los diferentes modelos de identidad para Microsoft Teams, como la nube y la híbrida. Obtenga más información sobre la autenticación multifactor.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: dff34a6a56294c8c62295e143f753777875bfbda
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112366"
---
# <a name="identity-models-and-authentication-for-microsoft-teams"></a>Modelos de identidad y autenticación para Microsoft Teams

Microsoft Teams admite todos los modelos de identidad que están disponibles con Microsoft 365 y Office 365, que incluyen:

- **Solo en la** nube: las cuentas de usuario se crean y administran en Microsoft 365 o Office 365 y se almacenan en Azure Active Directory (Azure AD). Azure AD valida las credenciales de inicio de sesión de usuario (nombre de cuenta y contraseña).

- **Híbrido:** las cuentas de usuario normalmente se administran en un bosque de Servicios de dominio de Active Directory (AD DS) local. Según la configuración, azure AD, AD DS o un proveedor de identidades federados pueden realizar la validación de credenciales. Este modelo usa la sincronización de directorios de AD DS a Azure AD con Azure AD Conectar.

Para obtener más información, [vea Microsoft 365 de identidad y Azure AD.](/microsoft-365/enterprise/about-microsoft-365-identity)

## <a name="configurations"></a>Configuraciones

Según las decisiones de su organización sobre qué modelo de identidad y configuración usa, los pasos de implementación pueden variar.

Si aún no ha implementado Microsoft 365 o Office 365 y un modelo de identidad, use esta tabla. 

|Modelo de identidad |Lista de comprobación de la implementación  |Información adicional  |
|---------|---------|---------|
|Todo     |<ol type="1"><li>Compare Microsoft 365 y Office 365 plan y obtenga una suscripción y un inquilino.</li><li>Cree una Microsoft 365 o Office 365 para su inquilino.</li><li>Comprar Microsoft 365 o Office 365 licencias para el inquilino</li><li>Configurar dominios y cuentas de usuario de administrador.</li></ol>  |<ul><li>[Office 365 de plan](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)</li><li>[Comparar Microsoft 365 planes para empresas](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[Comprar o quitar licencias de suscripción](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[Agregar licencias a una suscripción](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[Configurar Microsoft 365 para empresas](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[Agregar un dominio con el asistente de configuración](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li></ul><br>[Microsoft FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) está disponible para ayudarle.  |
|Identidad de la nube     |<ul><li>Crear cuentas de usuario con el Microsoft 365 de administración</li></ul> |<ul style="list-style-type:none"><li>[Agregar usuarios y asignar licencias](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul> |
|Identidad híbrida     |<ol type="1"><li>Instale Azure AD Conectar.</li><li>Configurar la sincronización de directorios.</li><li>Administre usuarios y grupos con herramientas de AD DS.</li></ol> |<ul style="list-style-type:none"><li>[Configurar la sincronización de directorios](/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
|Identidad híbrida con autenticación federada    |<ol type="1"><li>Instale y configure un proveedor de identidades federado como AD FS.</li><li>Instale Azure AD Conectar y configure la sincronización de directorios y la autenticación federada.</li><li>Administre usuarios y grupos con herramientas de AD DS.</li></ol> |<ul><li>[Planificar su implementación de AD FS](/previous-versions/azure/azure-services/dn151324(v=azure.100))</li><li>[Lista de comprobación: Implementar la granja de servidores de federación](/previous-versions/azure/azure-services/dn528856(v=azure.100))</li><li>[Configurar el acceso a la extranet para AD FS](/previous-versions/azure/azure-services/dn528859(v=azure.100))</li><li>[Configurar una confianza entre AD FS y Azure AD](/previous-versions/azure/azure-services/jj205461(v=azure.100))</li><li>[Verificar y administrar el inicio de sesión único con ADFS](/previous-versions/azure/azure-services/jj151809(v=azure.100))</li><li>[Configurar la sincronización de directorios](/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
||||

## <a name="multi-factor-authentication"></a>Autenticación multifactor

Las contraseñas son el método de autenticación más común para iniciar sesión en un equipo o servicio en línea, pero también son las más vulnerables. Los usuarios pueden elegir contraseñas fáciles y usar las mismas contraseñas para varios inicios de sesión en diferentes equipos y servicios. 

Para proporcionar un nivel adicional de seguridad para los inicios de sesión, use la autenticación multifactor (MFA), que requiere una contraseña y un método de verificación adicional como:

- Un mensaje de texto enviado a un teléfono que requiere que el usuario escriba un código de verificación.
- Una llamada de teléfono.
- La Microsoft Authenticator de teléfonos inteligentes.
- Otros métodos disponibles con identidad híbrida y autenticación federada.

MFA es compatible con cualquier plan Microsoft 365 o Office 365 que incluya Microsoft Teams. Es muy recomendable que, como mínimo, necesite MFA para esas cuentas a las que se les asignen roles de [administrador,](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)como Teams de servicio.

También debe agregar MFA a los usuarios. Una vez que los usuarios se inscriban en MFA, la próxima vez que inicien sesión, verán un mensaje en el que se les pedirá que configuren su método de verificación adicional. 

Para obtener más información, vea [Autenticación multifactor para Microsoft 365](/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365).