---
title: Administrar la versión de prueba de primera línea en Teams
author: daisyfell
ms.author: daisyfeller
ms.reviewer: samanro
manager: pamgreen
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo configurar una Teams de 90 días para trabajadores de primera línea para su organización.
ms.localizationpriority: medium
ms.collection:
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 098cb4cd84616a9b26ea7df5c1451219fd5b5f0e
ms.sourcegitcommit: 8ce73ea99be607f5cdccb22a5366bc96e8fb09c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2022
ms.locfileid: "65758305"
---
# <a name="manage-the-frontline-trial-in-teams"></a>Administrar la versión de prueba de primera línea en Teams

> [!NOTE]
> Esta experiencia de prueba estará disponible próximamente. Puede comprobar cuándo está disponible para su organización si busca un mensaje en el [Centro](https://go.microsoft.com/fwlink/p/?linkid=2070717) de mensajes del centro de Administración de Microsoft 365.

La experiencia de prueba de frontline Microsoft Teams permite a los usuarios de su organización que se encuentran en Teams iniciar una experiencia de Teams para todo el equipo de primera línea, siempre y cuando los demás miembros estén en Azure Active Directory (Azure AD). Puede deshabilitar esta característica para los usuarios de su organización mediante el [módulo de PowerShell AllowSelfServicePurchase](/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell).

## <a name="what-services-are-included"></a>Qué servicios se incluyen

La versión de prueba incluye todo el contenido de la [licencia de Microsoft 365 F3](https://www.microsoft.com/microsoft-365/enterprise/f3) con las siguientes excepciones:

- La prueba frontline incluye Exchange Foundation en lugar de Exchange quiosco. Es posible que los usuarios falten otras funcionalidades Teams debido a este cambio.

## <a name="eligibility"></a>Elegibilidad

> [!NOTE]
> Puede comprobar si su organización forma parte del programa piloto de prueba si busca un anuncio en el [Centro](https://go.microsoft.com/fwlink/p/?linkid=2070717) de mensajes del centro de Administración de Microsoft 365. La organización tendrá que formar parte del programa piloto de prueba para que los usuarios puedan iniciar o participar en una prueba. Esta oferta no está disponible para los clientes de GCC, GCC High, DoD o EDU.

La versión de prueba frontline puede dar cabida a un máximo de 300 usuarios por prueba.

Los usuarios pueden iniciar una prueba de primera línea para su equipo si:

- Tener una licencia activa que les dé acceso a Teams.
- Aún no ha iniciado una prueba para trabajadores de primera línea.

> [!IMPORTANT]
> Si el usuario que inició la versión de prueba abandona la organización antes de que finalice la versión de prueba, como administrador tendrá que supervisar la versión de prueba, ponerse en contacto con el equipo para ver quién se beneficia de estas características y decidir qué usuarios necesitará actualizar a una licencia de pago.

Los usuarios pueden participar en una prueba para trabajadores de primera línea si tienen una dirección de correo electrónico de dominio de Azure Active Directory administrada.

Los usuarios pueden participar si han iniciado previamente una versión de prueba, pero no pueden iniciar otra prueba.

> [!NOTE]
> Los usuarios sin acceso existente a Teams solo se pueden agregar al equipo de prueba en el momento de la creación del equipo. Los usuarios de Teams existentes pueden agregarse a la versión de prueba después de crear el equipo.

## <a name="set-up-the-trial"></a>Configurar la versión de prueba

Los usuarios aptos pueden iniciar una prueba frontline iniciando sesión en la aplicación Tareas en Teams desde la [aplicación de](https://teams.microsoft.com/_#/apps/com.microsoft.teamspace.tab.planner/sections/mytasks) escritorio o web. En este momento, no se admite iniciar una versión de prueba de primera línea a través de dispositivos móviles. Cuando se inicia una versión de prueba, se asignará automáticamente la licencia de prueba de frontline a todo el equipo. A los usuarios con licencias de pago existentes que les proporcionan acceso a Teams también se les asignarán licencias de prueba, pero mantendrán la funcionalidad de sus licencias existentes durante toda la versión de prueba y conservarán sus licencias de pago existentes cuando finalice la versión de prueba. El usuario que inició la versión de prueba recibirá notificaciones por correo electrónico durante el transcurso de la versión de prueba.

## <a name="manage-the-frontline-trials-experience"></a>Administrar la experiencia de pruebas en primera línea

Los administradores pueden impedir que los usuarios finales inicien la prueba frontline dentro de su organización mediante el módulo de PowerShell **AllowSelfServicePurchase** . Esto es solo para licencias de prueba. [Obtenga información sobre cómo usar el módulo AllowSelfServicePurchase PowerShell](/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell).

### <a name="manage-teams-for-users-who-have-the-frontline-trial-license"></a>Administrar Teams para los usuarios que tienen la licencia de prueba de frontline

Puede administrar los usuarios que tienen la licencia de prueba de Frontline igual que los usuarios que tienen una licencia de pago normal. Para más información, vea [Administrar la configuración de Teams para su organización](/microsoftteams/manage-teams-overview).

### <a name="remove-a-trial-license"></a>Quitar una licencia de prueba

Puede quitar la licencia de prueba de frontline a través de PowerShell o su Centro de administración de Microsoft 365.

[Obtenga información sobre cómo quitar con PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).

[Obtenga información sobre cómo quitar en el centro de administración](/microsoft-365/admin/add-users/delete-a-user).

## <a name="upgrade-users-from-frontline-trial"></a>Actualizar usuarios de la versión de prueba de frontline

Los usuarios pueden ponerse en contacto con usted para solicitar licencias cuando finalice la versión de prueba. Necesitará privilegios de administrador para actualizar los usuarios.

### <a name="when-to-upgrade"></a>Cuándo actualizar

Cerca del final de la versión de prueba de 90 días, tendrá que consultar a los usuarios para ver quién debe continuar con una licencia de pago. Asegúrese de hacerlo antes de que expire la suscripción de prueba frontline para evitar interrupciones en las experiencias de los usuarios.

> [!IMPORTANT]
> Si la licencia frontline trial finaliza y no se asigna inmediatamente a un usuario una licencia que incluya Teams, perderá el acceso a Teams. Después de 30 días, sus datos (archivos, mensajes, etc.) se eliminan. El usuario aún existe en Azure Active Directory. Si se asigna una nueva licencia al usuario para habilitar Teams funcionalidad dentro del período de 30 días, todo su contenido en Teams seguirá existiendo.

### <a name="choose-an-upgrade-path"></a>Elegir una ruta de actualización

> [!TIP]
> La versión de prueba de Frontline se basa en la [licencia de Microsoft 365 F3](https://www.microsoft.com/microsoft-365/enterprise/f3).

Según las suscripciones que tenga actualmente su organización, hay tres maneras de actualizar de una versión de prueba de primera línea a una licencia de pago:

- **Actualice una suscripción de Microsoft 365 existente.** Use esta opción si su organización tiene suscripciones a otros productos de Office que no incluyen Teams. Para obtener más información, consulte [Actualizar a otro plan](/microsoft-365/commerce/subscriptions/upgrade-to-different-plan). Para ver los usuarios activos de una suscripción existente, vaya a **Usuarios >** [usuarios activos](https://go.microsoft.com/fwlink/p/?linkid=834822) en el Centro de administración de Microsoft 365.

- **Agregar usuarios a una suscripción de Microsoft 365 existente.** Use esta opción si su organización no tiene suficientes licencias de Teams pagadas para cubrir el equipo de primera línea. Para obtener más información, vea [Comprar o quitar licencias](/microsoft-365/commerce/licenses/buy-licenses). Para agregar usuarios a una suscripción existente que ya tiene suficientes licencias disponibles, consulte [Mover usuarios a una suscripción diferente](/microsoft-365/commerce/subscriptions/move-users-different-subscription). Para ver los usuarios activos de una suscripción existente, vaya a **Usuarios >** [usuarios activos](https://go.microsoft.com/fwlink/p/?linkid=834822) en el Centro de administración de Microsoft 365.

- **Comprar una nueva suscripción a Microsoft 365** Use esta opción si su organización no tiene suscripciones existentes para Office productos o si su organización quiere comprar una suscripción distinta de su suscripción existente para cubrir los usuarios de primera línea. Para obtener más información, vea [Microsoft 365 for frontline workers](https://www.microsoft.com/microsoft-365/enterprise/frontline).

Si no estás seguro de a qué Microsoft 365 suscripción actualizar, consulta [Microsoft 365 for frontline workers](https://www.microsoft.com/microsoft-365/enterprise/frontline). Si necesita ayuda adicional para elegir una suscripción, o si su organización necesita más de 300 licencias, póngase en contacto con su [asociado de Microsoft](https://www.microsoft.com/solution-providers/home) o representante de la cuenta de Microsoft.

### <a name="assign-paid-licenses"></a>Asignar licencias de pago

Para asignar las licencias recién adquiridas, consulte [Asignar licencias a usuarios](/microsoft-365/admin/manage/assign-licenses-to-users).  

Después de asignar las nuevas licencias, anule la asignación de las licencias de Teams Exploratory. Consulte [Cancelar la asignación de licencias de usuarios](/microsoft-365/admin/manage/remove-licenses-from-users), para obtener más información.

## <a name="faq"></a>Preguntas más frecuentes

**¿Cuánto tiempo dura la versión de prueba?** <br>
La versión de prueba frontline dura 90 días.

**¿Qué deben hacer los administradores al final de la experiencia de prueba frontline de 90 días?** <br>
Al final de la versión de prueba de 90 días, tendrá que consultar a los usuarios para ver quién necesita continuar con una licencia de pago. A continuación, deberá actualizar los [usuarios](#upgrade-users-from-frontline-trial).

**¿Qué sucede si el usuario que inició la versión de prueba deja la organización?** <br>
Como administrador, tendrá que supervisar la versión de prueba durante el resto del período de 90 días y actualizar a licencias pagadas para los usuarios que las necesiten cuando finalice la versión de prueba.

**¿Qué es la directiva de retención de datos?** <br>
Puede obtener información sobre la retención de datos en la [información Microsoft 365 suscripción](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?).

**¿Qué ocurre si un usuario encuentra un error al iniciar la versión de prueba de primera línea?** <br>
Asegúrese de que su organización, el usuario que inicia la prueba y los usuarios que se agregan a la versión de prueba cumplen los [criterios de elegibilidad](#eligibility).