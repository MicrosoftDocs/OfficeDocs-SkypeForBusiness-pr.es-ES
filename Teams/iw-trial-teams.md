---
title: Administrar la oferta de prueba comercial en la nube de Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/10/2018
ms.topic: article
audience: Admin
ms.reviewer: annikaelias
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
description: Los usuarios de Office 365 que no tienen licencia para Microsoft Teams pueden iniciar una versión de prueba de 1 año de los equipos.
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5101cc8f54d41aaf63b24fea1d9092b1465a81d7
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30462375"
---
<a name="manage-the-microsoft-teams-commercial-cloud-trial-offer"></a>Administrar la oferta de prueba comercial en la nube de Microsoft Teams
=======================================================

Microsoft Teams es una gran herramienta de colaboración para su organización. Permite a las personas y los equipos se analizan, innovar y compartir ideas utilizando la potencia de Office 365. Microsoft los equipos comerciales en la nube prueba ofrece usuarios de Office 365 existentes en la organización que no tienen licencia para que Microsoft Teams iniciar una versión de prueba de 1 año del producto. Los administradores pueden cambiar esta característica activada o desactivada para los usuarios de su organización.

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

La versión de evaluación concede una suscripción de prueba de un año en toda la organización. La versión de evaluación hace 500.000 licencias disponibles para la asignación. Para cada licencia asignada, la versión de evaluación asigna 2 GB de almacenamiento de SharePoint Online. 

## <a name="who-is-eligible"></a>¿Quiénes son elegibles

Los usuarios deben estar habilitados para registrarse y obtener aplicaciones y versiones de evaluación (en el centro de administración de Office 365). Para obtener más información, vea [Manage la versión de prueba](#manage-the-trial) más adelante en este artículo. 

Los usuarios que no tienen una licencia de Office 365 que incluye los equipos pueden iniciar la oferta de prueba de Microsoft los equipos comerciales en la nube. Por ejemplo, si un usuario tiene Office 365 Business (que no se incluyen los equipos), son aptos para la versión de evaluación.

## <a name="who-is-not-eligible"></a>Que no es válido

Su organización no está apto para la prueba if: 

- Usted es un cliente de socio de distribución
- Usted es un cliente de socio revendedor
- Usted es un cliente de gobierno o edu.

Si su organización es no válida para la oferta de prueba Microsoft los equipos de comercial en la nube, no verá el modificador **permiten a los usuarios instalar los servicios y aplicaciones de prueba** .

## <a name="how-users-sign-up-for-the-trial"></a>Cómo los usuarios suscribirse a la versión de evaluación

Los usuarios optan pueden registrarse para la oferta de prueba iniciando sesión en los equipos ([teams.microsoft.com](https://teams.microsoft.com)). Verán la pantalla siguiente para iniciar la versión de evaluación. 

![Captura de pantalla de la página de inicio para la versión de evaluación de los equipos trabajador de la información.](media/iw-trial-start-screen.png)

Todos los ensayos dentro de la organización compartan el mismo fechas inicial y final, que es la fecha del primer usuario suscrito a la versión de evaluación. Por ejemplo, si un usuario inicia la primera versión de evaluación en el 25 de enero de 2019 y el usuario B inicia una versión de prueba en 3 de junio de 2019, versión de prueba de los dos usuarios caducará el 25 de enero de 2020.

## <a name="manage-the-trial"></a>Administración de la versión de evaluación

Los administradores pueden administrar las licencias para los usuarios que han iniciado una sesión. 

Además, los administradores pueden deshabilitar la capacidad para los usuarios finales para aplicaciones de prueba y servicios dentro de su organización de notificación. Actualmente, la versión de evaluación que se describen en este artículo es la prueba sólo en esta categoría, pero es posible que se aplican a otros programas similares en el futuro. 

### <a name="prevent-users-from-installing-trial-apps-and-services"></a>Impedir que los usuarios instalen servicios y aplicaciones de prueba

Puede desactivar la capacidad de un usuario para instalar los servicios y aplicaciones de prueba.

1. Desde el [Centro de administración de Microsoft 365](https://portal.office.com/adminportal/home), vaya a **configuración** > **complementos & de servicios** > **usuario que son propiedad de aplicaciones y servicios**.

    ![Captura de pantalla de la página de complementos de servicios & en el centro de administración de Office 365.](media/iw-trial-enable-1.png)

2. Desactivar la opción **Permitir a los usuarios instalar los servicios y aplicaciones de prueba**.

    ![Captura de pantalla del usuario que pertenecen a la página de aplicaciones y servicios en el centro de administración de Office 365.](media/iw-trial-enable-2.png)


### <a name="manage-trial-availability-for-a-user-with-a-license-that-includes-teams"></a>Administrar la disponibilidad de prueba para un usuario con una licencia que incluye los equipos

Un usuario que se asigna una licencia que incluye los equipos no es apto para la versión de evaluación. Cuando está habilitado el plan de servicio de los equipos, el usuario puede iniciar sesión y utilizar los equipos. Si el plan de servicio está deshabilitado, el usuario no puede iniciar sesión y no se presenta ya sea con la opción de prueba.

Para desactivar el acceso a los equipos:

1. En el centro de administración de Microsoft 365, seleccione **los usuarios** > **usuarios activos**.

2. Active la casilla situada junto al nombre del usuario.

3. En la derecha, en la fila de **licencias de producto** , elija **Editar**.

4. En el panel de **licencias de producto** , cambie la alternancia a **desactivar**.

    ![Captura de pantalla de la página de licencias del producto en el centro de administración de Office 365.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-already-claimed-the-trial"></a>Administrar la disponibilidad de los equipos para los usuarios que ya se solicite la versión de evaluación

Si un usuario ha solicitado una licencia de prueba de los equipos, puede quitarlo mediante la eliminación de la licencia o plan de servicio.

Para desactivar la licencia de prueba:

1. En el centro de administración de Microsoft 365, seleccione **los usuarios** > **usuarios activos**.

2. Active la casilla situada junto al nombre del usuario.

3. En la derecha, en la fila de **licencias de producto** , elija **Editar**.

4. En el panel de **licencias de producto** , cambie la alternancia a **desactivar**.

    ![Captura de pantalla de la configuración de la licencia de prueba de los equipos en el panel de licencias de producto](media/iW-trial-enable-4.png)

### <a name="manage-teams-for-users-who-have-the-trial-license"></a>Administración de los equipos de los usuarios que tienen la licencia de prueba

Puede administrar los usuarios que tienen una licencia de prueba, al igual que administrar los usuarios que tienen una licencia de pagada regular. Para obtener más información, vea [características de administración de equipos de Microsoft en su organización de Office 365](enable-features-office-365.md).

### <a name="upgrade-users-from-the-trial-license"></a>Actualizar los usuarios de la licencia de prueba

Actualización de los usuarios de la licencia de prueba, realice lo siguiente:

1. Adquirir una suscripción que incluye los equipos.

2. Quitar la suscripción de prueba de los equipos del usuario.

3. Asignar la licencia adquirida recientemente.

Para obtener más información, consulte [Licencias de Office 365 para Microsoft Teams](Office-365-licensing.md).