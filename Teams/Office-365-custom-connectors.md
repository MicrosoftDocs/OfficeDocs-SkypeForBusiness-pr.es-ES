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
description: Los conectores mantienen su equipo al día haciendo llegar contenido y actualizaciones de servicios que se usan con frecuencia directamente en un canal.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3e6e65c3462242b82691a292770de684b6c4404b
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684247"
---
# <a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="d8dbe-103">Use Microsoft 365 y conectores personalizados en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8dbe-103">Use Microsoft 365 and custom connectors in Microsoft Teams</span></span>

<span data-ttu-id="d8dbe-104">Los conectores mantienen al equipo actualizado al ofrecer actualizaciones de servicio y contenido que se usan con frecuencia directamente en un canal.</span><span class="sxs-lookup"><span data-stu-id="d8dbe-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="d8dbe-105">Con conectores, los Microsoft Teams usuarios pueden recibir actualizaciones de servicios populares como Trello, Wunderlist, GitHub y Azure DevOps Services dentro de la transmisión de chat de su equipo.</span><span class="sxs-lookup"><span data-stu-id="d8dbe-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="d8dbe-106">Cualquier miembro de un equipo puede conectar su equipo a los servicios en la nube populares con los conectores si los permisos del equipo lo permiten y se notifica a todos los miembros del equipo de las actividades de ese servicio.</span><span class="sxs-lookup"><span data-stu-id="d8dbe-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="d8dbe-107">Los conectores seguirán funcionando incluso después de que el miembro que haya configurado inicialmente el conector se haya ido.</span><span class="sxs-lookup"><span data-stu-id="d8dbe-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="d8dbe-108">Cualquier miembro del equipo con los permisos para agregar o quitar puede modificar los conectores configurados por otros miembros.</span><span class="sxs-lookup"><span data-stu-id="d8dbe-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="d8dbe-109">Microsoft 365 conectores se pueden usar con grupos Microsoft Teams y Microsoft 365, lo que facilita que todos los miembros se sincronicen y reciban información relevante rápidamente.</span><span class="sxs-lookup"><span data-stu-id="d8dbe-109">Microsoft 365 connectors can be used with both Microsoft Teams and Microsoft 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="d8dbe-110">Tanto Microsoft Teams como Exchange el mismo modelo de conector, lo que le permite usar los mismos conectores en ambas plataformas.</span><span class="sxs-lookup"><span data-stu-id="d8dbe-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="d8dbe-111">Sin embargo, vale la pena señalar que deshabilitar los conectores para el grupo de Microsoft 365 del que depende un equipo también deshabilitará la capacidad de crear conectores para ese equipo.</span><span class="sxs-lookup"><span data-stu-id="d8dbe-111">It is worth noting, however, that disabling connectors for the Microsoft 365 group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

> [!NOTE]
> <span data-ttu-id="d8dbe-112">Los conectores están deshabilitados de forma predeterminada en los entornos de Community (GCC) gubernamentales.</span><span class="sxs-lookup"><span data-stu-id="d8dbe-112">Connectors are disabled by default in the Government Cloud Community (GCC) environments.</span></span> <span data-ttu-id="d8dbe-113">Si necesita habilitarlos, establezca los parámetros ConnectorsEnabled o ConnectorsEnabledForTeams en $true con el cmdlet [SetOrganizationConfig.](/powershell/module/exchange/set-organizationconfig?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="d8dbe-113">If you need to enable them, set the ConnectorsEnabled or ConnectorsEnabledForTeams parameters to $true with the [SetOrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) cmdlet.</span></span> <span data-ttu-id="d8dbe-114">Anteriormente tenía que conectarse a la [Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="d8dbe-114">You previously needed to connect to the [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="add-a-connector-to-a-channel"></a><span data-ttu-id="d8dbe-115">Agregar un conector a un canal</span><span class="sxs-lookup"><span data-stu-id="d8dbe-115">Add a connector to a channel</span></span>

<span data-ttu-id="d8dbe-116">Actualmente, puede agregar conectores mediante Microsoft Teams de escritorio y web.</span><span class="sxs-lookup"><span data-stu-id="d8dbe-116">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="d8dbe-117">Sin embargo, la información publicada por estos conectores se puede ver en **todos los clientes,** incluido el móvil.</span><span class="sxs-lookup"><span data-stu-id="d8dbe-117">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="d8dbe-118">Para agregar un conector a un canal, haga clic en los **puntos suspensivos (...),** a la derecha del nombre de un canal y, a continuación, haga clic **en Conectores.**</span><span class="sxs-lookup"><span data-stu-id="d8dbe-118">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d8dbe-119">![Captura de pantalla de Teams interfaz con la opción Conectores seleccionada.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span><span class="sxs-lookup"><span data-stu-id="d8dbe-119">![Screenshot of the Teams interface with the Connectors option selected.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span></span>

2. <span data-ttu-id="d8dbe-120">Puede seleccionar entre una variedad de conectores disponibles y, a continuación, hacer clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="d8dbe-120">You can select from a variety of available connectors, and then click **Add**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d8dbe-121">![Captura de pantalla del cuadro de diálogo Conectores que muestra los conectores disponibles.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span><span class="sxs-lookup"><span data-stu-id="d8dbe-121">![Screenshot of the Connectors dialog showing available the connectors.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span></span>

3. <span data-ttu-id="d8dbe-p106">Complete la información necesaria del conector seleccionado y haga clic en **Guardar**. Cada conector requiere un conjunto diverso de información para funcionar correctamente; incluso es posible que algunos le pidan iniciar sesión en el servicio mediante los vínculos provistos en la página de configuración del conector.</span><span class="sxs-lookup"><span data-stu-id="d8dbe-p106">Fill in the required information of the selected connector and click **Save**. Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d8dbe-124">![Captura de pantalla de la página de configuración para el conector de RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span><span class="sxs-lookup"><span data-stu-id="d8dbe-124">![Screenshot of the configuration page for the RSS connector.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span></span>

4. <span data-ttu-id="d8dbe-125">Los datos proporcionados por el conector se publican automáticamente en el canal.</span><span class="sxs-lookup"><span data-stu-id="d8dbe-125">Data provided by the connector is automatically posted to the channel.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d8dbe-126">![Captura de pantalla de la interfaz de Teams donde se ve una conversación en un canal.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span><span class="sxs-lookup"><span data-stu-id="d8dbe-126">![Screenshot of the Teams interface showing a conversation in a channel.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span></span>

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> <span data-ttu-id="d8dbe-127">**Notificación de actualización de URL del conector**</span><span class="sxs-lookup"><span data-stu-id="d8dbe-127">**Connector URL update notification**</span></span>
>
> <span data-ttu-id="d8dbe-128">Los Teams están transfiriendo a una nueva dirección URL para mejorar la seguridad.</span><span class="sxs-lookup"><span data-stu-id="d8dbe-128">The Teams connectors are transitioning to a new URL to enhance security.</span></span> <span data-ttu-id="d8dbe-129">Durante el transcurso de esta transición, recibirá determinadas notificaciones para actualizar el conector configurado para usar la nueva dirección URL.</span><span class="sxs-lookup"><span data-stu-id="d8dbe-129">During the course of this transition, you will receive certain notifications to update your configured connector to use the new URL.</span></span> <span data-ttu-id="d8dbe-130">Se recomienda encarecidamente que actualice el conector inmediatamente para evitar cualquier interrupción en los servicios de conector.</span><span class="sxs-lookup"><span data-stu-id="d8dbe-130">It is strongly recommended that you update your connector immediately to prevent any disruption to connector services.</span></span> <span data-ttu-id="d8dbe-131">Es necesario seguir los pasos siguientes para actualizar la dirección URL:</span><span class="sxs-lookup"><span data-stu-id="d8dbe-131">The following steps need to be followed to update the URL:</span></span>
> 1. <span data-ttu-id="d8dbe-132">En la página de configuración de conectores, se mostrará un mensaje "Atención requerida" en el botón "Administrar" para las conexiones que deben actualizarse.</span><span class="sxs-lookup"><span data-stu-id="d8dbe-132">In the connectors configuration page, an "Attention Required" message will be displayed under the "Manage" button for the connections that need to be updated.</span></span>
> <span data-ttu-id="d8dbe-133">![Captura de pantalla del mensaje "Atención requerida".](media/Teams_Attention_Required_message.png)</span><span class="sxs-lookup"><span data-stu-id="d8dbe-133">![Screenshot of the "Attention Required" message.](media/Teams_Attention_Required_message.png)</span></span>
> 2. <span data-ttu-id="d8dbe-134">Para los conectores de webhook entrantes, los usuarios pueden volver a crear la conexión simplemente seleccionando Actualizar **dirección URL** y usando la dirección URL de webhook recién generada.</span><span class="sxs-lookup"><span data-stu-id="d8dbe-134">For incoming webhook connectors, users can recreate the connection by simply selecting **Update URL** and using the newly generated webhook URL.</span></span>
> <span data-ttu-id="d8dbe-135">![Captura de pantalla del botón "Actualizar URL".](media/Teams_update_URL_button.png)</span><span class="sxs-lookup"><span data-stu-id="d8dbe-135">![Screenshot of the "Update URL" button.](media/Teams_update_URL_button.png)</span></span>
> 3. <span data-ttu-id="d8dbe-136">Para otros tipos de conector, el usuario tendría que quitar el conector y volver a crear la configuración del conector.</span><span class="sxs-lookup"><span data-stu-id="d8dbe-136">For other connector types, the user would need to remove the connector and recreate the connector configuration.</span></span>
> 4. <span data-ttu-id="d8dbe-137">Verá un mensaje "La dirección URL está actualizada" después de que la dirección URL se haya actualizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="d8dbe-137">You will see a message "URL is up-to-date" after the URL has been successfully updated.</span></span>
> <span data-ttu-id="d8dbe-138">![Captura de pantalla del mensaje "LA DIRECCIÓN URL está actualizada".](media/Teams_URL_up_to_date.png)</span><span class="sxs-lookup"><span data-stu-id="d8dbe-138">![Screenshot of the "URL is up-to-date" message.](media/Teams_URL_up_to_date.png)</span></span>


## <a name="develop-custom-connectors"></a><span data-ttu-id="d8dbe-139">Desarrollar conectores personalizados</span><span class="sxs-lookup"><span data-stu-id="d8dbe-139">Develop custom connectors</span></span>


<span data-ttu-id="d8dbe-140">También puede crear conectores personalizados, así como webhooks entrantes y salientes.</span><span class="sxs-lookup"><span data-stu-id="d8dbe-140">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="d8dbe-141">Consulte nuestra[ documentación para desarrolladores ](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d8dbe-141">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
