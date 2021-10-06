---
title: Active o desactive el acceso de invitado a Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
ms.localizationpriority: medium
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: Obtenga más información sobre cómo habilitar o deshabilitar el acceso de invitado en Microsoft Teams como administrador de Office 365.
ms.openlocfilehash: 2b444b8357d8edef9aaa1c9c8e72ae6762f5bd52
ms.sourcegitcommit: 74d3ab35c344d70b2399bc46a6ced3ab2762a470
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60138246"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>Active o desactive el acceso de invitado a Microsoft Teams

> [!Note]
>
> Hasta **febrero de 2021,** el acceso de invitado está desactivado de forma predeterminada. Debe habilitar el acceso de invitado para Teams antes de que los administradores o los propietarios del equipo puedan agregar invitados. Después de activar el acceso de invitado, es posible que los cambios tarden unas horas en tener efecto. Si los usuarios  ven el mensaje Póngase en contacto con el administrador cuando intenten agregar un invitado a su equipo, es probable que no se haya activado el acceso de invitado o que la configuración aún no sea efectiva.
>
> Después de febrero de **2021,** el acceso de invitado en Microsoft Teams estará activado de forma predeterminada para los nuevos clientes & clientes existentes que no hayan configurado esta configuración. Cuando se implemente este cambio, si aún no ha configurado la capacidad de acceso de invitado en Microsoft Teams, esa capacidad se habilitará en el espacio empresarial. Si desea que el acceso de invitado permanezca deshabilitado para su organización, tendrá que confirmar que la configuración de acceso de invitado está establecida en **Desactivado** en lugar de **Servicio predeterminado.**

> [!IMPORTANT]
> El habilitar el acceso de invitado depende de las características de Azure Active Directory, Microsoft 365, SharePoint y Teams. Para obtener más información, consulte [Colaborar con invitados en un equipo](/microsoft-365/solutions/collaborate-as-team).

## <a name="configure-guest-access-in-the-teams-admin-center"></a>Configurar el acceso de invitado en el centro de administración de Teams

1. Inicie sesión en el [Centro de administración de Microsoft Teams](https://admin.teams.microsoft.com/).

2. Seleccione **Acceso de invitado** de  >  **usuarios**.

3. Establezca **Permitir el acceso de invitado en Teams** en **On**.

    ![Permitir el modificador de acceso de invitado establecido en Activar .](media/guest-access-setting.png)

4. En **Llamadas,** **reuniones** **y** mensajería,  seleccione **Activar** o Desactivar para cada función, dependiendo de lo que quiera permitir a los invitados.

      - **Realizar llamadas privadas**: cambie esta opción a **Activado** para permitir que los invitados realicen llamadas entre compañeros.
      - **Vídeo IP:** active esta configuración **para** permitir que los invitados usen vídeo en sus llamadas y reuniones.
      - **Modo de uso compartido de** pantalla: esta configuración controla la disponibilidad del uso compartido de pantalla para los invitados.
          - Establezca esta opción como **Desactivado** para eliminar la posibilidad de que los invitados compartan sus pantallas en Teams.
          - Establezca esta opción como **Solicitud única** para permitir el uso compartido de aplicaciones individuales.
          - Establezca esta opción como **Pantalla completa** para permitir el uso de pantalla completa compartida.
      - **Reunirse ahora:** active esta opción **para** permitir que los invitados usen la característica Reunirse ahora en Microsoft Teams.
      - **Editar mensajes enviados**: establezca esta opción como **Activado** para permitir que los invitados editen los mensajes que han enviado anteriormente.
      - **Eliminar mensajes enviados:** active **esta** opción para permitir que los invitados eliminen los mensajes que enviaron anteriormente.
      - **Chat**: establezca esta opción como **Activado** para permitir a los invitados usar el chat en Teams.
      - **Giphy en conversaciones:** active esta **configuración** para permitir que los invitados usen Giphys en las conversaciones. Giphy es una base de datos en línea y un motor de búsqueda que permite a los usuarios buscar y compartir archivos GIF animados. A cada Giphy se le asigna una clasificación de contenido.
      - **Clasificación de contenido Giphy**: seleccione una clasificación de la lista desplegable:
          - **Permitir todo el contenido**: los invitados podrán insertar todos los Giphy en chats, independientemente de la clasificación de contenido.
          - **Moderado**: los invitados pueden insertar imágenes Giphy en los chats, pero el contenido para adultos estará restringido de forma moderada.
          - **Estricto:** los invitados pueden insertar Giphys en chats, pero no podrán insertar contenido para adultos.
      - **Memes en conversaciones:** active esta **configuración** para permitir que los invitados usen Memes en conversaciones.
      - **Adhesivos en conversaciones:** active esta **configuración** para permitir que los invitados usen adhesivos en las conversaciones.
      - **Lector inmersivo para mensajes:** active **esta** configuración para permitir a los invitados usar lector [inmersivo en Teams](https://support.microsoft.com/topic/a700c0d0-bc53-4696-a94d-4fbc86ac7a9a).

    ![Configuración de permisos de invitado en Teams.](media/manage-guest-access-image1.png)

5. Seleccione **Guardar**.

## <a name="external-access-federation-vs-guest-access"></a>Acceso externo (federación) frente a acceso de invitado

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a>Consulte también

[Configurar la colaboración moderna con Microsoft 365](/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[Bloquear invitados de un equipo específico](/microsoft-365/solutions/per-group-guest-access)

[Set-CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)
