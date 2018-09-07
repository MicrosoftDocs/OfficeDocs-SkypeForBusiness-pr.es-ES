---
title: Administrar la oferta de prueba de la nube de Microsoft los equipos comerciales
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/31/2018
ms.topic: article
audience: Admin
ms.reviewer: alchen
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
description: Los usuarios de Office 365 que no tienen licencia para Microsoft Teams pueden iniciar una versión de prueba de 1 año de los equipos.
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 10977a95d5ff86d72964270a2c6daa7d9764448e
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23858824"
---
<a name="manage-the-microsoft-teams-commercial-cloud-trial-offer"></a>Administrar la oferta de prueba de la nube de Microsoft los equipos comerciales
=======================================================

Microsoft Teams es una gran herramienta de colaboración para su organización. Permite a las personas y los equipos se analizan, innovar y compartir ideas utilizando la potencia de Office 365. Microsoft los equipos comerciales en la nube prueba ofrece usuarios de Office 365 existentes en la organización que no tienen licencia para que Microsoft Teams iniciar una versión de prueba de 1 año del producto. Los administradores tienen la capacidad de activar o desactivar esta característica para los usuarios dentro de su inquilino.

> [!NOTE]
> Esta oferta aún no está públicamente disponible, pero se puede implantar durante el próximo mes.

## <a name="whats-in-the-offer"></a>¿Qué es en la oferta

Los planes de servicio incluidos en esta oferta son:

- Exchange Foundation
- Flujo para Office 365 Plan 1
- Organizador de Microsoft
- Equipos de Microsoft (Teams1, los equipos de trabajador de la información)
- Office Online
- Planeación de PowerApps para Office 365 1
- Quiosco de SharePoint Online
- Influir hora de elegir
- Yammer Enterprise

## <a name="who-is-eligible"></a>¿Quiénes son elegibles

Los usuarios que no tienen una licencia de Office 365 que incluye los equipos pueden iniciar la oferta de prueba de Microsoft los equipos comerciales en la nube. Por ejemplo, si un usuario tiene Office 365 Business Premium (que incluye los equipos) y el plan de servicio de los equipos está deshabilitado, no son aptos para la versión de evaluación.

Además, el inquilino no es aptos para la prueba if: 
- Usted es un cliente de socio de distribución
- Usted es un cliente de socio revendedor
- Usted es un cliente GCC, GOV o edu.

Además, si el inquilino es no válido para la oferta de prueba Microsoft los equipos de comercial en la nube, no verá el modificador **permiten a los usuarios instalar los servicios y aplicaciones de prueba** .

En el nivel de inquilino, los equipos como un servicio debe habilitarse (en el centro de administración de equipos). Para obtener más información, vea [características de administración de equipos de Microsoft en su organización de Office 365](enable-features-office-365.md). Además, deben estar habilitados para registrarse y obtener aplicaciones y versiones de evaluación (en el centro de administración de Office 365). Para obtener más información, vea [Manage la versión de prueba](#manage-the-trial) más adelante en este artículo.

## <a name="how-users-sign-up-for-the-trial"></a>Cómo los usuarios suscribirse a la versión de evaluación

Los usuarios optan pueden registrarse para la oferta de prueba iniciando sesión en los equipos ([teams.microsoft.com](https://teams.microsoft.com)). Si optan, verán la pantalla siguiente para iniciar la versión de evaluación. 

![Captura de pantalla de la página de inicio para la versión de evaluación de los equipos trabajador de la información.](media/iw-trial-start-screen.png)

La versión de evaluación concede una versión de prueba de un año en toda la organización. Esta versión de prueba hará 500.000 licencias disponibles para la asignación. Para cada licencia asignada, la versión de evaluación asigna 2 GB de almacenamiento de SharePoint Online. Los usuarios optan adicionales dentro de la organización pueden registrarse para la versión de prueba pasando por el mismo proceso.

Todos los ensayos dentro de la organización compartan el mismo fechas inicial y final, que es la fecha en que el primer usuario firmado para la versión de evaluación. Por ejemplo, si un usuario inicia la primera versión de evaluación en el 25 de abril de 2018 y el usuario B inicia una versión de prueba en 3 de junio de 2018, versión de prueba de los dos usuarios caducará el 25 de abril de 2019.

La primera persona que se registró para la versión de prueba es el "propietario" de la suscripción. Sólo esa persona puede administrar la suscripción. 

## <a name="manage-the-trial"></a>Administración de la versión de evaluación

Los administradores pueden deshabilitar la capacidad de los usuarios finales para aplicaciones de prueba y servicios dentro de su inquilino de notificación. Actualmente, la versión de evaluación de los equipos es la prueba sólo en esta categoría, pero esto es posible que se aplica a otros programas similares en el futuro. 

1\. Desde el [Centro de administración de Office 365](https://portal.office.com/adminportal/home), vaya a **Servicios & complementos** > **usuario que son propiedad de aplicaciones y servicios**.

![Captura de pantalla de la página Servicios & complementos en el centro de administración de Office 365.](media/iw-trial-enable-1.png)

2\. Desactivar la opción **Permitir a los usuarios instalar los servicios y aplicaciones de prueba**.

![Captura de pantalla del usuario que pertenecen a la página de aplicaciones y servicios en el centro de administración de Office 365.](media/iw-trial-enable-2.png)

3\. Puede desactivar los equipos para el inquilino yendo al portal de administración de equipos. Cuando esta opción está deshabilitada, los usuarios no se pueden reclamar que ofrecen los equipos de prueba.

4\. Si ha deshabilitado el plan de servicio de los equipos para un usuario individual que tiene una licencia de aplicaciones, el usuario no es aptos para una licencia de prueba de notificación.

5\. Si un usuario ha solicitado una licencia de prueba de los equipos, puede quitarlo mediante la eliminación de la licencia o plan de servicio. 

![Captura de pantalla de la página de licencias del producto en el centro de administración de Office 365.](media/iw-trial-enable-3.png)

### <a name="upgrade-users-from-the-trial-license"></a>Actualizar los usuarios de la licencia de prueba

Actualización de los usuarios de la licencia de prueba, realice lo siguiente:

1. Comprar un SKU que incluye los equipos.
2. Quitar el SKU de prueba de los equipos del usuario.
3. A continuación, asignar la licencia adquirida recientemente.

Para obtener más información, consulte [Licencias de Office 365 para Microsoft Teams](Office-365-licensing.md).