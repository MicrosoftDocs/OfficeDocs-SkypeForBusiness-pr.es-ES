---
title: Usar el complemento para reunión de Microsoft Teams en Outlook
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Priority
search.appverid: MET150
description: Microsoft Teams instala un complemento en Outlook que permite a los usuarios programar reuniones de Microsoft Teams desde Outlook.
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: f465b03aacbaa1c7cd3cd835d279a112d0f87891
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23856876"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>Usar el complemento para reunión de Microsoft Teams en Outlook
=======================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

El complemento para reunión de Microsoft Teams se instala automáticamente para los usuarios que tienen instalado Microsoft Teams y Office 2013 o 2016 en su equipo Windows. Los usuarios verán el complemento para reunión de Microsoft Teams en la cinta del Calendario de Outlook. 

![Captura de pantalla del complemento de Microsoft Teams en la cinta de Outlook.](media/Teams-add-in-for-Outlook.png)

Si los usuarios no pueden ver el complemento de Microsoft Teams, pídales que cierren Outlook y Microsoft Teams, y que luego reinicien en primer lugar el cliente de Microsoft Teams y luego el de Outlook, específicamente en ese orden.

> [!NOTE]
> El complemento para reunión de Microsoft Teams para Outlook no está disponible actualmente para usuarios de Mac.

## <a name="authentication-requirements"></a>Requisitos de autenticación

El complemento para reunión de Microsoft Teams requiere que los usuarios inicien sesión en Microsoft Teams usando la autenticación moderna. Aunque los usuarios no usen este método para iniciar sesión, podrán usar el cliente de Microsoft Teams, pero no podrán programar reuniones en línea de Microsoft Teams usando el complemento de Outlook. Puede solucionar este inconveniente de una de las siguientes formas:

- Si la autenticación moderna no está configurada en su organización, configúrela.
- Si la autenticación moderna está configurada, pero el usuario opta por no utilizarla en el cuadro de diálogo, pídale que vuelva a iniciar sesión usando la autenticación multifactor.

Para obtener más información sobre cómo configurar la autenticación, consulte [Modelos de identidad y autenticación en Microsoft Teams](identify-models-authentication.md).

## <a name="enable-private-meetings"></a>Habilitar las reuniones privadas

Para que se implemente el complemento, debe estar habilitado Permitir la programación de reuniones privadas en el [Centro de administración de Office 365](https://portal.office.com/adminportal/home).

![Captura de pantalla de la configuración en la sección Llamadas y reuniones del Centro de administración de Office 365.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

El cliente de Microsoft Teams determina si los usuarios necesitan la versión de 32 o de 64 bits e instala el complemento correcto.

> [!NOTE]
> Es posible que los usuarios deban reiniciar Outlook después de una instalación o una actualización de Microsoft Teams para obtener el complemento más reciente.

## <a name="other-considerations"></a>Otras consideraciones

El complemento para reunión de Microsoft Teams sigue en proceso de desarrollo para ampliar sus funcionalidades, por lo que le recomendamos que tenga en cuenta lo siguiente:
- Algunas características de reunión en línea, como la grabación, los sondeos y el uso de pizarras todavía no están disponibles.
- Las opciones de reunión no están disponibles actualmente.
- En estos momentos, solo es posible invitar a personas de su compañía, dado que los usuarios externos todavía no pueden unirse a las reuniones.
- Este complemento es para reuniones programadas con participantes específicos, no para reuniones en un canal. Las reuniones de canal se deben programar desde Microsoft Teams. Actualmente, el complemento para reunión de Microsoft Teams en Outlook solo está disponible para usuarios de Windows, pero próximamente será compatible con Mac.
- El complemento no funciona si hay un proxy de autenticación en la ruta de red entre el equipo del usuario y los servicios de Microsoft Teams.
- El complemento se van a implantar incrementalmente y es posible que no esté disponible para su organización todavía.

## <a name="troubleshooting"></a>Solución de problemas

Si no se puede obtener la reunión de los equipos de complemento para Outlook instalar, intente estos pasos para solucionar problemas.

- Reinicie al cliente de escritorio de los equipos.
- Cierre la sesión y, a continuación, iniciar una sesión en el cliente de escritorio de los equipos.
- Reinicie al cliente de escritorio de Outlook. (Asegúrese de que Outlook no se está ejecutando en modo de administrador.)
- Asegúrese de que el nombre de cuenta de usuario que inició sesión no contiene espacios. (Esto es un problema conocido y se solucionará en una futura actualización.)
- Asegúrese de que está habilitado el inicio de sesión único (SSO).

Para obtener instrucciones generales sobre cómo desactivar complementos, consulte [Ver, administrar e instalar los complementos de los programas de Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).

Obtenga más información sobre [reuniones y llamadas en Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

