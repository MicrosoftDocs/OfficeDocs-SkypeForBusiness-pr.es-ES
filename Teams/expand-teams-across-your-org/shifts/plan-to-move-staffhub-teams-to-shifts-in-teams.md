---
title: Planear la transición de los equipos de StaffHub a turnos en Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: gumariam,aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo planear la transición de los equipos de StaffHub a turnos en Microsoft Teams.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ac278593215fc982d7246059503d8c65990c9b87
ms.sourcegitcommit: 3c40bdd228ef88967cdf689100f2030f6997d9d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2019
ms.locfileid: "36715920"
---
# <a name="plan-to-move-your-staffhub-teams-to-shifts-in-microsoft-teams"></a>Planear la transición de los equipos de StaffHub a turnos en Microsoft Teams

> [!IMPORTANT]
> A partir del 1 de octubre de 2019, Microsoft StaffHub se retirará. Estamos construyendo las capacidades de StaffHub en Microsoft Teams. En la actualidad, Teams incluye la aplicación de turnos para la administración de la programación, y las funciones adicionales se aplicarán a lo largo del tiempo. StaffHub dejará de funcionar para todos los usuarios el 1 de octubre de 2019. Cualquier persona que intente abrir StaffHub recibirá un mensaje para que pueda descargar Teams. Para obtener más información, consulte [Microsoft StaffHub para que se](microsoft-staffhub-to-be-retired.md)retirará. 

La transición de StaffHub a teams comienza al empezar a planificar el cambio. Para ayudar a garantizar que el cambio a teams se realice correctamente, hemos creado una escala de tiempo de ejemplo que muestra un plan de transición típico. La escala de tiempo de ejemplo describe las actividades de planeación para prepararse para el traslado y le permite mover los equipos de StaffHub de su organización a teams.

Use la escala de tiempo como guía para planear el desplazamiento de StaffHub a teams y personalizarlo según las necesidades de su organización. Asegúrese de revisar los recursos vinculados a los pasos de la escala de tiempo.

## <a name="prepare-to-move-your-staffhub-teams-to-teams"></a>Prepararse para mover los equipos de StaffHub a teams

|Paso |Instrucciones  |Recursos |
|---------|---------|---------|
|1    |Preparar e identificar las partes interesadas         |         |
|2     |Revise la documentación de la transición de StaffHub a la incorporación de equipos y equipos         |[StaffHub para que se retirará](microsoft-staffhub-to-be-retired.md)<br><br>[Mover los equipos de StaffHub a los cambios en Teams](move-staffhub-teams-to-shifts-in-teams.md)<br><br>[Introducción a teams](../../get-started-with-teams-quick-start.md)         |
|3    |Habilitar grupos de Office 365 para su organización        |[Grupos y equipos de Office 365](../../Office-365-groups.md)      |
|4    |Asegurarse de que se cumplan los requisitos previos         |[Comprobar que se cumplen los requisitos previos](move-staffhub-teams-to-shifts-in-teams.md#check-that-prerequisites-are-met)       |
|5   |Asignar licencias de Teams a los usuarios de StaffHub en su organización|[Asignar licencias de Teams](move-staffhub-teams-to-shifts-in-teams.md#assign-teams-licenses)<br><br>[Gestionar acceso de los usuarios a Microsoft Teams](../../user-access.md)      |
|6    |Instalar el módulo de PowerShell de StaffHub        |[Instalar el módulo de PowerShell de StaffHub](install-the-staffhub-powershell-module.md)        |
|7     |Determinar la escala de tiempo e identificar a los usuarios de StaffHub para moverlos a teams       |[Ejecutar un informe para mostrar el uso de StaffHub activo](run-report-to-show-staffhub-usage.md) |
|4,8     |Identificar a los usuarios de StaffHub que no tienen una cuenta de Azure AD (se muestra como "inactivo" en StaffHub) y vincular una cuenta     |[Vincular una cuenta de Azure AD a los miembros del equipo de StaffHub que no tengan una](move-staffhub-teams-to-shifts-in-teams.md#link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one)        |
|99,999    |Crear contenido de aprendizaje para los usuarios que están adaptados a la organización         |[Preparar un plan de preparación de usuarios para Teams](../../upgrade-user-readiness.md)     |
|base10    |Comunicarse con los usuarios de StaffHub acerca de la transición a los cambios en Teams         |[De StaffHub a teams ejemplo de comunicación de correo electrónico a usuarios](staffhub-to-teams-email-template.md)         |
|once     |Instalar clientes de Teams         |[Obtener clientes para Microsoft Teams](../../get-clients.md) |
|2007    |Asignar la Directiva de configuración de la aplicación FirstLineWorker a los usuarios (o crear y asignar una directiva de configuración de aplicación personalizada) para anclar la aplicación turnos a clientes de Teams  |[Asignar la Directiva de configuración de la aplicación de FirstlineWorker a los usuarios](move-staffhub-teams-to-shifts-in-teams.md#assign-the-firstlineworker-app-setup-policy-to-users)         |
|13     |Enseñar a los usuarios a usar turnos y equipos         |[Usuarios incorporados a teams](move-staffhub-teams-to-shifts-in-teams.md#onboard-users-to-teams)<br><br>[Desplaza la documentación de ayuda](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)<br><br>[Documentación de Ayuda de Teams](https://support.office.com/teams)<br><br>[Vídeos de aprendizaje de Teams](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)       |
|14     |Revise la lista de equipos de StaffHub para asegurarse de que todos los usuarios de esos equipos se deben mover a teams. Quitar usuarios que no deberían estar en la programación. |         |

## <a name="move-your-organizations-staffhub-teams-to-teams"></a>Mover los equipos de StaffHub de su organización a teams

|Paso |Instrucciones |Recursos  |
|---------|---------|---------|
|1  |Identificar un equipo piloto y mover un equipo          |[Mover un equipo de StaffHub](move-staffhub-teams-to-shifts-in-teams.md#move-a-staffhub-team)          |
|2    |Valide el equipo piloto e identifique los problemas de movimiento. Actualice la documentación de aprendizaje según sea necesario.         |         |
|3     |Identificar equipos piloto adicionales y pasar de cinco a diez equipos         |[Mover los equipos de StaffHub](move-staffhub-teams-to-shifts-in-teams.md#go-beyond-your-pilot-and-move-all-staffhub-teams)         |
|4     |Identificar equipos de StaffHub restantes y moverlos en un enfoque por fases         |[Mover los equipos de StaffHub](move-staffhub-teams-to-shifts-in-teams.md#go-beyond-your-pilot-and-move-all-staffhub-teams)         |
|5     |Seguir proporcionando soporte técnico para turnos y equipos         |         |
|6     |Si el restablecimiento de contraseñas de autoservicio está habilitado, ejecute un informe para admitir problemas de inicio de sesión en Teams       |[Ejecutar un informe para la configuración de restablecimiento de contraseña de autoservicio](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-reporting)        |
