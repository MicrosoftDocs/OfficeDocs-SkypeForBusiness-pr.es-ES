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
appliesto:
- Microsoft Teams
ms.openlocfilehash: a266d9d3ea8fd572cca171768174d86094a8c945
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766973"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a>Administrar la licencia de Microsoft Teams Exploratory
=======================================================

La experiencia de Microsoft Teams Exploratory permite a los usuarios de su organización que tienen Azure Active Directory (Azure AD) y no tienen licencia para Teams activar una experiencia de Teams Exploratory Los administradores pueden activar o desactivar esta característica para los usuarios de su organización. La anterior [oferta de prueba comercial en la nube de Microsoft](iw-trial-teams.md) se ha reemplazado por la experiencia de Teams Exploratory.

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

  <sup>1</sup> El cambio de uso desde Microsoft Stream a [OneDrive para la Empresa y SharePoint para grabar reuniones](tmr-meeting-recording-change.md) estará basado en fases. Durante el lanzamiento podrá participar en esta experiencia. En noviembre, tendrá que decidir si quiere seguir usando la secuencia. En un momento, a principios de 2021, requerimos que todos los clientes usen OneDrive para la Empresa y SharePoint para las nuevas grabaciones de la reunión.

## <a name="whos-eligible"></a>¿Quiénes reúnen los requisitos?

Los usuarios se ajustan a los requerimientos para una experiencia de Teams Exploratory si:

- Tienen una dirección de correo electrónico de dominio de Azure AD administrada.
- Pertenecen a un inquilino con una suscripción pagada.

Los usuarios deben estar habilitados para registrarse en aplicaciones y versiones de prueba (en el Centro de administración de Microsoft 365). Para más información, vea [Administrar la experiencia Teams Exploratory](#manage-the-teams-exploratory-experience), más adelante en este artículo.

## <a name="who-isnt-eligible"></a>¿Quiénes no reúnen los requisitos?

Los usuarios no reúnen los requerimientos si:

- Actual o previamente tuvieron Teams de una licencia de prueba, pagada o no pagada. 
- Se encuentran en un espacio empresarial que ha recibido, al menos, una oferta especial COVID.

Su organización no es apta para esta oferta si usted es cliente de Syndication Partner o cliente de GCC, GCC High, DoD o EDU.

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a>¿Cómo los usuarios se pueden inscribir en la experiencia de Teams Exploratory?

Los usuarios que son aptos pueden registrarse para la oferta de la experiencia de Teams Exploratory iniciando sesión en Teams ([teams.microsoft.com](https://teams.microsoft.com)). Se les asignará esta licencia automáticamente y el administrador del inquilino recibirá una notificación por correo electrónico la primera vez que un usuario de su organización active la experiencia de Teams Exploratory.

## <a name="manage-the-teams-exploratory-experience"></a>Administrar la experiencia de Teams Exploratory

La experiencia de Teams Exploratory está pensada para ser activada por usuarios finales individuales, y usted no puede activar esta oferta en nombre de los empleados que sean usuarios finales.

La experiencia de Teams Exploratory viene con una licencia de Exchange Online pero no será asignada al usuario hasta que el administrador la asigne. Si el usuario no tiene una licencia de Exchange y el administrador aún no ha asignado la licencia de Exchange Online, el usuario no podrá programar reuniones en Teams y es posible que no disponga de otras características.

Los administradores pueden desactivar la opción de que los usuarios finales ejecuten la experiencia de Teams Exploratory dentro de su organización mediante el uso del conmutador de **aplicaciones y servicios de prueba** .

### <a name="prevent-users-from-installing-trial-apps-and-services"></a>Evitar que los usuarios instalen aplicaciones y servicios de prueba

Puede desactivar la capacidad de un usuario para instalar aplicaciones y servicios de prueba, lo que impediría al usuario ejecutar la experiencia de Teams Exploratory.

1. Desde el Centro de administración de Microsoft 365, vaya a **Configuración** > **Configuración de la organización** , seleccione **Servicios** , y luego seleccione **Aplicaciones y servicios que son propiedad del usuario** .

    ![Captura de pantalla de la página Servicios en el centro de administración.](media/iw-trial-services.png)

2. Desactive la casilla **Permitir que los usuarios instalen aplicaciones y servicios de prueba** .

    ![Captura de pantalla de la página Aplicaciones y servicios en propiedad del usuario en el centro de administración.](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > Si su organización no es apta para la experiencia de Teams Exploratory, no verá la opción **Dejar que los usuarios instalen aplicaciones y servicios de prueba** . 

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a>Administrar la disponibilidad de un usuario con una licencia que incluye Teams

Un usuario al que se le asigne una licencia que incluya Teams no es apto para la experiencia de Teams Exploratory. Cuando el plan de servicio de Teams está activado, el usuario puede iniciar sesión y utilizarlo. Si el plan de servicio está desactivado, el usuario no puede iniciar sesión y la experiencia de Teams Exploratory no estará disponible. Debe tener privilegios de administrador.

Para desactivar el acceso a Teams:

1. En el Centro de administración de Microsoft 365, seleccione **Usuarios** > **Usuarios activos** .

2. Seleccione la casilla junto al nombre del usuario.

3. En la parte derecha, en la fila **Licencias de producto** , elija **Editar** .

4. En el panel **Licencias de producto** , cambie el botón de alternancia a **Desactivado** .

    ![La página de licencias del producto en el centro de administración.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a>Administrar la disponibilidad de Teams para los usuarios que ya estén utilizando la experiencia Teams Exploratory.

Si un usuario está usando la experiencia Teams Exploratory, puede desactivarla eliminando la licencia o el plan de servicio. Debe tener privilegios de administrador.

Desactivar la licencia de la experiencia Teams Exploratory:

1. En el Centro de administración de Microsoft 365, seleccione **Usuarios** > **Usuarios activos** .

2. Seleccione la casilla junto al nombre del usuario.

3. En la parte derecha, en la fila **Licencias de producto** , elija **Editar** .

4. En el panel de **licencias de producto** , cambie el botón de alternancia para la licencia exploratoria a **Desactivado** .

    >[!Note]
    >El botón de alternancia de Teams Exploratory aparecerá después de que el primer usuario de la organización inicie la experiencia de Teams Exploratory.

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a>Administrar Teams para los usuarios que dispongan de la licencia de Teams Exploratory

Puede administrar a los usuarios que dispongan de la licencia de Teams Exploratory al igual que a los usuarios que dispongan de una licencia pagada estándar. Para más información, vea [Administrar la configuración de Teams para su organización](enable-features-office-365.md).

### <a name="upgrade-users-from-the-teams-exploratory-license"></a>Actualizar los usuarios de la licencia de Teams Exploratory

Para actualizar a los usuarios de la licencia de Teams Exploratory (debe tener privilegios de administrador), haga lo siguiente:

1. Adquiera una suscripción que incluya Teams.

2. Elimine la suscripción del usuario a Teams Exploratory.

3. Asignar la licencia que acaba de adquirir.

Para más información, consulte [Descripción del servicio de Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).

> [!NOTE]
> Si la licencia de Teams Exploratory finaliza y un usuario no se actualiza inmediatamente a una suscripción que incluya Teams, tiene 30 días de periodo de gracia y, a continuación, en el plazo de 30 días tras el que se van a eliminar los datos. El usuario seguirá existiendo en Azure Active Directory Una vez que se asigne una nueva licencia al usuario para habilitar de nuevo la funcionalidad de Teams, todo el contenido seguirá existiendo si se agrega el usuario dentro del plazo del período de gracia.

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a>¿Qué sucede con las licencias heredadas de la versión de prueba de Microsoft Teams Commercial Cloud?

A partir de febrero de 2020, los usuarios con elegibilidad podrán utilizar la versión más reciente de la experiencia de Microsoft Teams Exploratory. Todas las licencias de prueba de la nube comercial de Teams heredadas se convertirán automáticamente a la nueva oferta antes de que expire la prueba.

Cuando los usuarios inician sesión por primera vez en su versión de prueba comercial vencida en la nube de Teams, asignamos automáticamente una licencia de experiencia exploratoria de Teams a esos usuarios. Los usuarios no se convierten hasta que inician sesión.

### <a name="remove-a-teams-exploratory-license"></a>Eliminar una licencia de Teams Exploratory

- Si usted desea eliminar la licencia usando PowerShell, consulte: [Eliminar las licencias de las cuentas de usuario con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)

- Si quiere eliminar esta licencia a través del Portal de administración, consulte: [Quitar a un usuario de su organización](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)

## <a name="what-is-the-data-retention-policy"></a>Qué es la directiva de retención de datos

Consulte [Información de la suscripción a Microsoft 365](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).

## <a name="how-long-does-the-teams-exploratory-experience-last"></a>¿Cuánto tiempo dura la experiencia de Teams Exploratory?

La experiencia de Microsoft Teams Exploratory está disponible sin costo adicional hasta la próxima fecha del **aniversario** o **renovación del contrato** o en enero de 2021 o posteriormente. En ese momento, los usuarios finales de una licencia de la experiencia de Microsoft Exploratory tendrán que cambiarse a una licencia de pago que incluya Teams. Aquellas licencias de experiencia de Microsoft Exploratory que se inicien después de esa fecha permanecerán disponibles sin costo adicional hasta su próximo **aniversario** o ciclo de **renovación** .

### <a name="what-happens-if-an-end-user-initiates-the-microsoft-teams-exploratory-experience-just-before-the-anniversary-or-renewal-date"></a>¿Qué ocurre si un usuario final inicia la experiencia de Microsoft Teams Exploratory justo antes del aniversario o fecha de renovación?

Las licencias de la experiencia de Microsoft Teams Exploratory iniciadas en un plazo de 90 días antes de la fecha de **aniversario** o **renovación del contrato** de su empresa no deberán cambiarse a una licencia de pago hasta el siguiente aniversario o ciclo de renovación.

### <a name="what-if-my-agreement-doesnt-have-an-anniversary-or-yearly-renewal-date-for-example-month-to-month-agreements"></a>¿Qué ocurre si mi acuerdo no tiene ninguna fecha de aniversario o renovación anual (por ejemplo, acuerdos mensuales)?

En el caso de contratos sin una fecha de aniversario o una renovación anual, el año siguiente después de que el primer usuario final active las licencias de Microsoft Teams Exploratory se considerará como el aniversario o la fecha de renovación. Los usuarios de Microsoft Teams Exploratory deben pasar a una licencia de pago en esa fecha cada año, según las directivas anteriormente indicadas.

Por ejemplo, si el primer usuario final activa Microsoft Teams Exploratory el 19 de junio de 2020, este usuario y todos los demás elegibles en el espacio empresarial del cliente deben pasar a una licencia de pago con Teams el 19 de junio de 2021.

> [!Note]
> Se deshabilitará a los clientes y se les impedirá que inicien nuevas licencias de prueba de Exploratory durante 3 meses pasado la fecha de expiración de la licencia de prueba de Exploratory anterior.
