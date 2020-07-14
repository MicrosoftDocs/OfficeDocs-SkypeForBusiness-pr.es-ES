---
title: Modelos de identidad y autenticación
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 09/25/2017
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
description: Learn about the different identity models in Microsoft Teams such as Cloud, Synchronized, and Federated. Also learn about multi-factor authentication.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 330a197f2e042ee8d87e294f9ff822c6bf6d5ac6
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121570"
---
<a name="identity-models-and-authentication-in-microsoft-teams"></a>Modelos de identidad y autenticación en Microsoft Teams
==========================================

Microsoft Teams supports all the identity models that are available with Microsoft 365 and Office 365. Supported identity models include:

-   **Identidad de nube**: en este modelo, un usuario se crea y administra en Microsoft 365 u Office 365, y se almacena en Azure Active Directory, y la contraseña es comprobada por Azure Active Directory.

-   **Synchronized Identity**: In this model, the user identity is managed in an on-premises server, and the accounts and password hashes are synchronized to the cloud. The user enters the same password on-premises as they do in the cloud, and at sign-in the password is verified by Azure Active Directory. This model uses the Microsoft Azure Active Directory Connect Tool.

-   **Federated Identity**: This model requires a synchronized identity with the user password is verified by the on-premises identity provider. With this model, the password hash does not need to be synchronized to Azure AD, and Active Directory Federation Services (ADFS) or a third-party identity provider is used to authenticate users against the on-premises Active Directory.

<a name="configurations"></a>Configuraciones
--------------

Depending on your organization's decisions of which identity model to implement and use, the implementation requirements may vary. Refer to the requirements table below to ensure that your deployment meets these prerequisites. If you have already deployed Microsoft 365 or Office 365 and have already implemented the identity and authentication method, you may skip these steps.


|Modelo de identidad |Lista de comprobación de la implementación  |Información adicional  |
|---------|---------|---------|
|Todo     |<ol type="1"><li>Comparar las opciones de plan de Microsoft 365 y Office 365 y obtener una suscripción</li><li>Crear una organización de Microsoft 365 u Office 365</li><li>Asignar licencias de Microsoft 365 u Office 365 al inquilino</li><li>Configurar dominios y usuarios administradores</li><li>Continuar con las instrucciones específicas para el modelo de identidad</li></ol>          |<ul style="list-style-type:none"><li>[Opciones del plan de Microsoft 365 y Office 365](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[Comparar los planes de aplicaciones de Microsoft 365 para empresas](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[Administrar licencias de suscripción](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[Agregar licencias a una suscripción](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[Configurar Microsoft 365 para empresas](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[Agregar usuarios y dominios con el asistente para configuración](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li><li>Nota: Si necesita ayuda, [Microsoft FastTrack](https://go.microsoft.com/fwlink/?linkid=854618) está disponible para ayudar.</li></ul>          |
|Identidad de nube     |<ol type="1"><li>Crear usuarios mediante el centro de administración de Microsoft 365</li></ol>           |<ul style="list-style-type:none"><li>[Agregar usuarios de forma individual o en bloque](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul>         |
|Identidad sincronizada     |<ol type="1"><li>Instalar Azure AD Connect</li><li>Configurar la sincronización del directorio</li><li>Crear usuarios utilizando las herramientas de administración locales de Active Directory</li></ol>         |<ul style="list-style-type:none"><li>[Configurar la sincronización de directorios](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>Nota: los hash de contraseña deben estar sincronizados para Microsoft 365 y Office 365 para realizar la autenticación.</li></ul>         |
|Identidad federada    |<ol type="1"><li>Instalar Azure AD Connect</li><li>Configurar la sincronización del directorio</li><li>Instalar y configurar un proveedor de identidades federadas (se recomienda ADFS)</li><li>Crear usuarios utilizando las herramientas de administración locales de Active Directory</li></ol>           |<ul style="list-style-type:none"><li>[Configurar la sincronización de directorios](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>[Planificar su implementación de AD FS](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[Lista de comprobación: Implementar la granja de servidores de federación](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[Configurar el acceso a la extranet para AD FS](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[Configurar una confianza entre AD FS y Azure AD](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[Verificar y administrar el inicio de sesión único con ADFS](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[Lista de compatibilidad de federación de Azure AD](https://go.microsoft.com/fwlink/?linkid=854625)</li><li>Nota: Los valores hash de contraseña no necesitan sincronizarse con Azure Active Directory.</li></ul>         |

Consulte [elegir un modelo de inicio de sesión](https://go.microsoft.com/fwlink/?linkid=854626) y [comprender los modelos de identidad y las guías de Azure Active Directory](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9) para obtener más información.


<a name="multi-factor-authentication"></a>Autenticación multifactor
----------------------------

Microsoft 365 and Office 365 plans support Multi-Factor Authentication (MFA) that increases the security of user logins to services. With MFA, users are required to acknowledge a phone call, text message, or an app notification on their smartphone after correctly entering their password. Only after this second authentication factor has been satisfied, can a user sign in.

Multi Factor authentication is supported with any Microsoft 365 or Office 365 plan that includes Microsoft Teams. The subscription plans that include Microsoft Teams are discussed later in the Licensing section below.

Once the users are enrolled for MFA, the next time a user signs in, they will see a message that asks them to set up their second authentication factor. Supported authentication methods are:


|Tipo de inquilino  |Opciones disponibles de segundo factor de MFA  |Notas  |
|---------|---------|---------|
|**Solo nube**     |MFA para Microsoft 365 u Office 365 <ul><li>Llamada telefónica</li><li>Mensaje de texto</li><li>Notificación en la aplicación móvil</li><li>Código de verificación de la aplicación móvil</li></ul>        | |
|**Configuración híbrida (modelo de identidad sincronizada o federada)**     |<ul><li>MFA para Microsoft 365 u Office 365</li><li>Módulo de Azure MFA (integrado con ADFS)</li><li>Tarjeta inteligente física o virtual (integrada con ADFS)</li></ul>         |Nota: hay soluciones MFA adicionales disponibles con [documentos de compatibilidad del proveedor de identidades de Azure ad](https://www.microsoft.com/download/details.aspx?id=56843)         |
