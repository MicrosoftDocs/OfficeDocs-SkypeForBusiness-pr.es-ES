---
title: Modelos de identidad y autenticación
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: reference
ms.service: msteams
ms.reviewer: anach
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Conozca los diferentes modelos de identidad de Microsoft Teams, como Nube, Sincronizada y Federada. Aprenda también sobre la autenticación multifactor.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a58dcdae704be7ccdaefe1e2bca3b4978f4a10f9
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139299"
---
<a name="identity-models-and-authentication-in-microsoft-teams"></a>Modelos de identidad y autenticación en Microsoft Teams
==========================================

Microsoft Teams admite todos los modelos de identidad que están disponibles con Office 365. Los modelos de identidad admitidos son los siguientes:

-   **Identidad de nube**: En este modelo, los usuarios se crean y administran en Office 365, y se almacenan en Azure Active Directory. Las contraseñas las verifica Azure Active Directory.

-   **Identidad sincronizada**: En este modelo, la identidad del usuario se administra en un servidor dentro de la empresa y las cuentas y los valores hash de contraseña se sincronizan con la nube. El usuario introduce la misma contraseña a nivel local que en la nube, y al momento de iniciar sesión, Azure Active Directory verifica la contraseña. Este modelo usa la herramienta Microsoft Azure Active Directory Connect.

-   **Identidad federada**: Este modelo requiere que una identidad sincronizada con la contraseña de usuario sea verificada por el proveedor de identidades local. Con este modelo, el valor hash de contraseña no necesita sincronizarse con Azure AD, y se utiliza Active Directory Federation Services (ADFS) o un proveedor de identidades de terceros para autenticar a los usuarios con el Active Directory local.

<a name="configurations"></a>Configuraciones
--------------

Según las decisiones de la organización sobre qué modelo de identidad implementar y usar, los requisitos de implementación pueden variar. Consulte la tabla requisitos siguiente para asegurarse de que su implementación cumpla con estos requisitos previos. Si ya ha implementado Office 365 y ya ha implementado el método de identidad y autenticación, puede omitir estos pasos.


|Modelo de identidad |Lista de comprobación de la implementación  |Información adicional  |
|---------|---------|---------|
|Todo     |<ol type="1"><li>Comparar las opciones de planes de Office 365 y obtener una suscripción</li><li>Crear un inquilino de Office 365</li><li>Asignar licencias de Office 365 al inquilino</li><li>Configurar dominios y usuarios administradores</li><li>Continuar con las instrucciones específicas para el modelo de identidad</li></ol>          |<ul style="list-style-type:none"><li>[Opciones de planas de Office 365](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[Comparar los planes de negocio de Office 365](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[Comprar licencias de Office 365 para suscripción empresarial](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[Agregar licencias a una suscripción](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[Configurar Office 365 para empresas](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[Agregar usuarios y dominios con el asistente para configuración](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li><li>Nota: Si necesita ayuda, [el equipo de Microsoft FastTrack para Office 365](https://go.microsoft.com/fwlink/?linkid=854618) está disponible para asistirle.</li></ul>          |
|Identidad de nube     |<ol type="1"><li>Crear usuarios utilizando el portal de administración de Office 365</li></ol>           |<ul style="list-style-type:none"><li>[Agregar usuarios en forma individual o en lote a Office 365](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul>         |
|Identidad sincronizada     |<ol type="1"><li>Instalar Azure AD Connect</li><li>Configurar la sincronización del directorio</li><li>Crear usuarios utilizando las herramientas de administración locales de Active Directory</li></ol>         |<ul style="list-style-type:none"><li>[Configurar la sincronización del directorio para Office 365](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>Nota: Se deben sincronizar los valores hash de contraseña para que Office 365 realice la autenticación.</li></ul>         |
|Identidad federada    |<ol type="1"><li>Instalar Azure AD Connect</li><li>Configurar la sincronización del directorio</li><li>Instalar y configurar un proveedor de identidades federadas (se recomienda ADFS)</li><li>Crear usuarios utilizando las herramientas de administración locales de Active Directory</li></ol>           |<ul style="list-style-type:none"><li>[Configurar la sincronización del directorio para Office 365](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>[Planificar su implementación de AD FS](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[Lista de comprobación: Implementar la granja de servidores de federación](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[Configurar el acceso a la extranet para AD FS](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[Configurar una confianza entre AD FS y Azure AD](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[Verificar y administrar el inicio de sesión único con ADFS](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[Lista de compatibilidad de federación de Azure AD](https://go.microsoft.com/fwlink/?linkid=854625)</li><li>Nota: Los valores hash de contraseña no necesitan sincronizarse con Azure Active Directory.</li></ul>         |

Consulte [Elegir un modelo de inicio de sesión para Office 365](https://go.microsoft.com/fwlink/?linkid=854626) y [Comprender la identidad en Office 365 y Azure Active Directory](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9) para obtener más información.

<a name="multi-factor-authentication"></a>Autenticación multifactor
----------------------------

Los planes de Office 365 admiten la autenticación multifactor (MFA) que aumenta la seguridad de los inicios de sesión de usuario en los servicios de Office 365. Con MFA para Office 365, los usuarios deben responder a una llamada de teléfono, un mensaje de texto o una notificación de aplicación en sus smartphones después de introducir correctamente la contraseña. Solo podrán iniciar sesión una vez que se haya cumplido este segundo factor de autenticación.

La autenticación multifactor es compatible con cualquier plan 365 de Office que incluya Microsoft Teams. Los planes de suscripción de Office 365 que incluyen Microsoft Teams se describen más adelante en la sección licencias que se muestra a continuación.

Una vez que los usuarios se hayan inscrito para MFA, la próxima vez que un usuario inicie sesión, verán un mensaje en el que se les pedirá que configuren el segundo factor de autenticación. Los métodos de autenticación compatibles son:


|Tipo de inquilino  |Opciones disponibles de segundo factor de MFA  |Notas  |
|---------|---------|---------|
|**Solo nube**     |MFA para Office 365 <ul><li>Llamada telefónica</li><li>Mensaje de texto</li><li>Notificación en la aplicación móvil</li><li>Código de verificación de la aplicación móvil</li></ul>        |[Planificar la autenticación multifactor para implementaciones de Office 365](https://support.office.com/article/Plan-for-multi-factor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba)         |
|**Configuración híbrida (modelo de identidad sincronizada o federada)**     |<ul><li>MFA para Office 365</li><li>Módulo de Azure MFA (integrado con ADFS)</li><li>Tarjeta inteligente física o virtual (integrada con ADFS)</li></ul>         |Nota: hay soluciones MFA adicionales disponibles con [documentos de compatibilidad del proveedor de identidades de Azure ad](https://www.microsoft.com/download/details.aspx?id=56843)         |
