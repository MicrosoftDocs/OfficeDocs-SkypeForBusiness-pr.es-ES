---
title: Administrar la experiencia de Microsoft Teams Exploratory
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Los usuarios de Office 365 o Microsoft 365 que no tienen una licencia de Microsoft Teams pueden activar una licencia de Teams Exploratory.
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 368c4dace7a7ba14cb13f3a027b9d04ee63dc17b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119209"
---
# <a name="manage-the-microsoft-teams-exploratory-license"></a>Administrar la licencia de Microsoft Teams Exploratory

La experiencia de Microsoft Teams Exploratory permite a los usuarios de su organización que tienen Azure Active Directory (Azure AD) y no tengan licencia para los Teams iniciar una experiencia exploratoria de los Teams. Los administradores pueden activar o desactivar esta característica para los usuarios de su organización. La anterior [Prueba comercial en la nube de Microsoft]() se ha reemplazado por la experiencia de Teams Exploratory.

> [!NOTE]
> Hay un límite de 100 licencias de Microsoft Teams Exploratory por espacio empresarial.

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

  <sup>1</sup> El cambio de uso desde Microsoft Stream a [OneDrive para la Empresa y SharePoint para grabar reuniones](tmr-meeting-recording-change.md) estará basado en fases. Durante el lanzamiento, podrá participar en esta experiencia. En noviembre, tendrá que decidir si quiere seguir usando la secuencia. En un momento, a principios de 2021, requerimos que todos los clientes usen OneDrive para la Empresa y SharePoint para las nuevas grabaciones de la reunión.

## <a name="whos-eligible"></a>Quién reúne los requisitos

Los usuarios se ajustan a los requerimientos para una experiencia de Teams Exploratory si:

- Tienen una dirección de correo electrónico de dominio de Azure AD administrada.
- Pertenecen a un espacio empresarial con una suscripción pagada.
- No tienen una licencia activa de Teams.
- No están en un espacio empresarial donde se creó una directiva de asignación de licencias.

Se debe habilitar a los usuarios para registrarse en aplicaciones y pruebas (en el Centro de administración de Microsoft 365). Para obtener más información, consulte [Administrar la experiencia de Teams Exploratory](#manage-the-teams-exploratory-experience), más adelante en este artículo.

## <a name="who-isnt-eligible"></a>¿Quiénes no reúnen los requisitos?

Los usuarios no reúnen los requerimientos si:

- Ahora o anteriormente, tuvieron Teams mediante una licencia pagada, no pagada, o de prueba.
- Se encuentran en un espacio empresarial que ha recibido, al menos, una oferta especial COVID.

Su organización no es apta para esta oferta si usted es cliente de Syndication Partner o cliente de GCC, GCC High, DoD o EDU.

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a>¿Cómo los usuarios se pueden inscribir en la experiencia de Teams Exploratory?

Los usuarios que son aptos pueden inscribirse en la experiencia de Teams Exploratory iniciando sesión en Teams desde el equipo o la Web ([teams.microsoft.com](https://teams.microsoft.com)). Por ahora, no está disponible la habilitación de Exploratory mediante dispositivos móviles. Al registrarse, se les asignará esta licencia de manera automática, y el administrador del espacio empresarial recibirá una notificación por correo electrónico la primera vez que un usuario de su organización active la experiencia de Teams Exploratory.

## <a name="manage-the-teams-exploratory-experience"></a>Administrar la experiencia de Teams Exploratory

La experiencia de Teams Exploratory está pensada para ser activada por usuarios finales individuales, y usted no puede activar esta oferta en nombre de los empleados que sean usuarios finales.

La experiencia Teams Exploratory viene con una licencia de Exchange Online, pero no se asignará al usuario hasta que el administrador la asigne. Si el usuario no tiene una licencia de Exchange y el administrador aún no ha asignado la licencia de Exchange Online, el usuario no podrá programar reuniones en Teams y es posible que no disponga de otras características.

Los administradores pueden desactivar la opción de que los usuarios finales ejecuten la experiencia de Teams Exploratory dentro de su organización mediante el uso del conmutador de **aplicaciones y servicios de prueba**.

### <a name="prevent-users-from-installing-trial-apps-and-services"></a>Evitar que los usuarios instalen aplicaciones y servicios de prueba

Puede desactivar la capacidad de un usuario para instalar aplicaciones y servicios de prueba, lo que impediría al usuario ejecutar la experiencia de Teams Exploratory.

1. Desde el Centro de administración de Microsoft 365, vaya a **Configuración** > **Configuración de la organización**, seleccione **Servicios**, y luego seleccione **Aplicaciones y servicios que son propiedad del usuario**.

    ![Captura de pantalla de la página Servicios en el centro de administración.](media/iw-trial-services.png)

2. Quite la marca de verificación de **Permitir que los usuarios instalen aplicaciones y servicios de prueba**.

    ![Captura de pantalla de la página Aplicaciones y servicios en propiedad del usuario en el centro de administración.](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > Si su organización no es apta para la experiencia de Teams Exploratory, no verá la opción **Dejar que los usuarios instalen aplicaciones y servicios de prueba**. 

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a>Administrar la disponibilidad de un usuario con una licencia que incluye Teams

Un usuario al que se ha asignado una licencia que incluye Teams no es apto para la experiencia Teams Exploratory. Cuando el plan de servicio de Teams esté activado, el usuario puede iniciar sesión y usar Teams. Si el plan de servicio está deshabilitado, el usuario no podrá iniciar sesión y la experiencia Teams Exploratory no estará disponible. Debe tener privilegios de administrador.

Para desactivar el acceso a Teams:

1. En el Centro de administración de Microsoft 365, seleccione **Usuarios** > **Usuarios activos**.

2. Seleccione la casilla junto al nombre del usuario.

3. En la parte derecha, en la fila **Licencias de producto**, elija **Editar**.

4. En el panel **Licencias de producto**, cambie el botón de alternancia a **Desactivado**.

    ![La página de licencias del producto en el centro de administración.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a>Administrar la disponibilidad de Teams para los usuarios que ya estén utilizando la experiencia Teams Exploratory.

Si un usuario está usando la experiencia Teams Exploratory, puede desactivarla eliminando la licencia o el plan de servicio. Debe tener privilegios de administrador.

Desactivar la licencia de la experiencia Teams Exploratory:

1. En el Centro de administración de Microsoft 365, seleccione **Usuarios** > **Usuarios activos**.

2. Seleccione la casilla junto al nombre del usuario.

3. En la parte derecha, en la fila **Licencias de producto**, elija **Editar**.

4. En el panel de **licencias de producto**, cambie el botón de alternancia para la licencia exploratoria a **Desactivado**.

    > [!NOTE]
    > El botón de alternancia de Teams Exploratory aparecerá después de que el primer usuario de la organización inicie la experiencia de Teams Exploratory.

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a>Administrar Teams para los usuarios que dispongan de la licencia de Teams Exploratory

Puede administrar a los usuarios que dispongan de la licencia de Teams Exploratory al igual que a los usuarios que dispongan de una licencia pagada estándar. Para más información, consulte [Administrar la configuración de Teams para su organización](enable-features-office-365.md).

### <a name="upgrade-users-from-the-teams-exploratory-license"></a>Actualizar los usuarios de la licencia de Teams Exploratory

Para actualizar a los usuarios de la licencia de Teams Exploratory (debe tener privilegios de administrador), haga lo siguiente:

1. Adquiera una suscripción que incluya Teams.

2. Elimine la suscripción del usuario a Teams Exploratory.

3. Asignar la licencia que acaba de adquirir.

Para más información, consulte [Descripción del servicio de Microsoft Teams](/office365/servicedescriptions/teams-service-description).

> [!NOTE]
> Si la licencia de Teams Exploratory finaliza y un usuario no se actualiza inmediatamente a una suscripción que incluya Teams, tendrá 30 días de periodo de gracia y, a continuación, otros 30 días hasta que se eliminen los datos. El usuario aún existirá en Azure Active Directory. Cuando se asigne una nueva licencia al usuario para volver a habilitar la funcionalidad de Teams, todo el contenido seguirá existiendo si el usuario se agrega durante el período de tiempo del periodo de gracia.

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a>¿Qué sucede con las licencias heredadas de la versión de prueba de Microsoft Teams Commercial Cloud?

A partir del 2020 de febrero, los usuarios elegibles pueden empezar a usar la última experiencia de Microsoft Teams Exploratory. Se convertirán automáticamente a la nueva oferta todas las licencias de prueba de la nube comercial de Teams antiguas antes de que expire la versión de prueba.

Cuando los usuarios inician sesión por primera vez en su versión vencida de la prueba comercial en la nube de Teams, asignaremos automáticamente una licencia de experiencia exploratoria de Teams a esos usuarios. No se convertirá a los usuarios hasta que inicien sesión.

### <a name="remove-a-teams-exploratory-license"></a>Eliminar una licencia de Teams Exploratory

- Si usted desea eliminar la licencia usando PowerShell, consulte: [Eliminar las licencias de las cuentas de usuario con Office 365 PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)

- Si quiere eliminar esta licencia a través del Portal de administración, consulte: [Quitar a un usuario de su organización](/microsoft-365/admin/add-users/delete-a-user)

## <a name="what-is-the-data-retention-policy"></a>Qué es la directiva de retención de datos

Consulte [Información de la suscripción a Microsoft 365](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).

## <a name="how-long-does-the-teams-exploratory-experience-last"></a>¿Cuánto tiempo dura la experiencia de Teams Exploratory?

Desde principios de 2021, Teams Exploratory está disponible como una suscripción de 12 meses (desde el registro inicial del usuario) para todos los clientes nuevos. La nueva suscripción de Teams Exploratory comienza cuando el primer usuario de una organización se registra en Teams Exploratory y expirará después de 12 meses. La fecha de expiración se aplicará a todos los usuarios del mismo espacio empresarial que el período de 12 meses que comienza en la fecha de registro del primer usuario.

> [!NOTE]
> La fecha de finalización de la experiencia se configura en un nivel de organización, lo que significa que se aplicará a todos los usuarios de la misma organización. Por ejemplo, el usuario 1 se registra en la suscripción el 1 de enero de 2021. Esto inicia una fecha de finalización de la suscripción del 31 de diciembre de 2021. Otro usuario, el usuario 2, se registra en la suscripción el 1 de octubre de 2021. El usuario 2 puede usar Teams Exploratory durante dos meses, ya que su fecha de finalización será el 31 de diciembre de 2021, porque está en la misma suscripción de organización que el usuario 1.

### <a name="what-should-administrators-do-at-the-end-of-the-12-month-teams-exploratory-experience"></a>Qué deberían hacer los administradores al final de la experiencia explorativa de 12 meses de Teams Exploratory

Al final de la suscripción de 12 meses, los administradores deberían cambiar a todos los usuarios de Teams Exploratory a una licencia de pago que incluya Teams. Es fundamental asegurarse de que se completa antes de que expire la suscripción de Teams Exploratory para evitar interrupciones en la experiencia del usuario.


> [!NOTE]
> Se deshabilitará a los clientes y se les impedirá que inicien nuevas licencias de prueba de Exploratory durante 3 meses pasado la fecha de expiración de la licencia de prueba de Exploratory anterior.

Para más información, consulte [Actualizar usuarios desde la licencia de Teams Exploratory](#upgrade-users-from-the-teams-exploratory-license)), más arriba en este artículo.