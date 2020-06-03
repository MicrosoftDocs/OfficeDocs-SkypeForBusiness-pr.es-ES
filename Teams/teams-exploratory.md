---
title: Administrar la experiencia de Microsoft Teams Exploratory
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: 502bdb8c5e441449680fa383b20f3e570d8a8ecc
ms.sourcegitcommit: ef3cd762e799df43bdcde03363c501d7ca9bb6b3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "44489132"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a>Administrar la licencia de Microsoft Teams Exploratory
=======================================================

La experiencia de Microsoft Teams Exploratory permite a los usuarios de su organización que tienen Azure Active Directory (AAD) y a los que no tienen licencia para Teams activar una experiencia de Teams Exploratory Los administradores pueden activar o desactivar esta característica para los usuarios de su organización. La anterior [oferta de prueba comercial en la nube de Microsoft](iw-trial-teams.md) se ha reemplazado por la experiencia de Teams Exploratory.

## <a name="whats-in-the-teams-exploratory-experience"></a>¿Qué es la experiencia de Teams Exploratory?

Los planes de servicio que verá un administrador como parte de la experiencia de Teams Exploratory son:
 - Exchange Online (plan 1)
 - Flow para Office 365
 - Información de MyAnalytics
 - Microsoft Forms (plan E1)
 - Microsoft Planner
 - Búsqueda de Microsoft
 - Microsoft StaffHub
 - Microsoft Stream para O365 E1 SKU
 - Microsoft Teams
 - Administración de dispositivos móviles para Office 365
 - Aplicaciones móviles de Office para Office 365 
 - Office Online
 - PowerApps para Office 365
 - SharePoint Online (plan 1)
 - Sway
 - To-Do (plan 1)
 - Whiteboard (plan 1)
 - Yammer Enterprise


## <a name="whos-eligible"></a>¿Quiénes reúnen los requisitos?

Mientras el usuario tenga una dirección de correo electrónico de dominio administrado de AAD y no se le haya asignado ninguna licencia de Teams, podrá participar en esta experiencia. Por ejemplo, si un usuario tiene Aplicaciones de Microsoft 365 para negocios (que no incluye Teams), puede optar por la experiencia de Teams Exploratory.

Los usuarios deben estar habilitados para registrarse en aplicaciones y versiones de prueba (en el Centro de administración de Microsoft 365). Para más información, vea [Administrar la experiencia Teams Exploratory](#manage-the-teams-exploratory-experience), más adelante en este artículo. 


## <a name="who-isnt-eligible"></a>¿Quiénes no reúnen los requisitos?

Su organización no es apta para esta oferta si usted es cliente de Syndication Partner o cliente de GCC, GCC High, DoD o EDU.


## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a>¿Cómo los usuarios se pueden inscribir en la experiencia de Teams Exploratory?

Los usuarios que son aptos pueden registrarse para la oferta de la experiencia de Teams Exploratory iniciando sesión en Teams ([teams.microsoft.com](https://teams.microsoft.com)). Se les asignará esta licencia automáticamente y el administrador del inquilino recibirá una notificación por correo electrónico la primera vez que un usuario de su organización active la experiencia de Teams Exploratory.

## <a name="manage-the-teams-exploratory-experience"></a>Administrar la experiencia de Teams Exploratory

La experiencia de Teams Exploratory está pensada para ser activada por usuarios finales individuales, y usted no puede activar esta oferta en nombre de los empleados que sean usuarios finales.

La experiencia de Teams Exploratory viene con una licencia de Exchange Online pero no será asignada al usuario hasta que el administrador la asigne. Si el usuario no tiene una licencia de Exchange y el administrador aún no ha asignado la licencia de Exchange Online, el usuario no podrá programar reuniones en Teams y es posible que no disponga de otras características.

Los administradores pueden desactivar la opción de que los usuarios finales ejecuten la experiencia de Teams Exploratory dentro de su organización mediante el uso del conmutador de **aplicaciones y servicios de prueba**.


### <a name="prevent-users-from-installing-trial-apps-and-services"></a>Evitar que los usuarios instalen aplicaciones y servicios de prueba

Puede desactivar la capacidad de un usuario para instalar aplicaciones y servicios de prueba, lo que impediría al usuario ejecutar la experiencia de Teams Exploratory. Debe tener privilegios de administrador. Para obtener más información sobre los roles de administrador, vea [Usar los roles de administrador de Microsoft Teams para administrar Teams](teams-exploratory.md).

1. Desde el [Centro de administración de Microsoft 365](https://portal.office.com/adminportal/home), vaya a **Configuración** > **Configuración**, seleccione **Servicios** y **Aplicaciones y servicios en propiedad del usuario**.

    ![Captura de pantalla de la página Servicios en el centro de administración.](media/iw-trial-services.png)

2. Desactive la casilla **Permitir que los usuarios instalen aplicaciones y servicios de prueba**.

    ![Captura de pantalla de la página Aplicaciones y servicios en propiedad del usuario en el centro de administración.](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > Si su organización no es apta para la experiencia de Teams Exploratory, no verá la opción **Dejar que los usuarios instalen aplicaciones y servicios de prueba**. 

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a>Administrar la disponibilidad de un usuario con una licencia que incluye Teams

Un usuario al que se le asigne una licencia que incluya Teams no es apto para la experiencia de Teams Exploratory. Cuando el plan de servicio de Teams está activado, el usuario puede iniciar sesión y utilizarlo. Si el plan de servicio está desactivado, el usuario no puede iniciar sesión y la experiencia de Teams Exploratory no estará disponible. Debe tener privilegios de administrador. 

Para desactivar el acceso a Teams:

1. En el [Centro de administración de Microsoft 365](https://portal.office.com/adminportal/home), seleccione **Usuarios** > **Usuarios activos**.

2. Seleccione la casilla junto al nombre del usuario.

3. En la parte derecha, en la fila **Licencias de producto**, elija **Editar**.

4. En el panel **Licencias de producto**, cambie el botón de alternancia a **Desactivado**.

    ![Captura de pantalla de la página Licencias de producto en el Centro de administración.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a>Administrar la disponibilidad de Teams para los usuarios que ya estén utilizando la experiencia Teams Exploratory.

Si un usuario está usando la experiencia Teams Exploratory, puede desactivarla eliminando la licencia o el plan de servicio. Debe tener privilegios de administrador. 

Desactivar la licencia de la experiencia Teams Exploratory:

1. En el Centro de administración de Microsoft 365, seleccione **Usuarios** > **Usuarios activos**.

2. Seleccione la casilla junto al nombre del usuario.

3. En la parte derecha, en la fila **Licencias de producto**, elija **Editar**.

4. En el panel de **licencias de producto**, cambie el botón de alternancia para la licencia exploratoria a** Desactivado**.
   
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
> Si la licencia de Teams Exploratory expira y el usuario no la actualiza de forma inmediata a un suscripción que incluya Teams, los datos del usuario no se eliminarán. El usuario seguirá existiendo en Azure Active Directory y todos los datos dentro de Teams se conservarán. Cuando una nueva licencia se asigne al usuario para volver a habilitar las funciones de Teams, todo el contenido seguirá existiendo. 

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a>¿Qué sucede con las licencias heredadas de evaluación en la Commercial Cloud de Microsoft Teams?

A partir de febrero de 2020, los usuarios aptos podrán utilizar la versión más reciente de la experiencia de Microsoft Teams Exploratory. Todas las licencias heredadas de la versión de evaluación de Commercial Cloud de Teams se convertirán automáticamente a un nuevo producto antes de que expire la versión de evaluación.

### <a name="remove-a-teams-exploratory-license"></a>Eliminar la licencia de Teams Exploratory

- Si usted desea eliminar la licencia usando PowerShell, vea: [Eliminar las licencias de las cuentas de usuario con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)

- Si quiere quitar esta licencia a través del portal de administración, vea: [Quitar licencias de usuarios en Office 365 para empresas](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/remove-licenses-from-users?view=o365-worldwide)

## <a name="how-long-does-the-teams-exploratory-experience-last"></a>¿Cuánto tiempo dura la experiencia de Teams Exploratory?

La experiencia de Microsoft Teams Exploratory está disponible sin costo adicional hasta la próxima fecha de **aniversario** o **renovación del contrato** empresarial, en enero de 2021 o después. En ese momento, los usuarios finales de una licencia de la experiencia de Microsoft Exploratory tendrán que cambiarse a una licencia de pago que incluya Teams. Aquellas licencias de experiencia de Microsoft Exploratory que se inicien después de esa fecha permanecerán disponibles sin costo adicional hasta su próximo **aniversario** o ciclo de **renovación**. 

### <a name="what-happens-if-an-end-user-initiates-the-microsoft-teams-exploratory-experience-just-before-my-anniversary-or-renewal-date"></a>¿Qué ocurre si un usuario final inicia la experiencia de Microsoft Teams Exploratory justo antes del aniversario o fecha de renovación?

Las licencias de la experiencia de Microsoft Teams Exploratory iniciadas en un plazo de 90 días antes de la fecha de **aniversario** o **renovación del contrato** de su empresa no deberán cambiarse a una licencia de pago hasta el siguiente aniversario o ciclo de renovación. 

### <a name="what-if-my-agreement-doesnt-have-an-anniversary-or-yearly-renewal-date-for-example-month-to-month-agreements"></a>¿Qué ocurre si mi acuerdo no tiene una fecha de aniversario o una renovación anual (por ejemplo, acuerdos mensuales)?

En el caso de contratos sin una fecha de aniversario o una renovación anual, el año siguiente después de que el primer usuario final active las licencias de Microsoft Teams Exploratory se considerará como el aniversario o la fecha de renovación. Los usuarios de Microsoft Teams Exploratory deben pasar a una licencia de pago en esa fecha cada año, según las directivas anteriormente indicadas.

Por ejemplo, si el primer usuario final activa Microsoft Teams Exploratory el 19 de junio de 2020, este usuario y todos los demás elegibles en el espacio empresarial del cliente deben pasar a una licencia de pago con Teams el 19 de junio de 2021. 

