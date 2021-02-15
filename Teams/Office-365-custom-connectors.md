---
title: Usar Microsoft 365 y conectores personalizados
author: SerdarSoysal
ms.author: serdars
manager: serdars
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
description: Los conectores mantienen a su equipo al día al brindarles, directamente en un canal, contenido y actualizaciones de servicios que se utilizan con frecuencia.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 908469913944aea2a27feb8a35b0e5e5620aae3f
ms.sourcegitcommit: 44de1da5617f57f8c37780ad3451c0128f60b1f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2021
ms.locfileid: "50076422"
---
<a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a>Usar Microsoft 365 y conectores personalizados en Microsoft Teams
=======================================================

Los conectores mantienen actualizado a su equipo al proporcionar actualizaciones de servicio y contenido que se usan con frecuencia directamente en un canal. Con los conectores, los usuarios de Microsoft Teams pueden recibir actualizaciones de servicios populares como Trello, Wunderlist, GitHub y Azure DevOps Services en la secuencia de chat de su equipo.

Cualquier miembro de un equipo puede conectar su equipo a los servicios en la nube más populares con los conectores si los permisos del equipo lo permiten y se notifica a todos los miembros del equipo las actividades de ese servicio. Los conectores seguirán funcionando incluso después de que el miembro que inicialmente ha configurado el conector haya dejado de funcionar. Cualquier miembro del equipo que tenga los permisos para agregar o quitar puede modificar la configuración de conectores por otros miembros.

Los conectores de Microsoft 365 se pueden usar tanto con Microsoft Teams como con grupos de Microsoft 365, lo que facilita que todos los miembros se sincronicen y reciban información relevante rápidamente. Tanto Microsoft Teams como Exchange usan el mismo modelo de conector, lo que le permite usar los mismos conectores en ambas plataformas. Sin embargo, es importante destacar que deshabilitar los conectores para el grupo de Microsoft 365 del que depende un equipo deshabilitará también la capacidad de crear conectores para ese equipo.

<a name="add-a-connector-to-a-channel"></a>Agregar un conector a un canal
----------------------------

Actualmente, puede agregar conectores mediante clientes web y de escritorio de Microsoft Teams. Sin embargo, la información publicada por estos conectores se puede ver en **todos los clientes, incluidos** los móviles.

1. Para agregar un conector a un canal, haga clic en los puntos **suspensivos (...),** a la derecha del nombre de un canal y, a continuación, haga clic **en Conectores.**

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla de la interfaz de Teams con la opción Conectores seleccionada.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. Puede seleccionar entre una variedad de conectores disponibles y, a continuación, hacer clic en **Agregar.**

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla del cuadro de diálogo Conectores que muestra los conectores disponibles.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. Complete la información necesaria del conector seleccionado y haga clic en **Guardar**. Cada conector requiere un conjunto diverso de información para funcionar correctamente; incluso es posible que algunos le pidan iniciar sesión en el servicio mediante los vínculos provistos en la página de configuración del conector.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla de la página de configuración para el conector de RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. Los datos proporcionados por el conector se publican automáticamente en el canal.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla de la interfaz de Teams donde se ve una conversación en un canal.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> **Notificación de actualización de la dirección URL del conector**
>
> Los conectores de Teams están transición a una nueva dirección URL para mejorar la seguridad. Durante el transcurso de esta transición, recibirá determinadas notificaciones para actualizar el conector configurado y usar la nueva dirección URL. Se recomienda encarecidamente que actualice inmediatamente el conector para evitar interrupciones en los servicios del conector. Es necesario seguir los pasos siguientes para actualizar la dirección URL:
> 1. En la página de configuración de conectores, se mostrará el mensaje "Atención requerida" en el botón "Administrar" para las conexiones que deben actualizarse.
> ![Captura de pantalla del mensaje "Atención requerida".](media/Teams_Attention_Required_message.png)
> 2. Para los conectores de webhook entrantes, los usuarios pueden volver a crear la conexión simplemente seleccionando Dirección **URL** de actualización y usando la URL de grupo web recién generada.
> ![Captura de pantalla del botón "Dirección URL de actualización".](media/Teams_update_URL_button.png)
> 3. Para otros tipos de conector, el usuario tendría que quitar el conector y volver a crear la configuración del conector.
> 4. Verá el mensaje "La dirección URL está actualizada" después de que la dirección URL se haya actualizado correctamente.
> ![Captura de pantalla del mensaje "La dirección URL está actualizada".](media/Teams_URL_up_to_date.png)


<a name="develop-custom-connectors"></a>Desarrollar conectores personalizados
----------------------------

También puede crear conectores personalizados, así como webhooks entrantes y salientes. Consulte nuestra[ documentación para desarrolladores ](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)para obtener más información.
