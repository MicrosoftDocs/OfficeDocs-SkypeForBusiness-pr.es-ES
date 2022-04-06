---
title: Usar Microsoft 365 y conectores personalizados
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: Los conectores mantienen su equipo al día haciendo llegar contenido y actualizaciones de servicios que se usan con frecuencia directamente en un canal.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7fef0b28d9663cdb472f4daf79076c2d4eefcd66
ms.sourcegitcommit: 2ce3e95401ac06c0370a54862372a94ec6291d01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2022
ms.locfileid: "64642984"
---
# <a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a>Use Microsoft 365 y conectores personalizados en Microsoft Teams

Para mantener el equipo actualizado, los conectores ofrecen actualizaciones de servicio y contenido que se usan con frecuencia directamente en un canal Teams usuario. Con conectores, los Teams usuarios pueden recibir actualizaciones de servicios populares como Trello, Wunderlist, GitHub y Azure DevOps Services. Las actualizaciones se publican directamente en la transmisión de chat de su equipo.

Microsoft 365 conectores se usan con Microsoft Teams y Microsoft 365, lo que facilita que todos los miembros permanezcan sincronizados y reciban información relevante rápidamente. Tanto Microsoft Teams como Exchange el mismo modelo de conector, lo que le permite usar los mismos conectores en ambas plataformas. Sin embargo, vale la pena señalar que deshabilitar los conectores para el grupo de Microsoft 365 del que depende un equipo también deshabilita la capacidad de crear conectores para ese equipo.

Cualquier miembro de un equipo puede conectar su equipo a los servicios en la nube populares con los conectores si los permisos del equipo lo permiten y se notifica a todos los miembros del equipo de las actividades de ese servicio. Los conectores siguen funcionando después de que el miembro que ha configurado inicialmente el conector se haya ido. Cualquier miembro del equipo con los permisos para agregar o quitar puede modificar los conectores configurados por otros miembros.

> [!NOTE]
> Los conectores están deshabilitados de forma predeterminada en los entornos de Community (GCC) gubernamentales. Para habilitar estos, establezca los `ConnectorsEnabled` parámetros o `ConnectorsEnabledForTeams` en `$true` con el `SetOrganizationConfig` cmdlet. Conectar a la [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).

## <a name="add-a-connector-to-a-channel"></a>Agregar un conector a un canal

Actualmente, puede agregar conectores mediante Microsoft Teams de escritorio y web. Sin embargo, la información publicada por estos conectores se puede ver en **todos los clientes,** incluido el móvil.

1. Para agregar un conector a un canal, haga clic en los **puntos suspensivos (...),** a la derecha del nombre de un canal y, a continuación, haga clic **en Conectores**.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla de Teams interfaz con la opción Conectores seleccionada.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. Puede seleccionar entre una variedad de conectores disponibles y, a continuación, hacer clic en **Agregar**.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla del cuadro de diálogo Conectores que muestra los conectores disponibles.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. Complete la información necesaria del conector seleccionado y haga clic en **Guardar**. Cada conector requiere un conjunto diverso de información para funcionar correctamente; incluso es posible que algunos le pidan iniciar sesión en el servicio mediante los vínculos provistos en la página de configuración del conector.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla de la página de configuración para el conector de RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. Los datos proporcionados por el conector se publican automáticamente en el canal.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla de la interfaz de Teams donde se ve una conversación en un canal.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<!---Delete this section after customer migration to new Webhook URL is complete --->

> [!IMPORTANT]
> **Notificación de actualización de URL del conector**
>
> Los Teams están transfiriendo a una nueva dirección URL para mejorar la seguridad. Durante el transcurso de esta transición, recibirá determinadas notificaciones para actualizar el conector configurado para usar la nueva dirección URL. Se recomienda encarecidamente que actualice el conector inmediatamente para evitar cualquier interrupción en los servicios de conector. Es necesario seguir los pasos siguientes para actualizar la dirección URL:
>
> 1. En la página de configuración de conectores, se mostrará un mensaje "Atención requerida" en el botón "Administrar" para las conexiones que deben actualizarse.
> ![Captura de pantalla del mensaje "Atención requerida".](media/Teams_Attention_Required_message.png)
> 2. Para los conectores de webhook entrantes, los usuarios pueden volver a crear la conexión simplemente seleccionando Actualizar **dirección URL** y usando la dirección URL de webhook recién generada.
> ![Captura de pantalla del botón "Actualizar URL".](media/Teams_update_URL_button.png)
> 3. Para otros tipos de conector, el usuario tendría que quitar el conector y volver a crear la configuración del conector.
> 4. Verá un mensaje "La dirección URL está actualizada" después de que la dirección URL se haya actualizado correctamente.
> ![Captura de pantalla del mensaje "LA DIRECCIÓN URL está actualizada".](media/Teams_URL_up_to_date.png)

## <a name="see-also"></a>Vea también

* [Crear conectores y webhooks personalizados](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
