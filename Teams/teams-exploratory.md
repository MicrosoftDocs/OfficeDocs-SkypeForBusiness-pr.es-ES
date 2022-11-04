---
title: Administrar la experiencia de Microsoft Teams Exploratory
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: high
description: Microsoft 365 o Office 365 usuarios que no tengan licencia de Microsoft Teams pueden iniciar una licencia exploratoria de Teams.
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5e5535be61aab03158aa11c68ebd3b753b3ca972
ms.sourcegitcommit: 18e66d54a9e349d4516253addc85cc12892c69a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2022
ms.locfileid: "68851780"
---
# <a name="manage-the-microsoft-teams-exploratory-license"></a>Administrar la licencia de Microsoft Teams Exploratory

The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (Azure AD) and aren't licensed for Teams initiate an exploratory experience of Teams. Admins can switch this feature on or off for users in their organization.

## <a name="whats-in-the-teams-exploratory-experience"></a>¿Qué incluye la experiencia de Teams Exploratory?

Los planes de servicio que verá un administrador como parte de la experiencia de Teams Exploratory son:

- Exchange Online (plan 1)
- Flow para Microsoft 365 u Office 365
- Información de MyAnalytics
- Microsoft Forms (plan E1)
- Microsoft Planner
- Búsqueda de Microsoft
- Microsoft StaffHub
- SKU de Microsoft Stream para Microsoft 365 y Office 365 E1 <sup>1</1>
- Microsoft Teams
- Administración de dispositivos móviles para Microsoft 365 u Office 365
- Aplicaciones móviles de Office para Office 365
- Office Online
- PowerApps para Microsoft 365 u Office 365
- SharePoint Online (plan 1)
- Sway
- To-Do (plan 1)
- Whiteboard (plan 1)
- Yammer Enterprise

  <sup>1</sup> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach. At launch, you'll be able to opt in to this experience. In November, you'll have to opt out if you want to continue using Stream. Sometime in early 2021, we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.

## <a name="whos-eligible"></a>Quién reúne los requisitos

Los usuarios se ajustan a los requerimientos para una experiencia de Teams Exploratory si:

- Tienen una dirección de correo electrónico de dominio de Azure AD administrada.
- Pertenecen a un espacio empresarial con una suscripción pagada.
- No tiene una licencia de Teams activa.
- No están en un inquilino donde se ha creado una directiva de asignación de licencias.

Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center). For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.

## <a name="who-isnt-eligible"></a>¿Quiénes no reúnen los requisitos?

Los usuarios no reúnen los requerimientos si:

- Actualmente tiene Teams con una licencia de pago o de prueba, o bien tenía anteriormente una licencia de prueba.
- Se encuentran en un espacio empresarial que ha recibido, al menos, una oferta especial COVID.

Su organización no es apta para esta oferta si usted es cliente de Syndication Partner o cliente de GCC, GCC High, DoD o EDU.

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a>¿Cómo los usuarios se pueden inscribir en la experiencia de Teams Exploratory?

Los usuarios que son aptos pueden inscribirse en la experiencia de Teams Exploratory iniciando sesión en Teams desde el equipo o la Web ([teams.microsoft.com](https://teams.microsoft.com)). En este momento, no se admite la habilitación exploratoria a través del móvil. Cuando se registre, se le asignará esta licencia automáticamente y el administrador de inquilinos recibirá una notificación por correo electrónico la primera vez que alguien de su organización inicie la experiencia exploratoria de Teams.

## <a name="manage-the-teams-exploratory-experience"></a>Administrar la experiencia de Teams Exploratory

La experiencia de Teams Exploratory está pensada para ser activada por usuarios finales individuales, y usted no puede activar esta oferta en nombre de los empleados que sean usuarios finales.

The Teams Exploratory experience comes with an Exchange Online license, but it won't be assigned to the user until the admin assigns it. If the user doesn't have an Exchange license already, and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and might be missing other Teams functionality.

Los administradores pueden desactivar la opción de que los usuarios finales ejecuten la experiencia de Teams Exploratory dentro de su organización mediante el uso del conmutador de **aplicaciones y servicios de prueba**.

### <a name="prevent-users-from-installing-trial-apps-and-services"></a>Evitar que los usuarios instalen aplicaciones y servicios de prueba

Puede desactivar la capacidad de un usuario para instalar aplicaciones y servicios de prueba, lo que impediría al usuario ejecutar la experiencia de Teams Exploratory.

1. Desde el Centro de administración de Microsoft 365, vaya a **Configuración** > **Configuración de la organización**, seleccione **Servicios**, y luego seleccione **Aplicaciones y servicios que son propiedad del usuario**.

    ![Captura de pantalla de la página Servicios en el centro de administración.](media/iw-trial-services.png)

2. Desactive la marca de verificación de **Permitir que los usuarios instalen aplicaciones y servicios de prueba**.

    ![Captura de pantalla de la página Aplicaciones y servicios pertenecientes al usuario en el centro de administración.](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > Si su organización no es apta para la experiencia de Teams Exploratory, no verá la opción **Dejar que los usuarios instalen aplicaciones y servicios de prueba**. 

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a>Administrar la disponibilidad de un usuario con una licencia que incluye Teams

Un usuario al que se le asigne una licencia que incluya Teams no es apto para la experiencia de Teams Exploratory. Cuando el plan de servicio de Teams está activado, el usuario puede iniciar sesión y utilizarlo. Si el plan de servicio está deshabilitado, el usuario no puede iniciar sesión y la experiencia exploratoria de Teams no está disponible. Debe tener privilegios de administrador.

Para desactivar el acceso a Teams:

1. En el Centro de administración de Microsoft 365, seleccione **Usuarios** > **Usuarios activos**.

2. Seleccione la casilla junto al nombre del usuario.

3. En la parte derecha, en la fila **Licencias de producto**, elija **Editar**.

4. En el panel **Licencias de producto**, cambie el botón de alternancia a **Desactivado**.

    ![La página de licencias del producto en el centro de administración.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a>Administrar la disponibilidad de Teams para los usuarios que ya estén utilizando la experiencia Teams Exploratory.

If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan. You must have admin privileges.

Desactivar la licencia de la experiencia Teams Exploratory:

1. En el Centro de administración de Microsoft 365, seleccione **Usuarios** > **Usuarios activos**.

2. Seleccione la casilla junto al nombre del usuario.

3. En la parte derecha, en la fila **Licencias de producto**, elija **Editar**.

4. En el panel de **licencias de producto**, cambie el botón de alternancia para la licencia exploratoria a **Desactivado**.

    > [!NOTE]
    > El botón de alternancia de Teams Exploratory aparecerá después de que el primer usuario de la organización inicie la experiencia de Teams Exploratory.

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a>Administrar Teams para los usuarios que dispongan de la licencia de Teams Exploratory

You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license. For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).

### <a name="upgrade-users-from-teams-exploratory"></a>Actualizar los usuarios de Teams Exploratory

Debe tener privilegios de administrador para actualizar usuarios de Teams Exploratory. Para obtener más información, consulte [Actualizar usuarios desde la prueba exploratoria de Teams](upgrade-from-teams-exploratory.md).

> [!NOTE]
> Si finaliza la licencia exploratoria de Teams y un usuario no se actualiza inmediatamente a una suscripción que incluye Teams, perderá el acceso a Teams, OneDrive y SharePoint después de un período de gracia de 30 días. Después de otros 30 días, se eliminan los datos asociados de Teams, OneDrive y SharePoint. El usuario aún existe en Azure Active Directory.
> 
> Una vez que se asigne una nueva licencia al usuario para habilitar de nuevo la funcionalidad de Teams, todo el contenido seguirá existiendo si se agrega el usuario dentro del plazo del período de gracia.

### <a name="remove-a-teams-exploratory-license"></a>Eliminar una licencia de Teams Exploratory

- Si usted desea eliminar la licencia usando PowerShell, consulte: [Eliminar las licencias de las cuentas de usuario con Office 365 PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)

- Si quiere eliminar esta licencia a través del Portal de administración, consulte: [Quitar a un usuario de su organización](/microsoft-365/admin/add-users/delete-a-user)

## <a name="what-is-the-data-retention-policy"></a>Qué es la directiva de retención de datos

Consulte [Información de la suscripción a Microsoft 365](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires).

## <a name="how-long-does-the-teams-exploratory-experience-last"></a>¿Cuánto tiempo dura la experiencia de Teams Exploratory?

Teams Exploratory está disponible como una suscripción de 12 meses (desde el registro inicial del usuario) para todos los clientes nuevos. La nueva suscripción de Teams Exploratory comienza cuando el primer usuario de una organización se registra en Teams Exploratory y expirará después de 12 meses. La fecha de expiración se aplicará a todos los usuarios del mismo espacio empresarial que el período de 12 meses que comienza en la fecha de registro del primer usuario.

> [!NOTE]
> La fecha de finalización de la experiencia se configura en un nivel de organización, lo que significa que se aplicará a todos los usuarios de la misma organización. Por ejemplo, el usuario 1 se registra en la suscripción el 1 de enero de 2021. Esto inicia una fecha de finalización de la suscripción del 31 de diciembre de 2021. Otro usuario, el usuario 2, se registra en la suscripción el 1 de octubre de 2021. El usuario 2 puede usar Teams Exploratory durante dos meses, ya que su fecha de finalización será el 31 de diciembre de 2021, porque está en la misma suscripción de organización que el usuario 1.

### <a name="what-should-administrators-do-at-the-end-of-the-12-month-teams-exploratory-experience"></a>Qué deberían hacer los administradores al final de la experiencia explorativa de 12 meses de Teams Exploratory

Al final de la suscripción de 12 meses, los administradores deberían cambiar a todos los usuarios de Teams Exploratory a una licencia de pago que incluya Teams. Es fundamental asegurarse de que esta acción se completa antes de que expire la suscripción exploratoria de Teams para evitar interrupciones en la experiencia del usuario.


> [!NOTE]
> Se deshabilitará a los clientes y se les impedirá que inicien nuevas licencias de prueba de Exploratory durante 3 meses pasado la fecha de expiración de la licencia de prueba de Exploratory anterior.

Para más información, consulte [Actualizar usuarios desde la licencia de Teams Exploratory](#upgrade-users-from-teams-exploratory), más arriba en este artículo.
