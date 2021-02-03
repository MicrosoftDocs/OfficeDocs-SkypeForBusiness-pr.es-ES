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
<a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="2ee0a-103">Usar Microsoft 365 y conectores personalizados en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ee0a-103">Use Microsoft 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="2ee0a-p101">Los conectores mantienen al equipo al día al proporcionar actualizaciones de servicio y contenido usado con frecuencia directamente en un canal. Con los conectores, los usuarios de Microsoft Teams pueden recibir actualizaciones de servicios populares como Trello, Wunderlist, GitHub y Azure DevOps Services en la secuencia de chat de su equipo.</span><span class="sxs-lookup"><span data-stu-id="2ee0a-p101">Connectors keep your team current by delivering frequently used content and service updates directly into a channel. With connectors, your Microsoft Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="2ee0a-106">Cualquier miembro de un equipo puede conectar su equipo a los servicios en la nube más populares con los conectores si los permisos del equipo lo permiten y se notifica a todos los miembros del equipo las actividades de ese servicio.</span><span class="sxs-lookup"><span data-stu-id="2ee0a-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="2ee0a-107">Los conectores seguirán funcionando incluso después de que el miembro que inicialmente ha configurado el conector haya dejado de funcionar.</span><span class="sxs-lookup"><span data-stu-id="2ee0a-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="2ee0a-108">Cualquier miembro del equipo que tenga los permisos para agregar o quitar puede modificar la configuración de conectores por otros miembros.</span><span class="sxs-lookup"><span data-stu-id="2ee0a-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="2ee0a-109">Los conectores de Microsoft 365 se pueden usar tanto con Microsoft Teams como con grupos de Microsoft 365, lo que facilita que todos los miembros se sincronicen y reciban información relevante rápidamente.</span><span class="sxs-lookup"><span data-stu-id="2ee0a-109">Microsoft 365 connectors can be used with both Microsoft Teams and Microsoft 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="2ee0a-110">Tanto Microsoft Teams como Exchange usan el mismo modelo de conector, lo que le permite usar los mismos conectores en ambas plataformas.</span><span class="sxs-lookup"><span data-stu-id="2ee0a-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="2ee0a-111">Sin embargo, es importante destacar que deshabilitar los conectores para el grupo de Microsoft 365 del que depende un equipo deshabilitará también la capacidad de crear conectores para ese equipo.</span><span class="sxs-lookup"><span data-stu-id="2ee0a-111">It is worth noting, however, that disabling connectors for the Microsoft 365 group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="2ee0a-112">Agregar un conector a un canal</span><span class="sxs-lookup"><span data-stu-id="2ee0a-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="2ee0a-113">Actualmente, puede agregar conectores mediante clientes web y de escritorio de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2ee0a-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="2ee0a-114">Sin embargo, la información publicada por estos conectores se puede ver en **todos los clientes, incluidos** los móviles.</span><span class="sxs-lookup"><span data-stu-id="2ee0a-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="2ee0a-115">Para agregar un conector a un canal, haga clic en los puntos **suspensivos (...),** a la derecha del nombre de un canal y, a continuación, haga clic **en Conectores.**</span><span class="sxs-lookup"><span data-stu-id="2ee0a-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2ee0a-116">![Captura de pantalla de la interfaz de Teams con la opción Conectores seleccionada.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span><span class="sxs-lookup"><span data-stu-id="2ee0a-116">![Screenshot of the Teams interface with the Connectors option selected.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span></span>

2. <span data-ttu-id="2ee0a-117">Puede seleccionar entre una variedad de conectores disponibles y, a continuación, hacer clic en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="2ee0a-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2ee0a-118">![Captura de pantalla del cuadro de diálogo Conectores que muestra los conectores disponibles.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span><span class="sxs-lookup"><span data-stu-id="2ee0a-118">![Screenshot of the Connectors dialog showing available the connectors.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span></span>

3. <span data-ttu-id="2ee0a-p105">Complete la información necesaria del conector seleccionado y haga clic en **Guardar**. Cada conector requiere un conjunto diverso de información para funcionar correctamente; incluso es posible que algunos le pidan iniciar sesión en el servicio mediante los vínculos provistos en la página de configuración del conector.</span><span class="sxs-lookup"><span data-stu-id="2ee0a-p105">Fill in the required information of the selected connector and click **Save**. Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2ee0a-121">![Captura de pantalla de la página de configuración para el conector de RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span><span class="sxs-lookup"><span data-stu-id="2ee0a-121">![Screenshot of the configuration page for the RSS connector.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span></span>

4. <span data-ttu-id="2ee0a-122">Los datos proporcionados por el conector se publican automáticamente en el canal.</span><span class="sxs-lookup"><span data-stu-id="2ee0a-122">Data provided by the connector is automatically posted to the channel.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2ee0a-123">![Captura de pantalla de la interfaz de Teams donde se ve una conversación en un canal.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span><span class="sxs-lookup"><span data-stu-id="2ee0a-123">![Screenshot of the Teams interface showing a conversation in a channel.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span></span>

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> <span data-ttu-id="2ee0a-124">**Notificación de actualización de la dirección URL del conector**</span><span class="sxs-lookup"><span data-stu-id="2ee0a-124">**Connector URL update notification**</span></span>
>
> <span data-ttu-id="2ee0a-125">Los conectores de Teams están transición a una nueva dirección URL para mejorar la seguridad.</span><span class="sxs-lookup"><span data-stu-id="2ee0a-125">The Teams connectors are transitioning to a new URL to enhance security.</span></span> <span data-ttu-id="2ee0a-126">Durante el transcurso de esta transición, recibirá determinadas notificaciones para actualizar el conector configurado y usar la nueva dirección URL.</span><span class="sxs-lookup"><span data-stu-id="2ee0a-126">During the course of this transition, you will receive certain notifications to update your configured connector to use the new URL.</span></span> <span data-ttu-id="2ee0a-127">Se recomienda encarecidamente que actualice inmediatamente el conector para evitar interrupciones en los servicios del conector.</span><span class="sxs-lookup"><span data-stu-id="2ee0a-127">It is strongly recommended that you update your connector immediately to prevent any disruption to connector services.</span></span> <span data-ttu-id="2ee0a-128">Es necesario seguir los pasos siguientes para actualizar la dirección URL:</span><span class="sxs-lookup"><span data-stu-id="2ee0a-128">The following steps need to be followed to update the URL:</span></span>
> 1. <span data-ttu-id="2ee0a-129">En la página de configuración de conectores, se mostrará el mensaje "Atención requerida" en el botón "Administrar" para las conexiones que deben actualizarse.</span><span class="sxs-lookup"><span data-stu-id="2ee0a-129">In the connectors configuration page, an "Attention Required" message will be displayed under the "Manage" button for the connections that need to be updated.</span></span>
> <span data-ttu-id="2ee0a-130">![Captura de pantalla del mensaje "Atención requerida".](media/Teams_Attention_Required_message.png)</span><span class="sxs-lookup"><span data-stu-id="2ee0a-130">![Screenshot of the "Attention Required" message.](media/Teams_Attention_Required_message.png)</span></span>
> 2. <span data-ttu-id="2ee0a-131">Para los conectores de webhook entrantes, los usuarios pueden volver a crear la conexión simplemente seleccionando Dirección **URL** de actualización y usando la URL de grupo web recién generada.</span><span class="sxs-lookup"><span data-stu-id="2ee0a-131">For incoming webhook connectors, users can recreate the connection by simply selecting **Update URL** and using the newly generated webhook URL.</span></span>
> <span data-ttu-id="2ee0a-132">![Captura de pantalla del botón "Actualizar DIRECCIÓN URL".](media/Teams_update_URL_button.png)</span><span class="sxs-lookup"><span data-stu-id="2ee0a-132">![Screenshot of the "Update URL" button.](media/Teams_update_URL_button.png)</span></span>
> 3. <span data-ttu-id="2ee0a-133">Para otros tipos de conector, el usuario tendría que quitar el conector y volver a crear la configuración del conector.</span><span class="sxs-lookup"><span data-stu-id="2ee0a-133">For other connector types, the user would need to remove the connector and recreate the connector configuration.</span></span>
> 4. <span data-ttu-id="2ee0a-134">Verá el mensaje "La dirección URL está actualizada" después de que la dirección URL se haya actualizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="2ee0a-134">You will see a message "URL is up-to-date" after the URL has been successfully updated.</span></span>
> <span data-ttu-id="2ee0a-135">![Captura de pantalla del mensaje "La dirección URL está actualizada".](media/Teams_URL_up_to_date.png)</span><span class="sxs-lookup"><span data-stu-id="2ee0a-135">![Screenshot of the "URL is up-to-date" message.](media/Teams_URL_up_to_date.png)</span></span>


<a name="develop-custom-connectors"></a><span data-ttu-id="2ee0a-136">Desarrollar conectores personalizados</span><span class="sxs-lookup"><span data-stu-id="2ee0a-136">Develop custom connectors</span></span>
----------------------------

<span data-ttu-id="2ee0a-137">También puede crear conectores personalizados, así como webhooks entrantes y salientes.</span><span class="sxs-lookup"><span data-stu-id="2ee0a-137">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="2ee0a-138">Consulte nuestra[ documentación para desarrolladores ](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2ee0a-138">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
