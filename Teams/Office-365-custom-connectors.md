---
title: Usar Office 365 y conectores personalizados en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
description: Los conectores mantienen a su equipo al día al brindarles, directamente en un canal, contenido y actualizaciones de servicios que se utilizan con frecuencia.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b1dc57bbe3d216ee779f962ef4b2fc1152e2161
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37563858"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="7789f-103">Usar Office 365 y conectores personalizados en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7789f-103">Use Office 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="7789f-p101">Los conectores mantienen actualizado a su equipo mediante la entrega de contenido y actualizaciones de servicio de uso frecuente directamente en un canal. Con los conectores, los usuarios de Microsoft Teams pueden recibir actualizaciones de servicios populares como Twitter, Trello, Wunderlist, GitHub y Azure DevOps dentro del flujo de chat de su equipo.</span><span class="sxs-lookup"><span data-stu-id="7789f-p101">Connectors keep your team current by delivering frequently used content and service updates directly into a channel. With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="7789f-106">Cualquier miembro de un equipo puede conectar su equipo a servicios en la nube populares con los conectores si los permisos del equipo lo permiten y todos los miembros del equipo reciben notificaciones de actividades de ese servicio.</span><span class="sxs-lookup"><span data-stu-id="7789f-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="7789f-107">Los conectores seguirán funcionando incluso después de que el miembro haya dejado de instalar el conector.</span><span class="sxs-lookup"><span data-stu-id="7789f-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="7789f-108">Cualquier miembro del equipo con los permisos para quitar la configuración de otros miembros puede modificar los conectores.</span><span class="sxs-lookup"><span data-stu-id="7789f-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="7789f-109">Los conectores de Office 365 se pueden usar con grupos de Microsoft Teams y Office 365, lo que permite que todos los miembros permanezcan sincronizados y reciban la información relevante rápidamente.</span><span class="sxs-lookup"><span data-stu-id="7789f-109">Office 365 connectors can be used with both Microsoft Teams and Office 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="7789f-110">Tanto Microsoft Teams como Exchange usan el mismo modelo de conector, que le permite usar los mismos conectores en ambas plataformas.</span><span class="sxs-lookup"><span data-stu-id="7789f-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="7789f-111">Sin embargo, vale la pena tener en cuentan que deshabilitar conectores para el grupo de Office 365 del que depende un equipo deshabilitará la capacidad de crear conectores para ese equipo también.</span><span class="sxs-lookup"><span data-stu-id="7789f-111">It is worth noting, however, that disabling connectors for the Office 365 Group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="7789f-112">Agregar un conector a un canal</span><span class="sxs-lookup"><span data-stu-id="7789f-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="7789f-113">En la actualidad, puede Agregar conectores con el escritorio de Microsoft Teams y los clientes Web.</span><span class="sxs-lookup"><span data-stu-id="7789f-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="7789f-114">Sin embargo, la información publicada por estos conectores puede verse en **todos los clientes** , incluidos los teléfonos móviles.</span><span class="sxs-lookup"><span data-stu-id="7789f-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="7789f-115">Para agregar un conector a un canal, haga clic en los **puntos suspensivos (...),** a la derecha de un nombre de canal y, a continuación, haga clic en **conectores**.</span><span class="sxs-lookup"><span data-stu-id="7789f-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    ![Captura de pantalla de la interfaz de equipos con la opción conectores seleccionada.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. <span data-ttu-id="7789f-117">Puede elegir entre una variedad de conectores disponibles y, a continuación, hacer clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="7789f-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    ![Captura de pantalla del cuadro de diálogo conectores que muestra los conectores disponibles.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. <span data-ttu-id="7789f-p105">Complete la información necesaria del conector seleccionado y haga clic en **Guardar**. Cada conector requiere un conjunto diverso de información para funcionar correctamente; incluso es posible que algunos le pidan iniciar sesión en el servicio mediante los vínculos provistos en la página de configuración del conector.</span><span class="sxs-lookup"><span data-stu-id="7789f-p105">Fill in the required information of the selected connector and click **Save**. Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    ![Captura de pantalla de la página de configuración para el conector de RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. <span data-ttu-id="7789f-122">Los datos proporcionados por el conector se publican automáticamente en el canal.</span><span class="sxs-lookup"><span data-stu-id="7789f-122">Data provided by the connector is automatically posted to the channel.</span></span>

    ![Captura de pantalla de la interfaz de Teams donde se ve una conversación en un canal.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a><span data-ttu-id="7789f-124">Desarrollar conectores personalizados</span><span class="sxs-lookup"><span data-stu-id="7789f-124">Develop custom connectors</span></span>
-----------------------------

<span data-ttu-id="7789f-125">Es muy fácil desarrollar conectores personalizados que puedan integrarse con las aplicaciones de línea de negocio (LOB).</span><span class="sxs-lookup"><span data-stu-id="7789f-125">It is very easy to develop custom connectors that can integrate with your line-of-business (LOB) applications.</span></span> <span data-ttu-id="7789f-126">Puede usar el conector de enlace de **entrada de correo entrante** integrado para crear un extremo de un canal que extrae datos de cualquier aplicación que use métodos http post.</span><span class="sxs-lookup"><span data-stu-id="7789f-126">You can use the built-in **Incoming Webhook** connector to create an endpoint for a channel that pulls data from any application using HTTP post methods.</span></span>

1. <span data-ttu-id="7789f-127">Agregue **webhook entrante** como lo haría con cualquier otro conector.</span><span class="sxs-lookup"><span data-stu-id="7789f-127">Add the **Incoming Webhook** like any other connector.</span></span>

    ![Captura de pantalla de la opción para agregar el conector de webhook entrante.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2. <span data-ttu-id="7789f-129">Para crear un webhook, especifique un **nombre**, actualice la imagen de webhook y haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="7789f-129">To create a Webhook, specify a **name**, update the Webhook image, if necessary, and click **Create**.</span></span>

    ![Captura de pantalla de la página de configuración del conector de entrada del Web entrante.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3. <span data-ttu-id="7789f-131">Las aplicaciones que insertan datos en este canal requieren la dirección URL del conector para webhook.</span><span class="sxs-lookup"><span data-stu-id="7789f-131">Applications that push data to this channel require the Webhook connector URL.</span></span> <span data-ttu-id="7789f-132">Se crea una dirección URL única al crear el webhook.</span><span class="sxs-lookup"><span data-stu-id="7789f-132">A unique URL is created when you create the Webhook.</span></span> <span data-ttu-id="7789f-133">Comparta esta dirección URL con sus desarrolladores para que puedan configurar sus aplicaciones para insertar datos, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="7789f-133">Share this URL with your developers so that they can configure their applications to push data, as needed.</span></span>

    ![Captura de pantalla de la URL exclusiva del webhook.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4. <span data-ttu-id="7789f-135">Cuando una aplicación externa inserta datos en un conector, el mensaje se muestra en la lista de conversaciones del canal como un mensaje especial denominado mensaje de **tarjeta de conector**.</span><span class="sxs-lookup"><span data-stu-id="7789f-135">When an external application pushes data to a connector, the message is shown in the channel conversation list as a special message called a **Connector Card** message.</span></span>

    ![Captura de pantalla de la interfaz de Teams donde se ve un mensaje de la tarjeta de conector.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

     <span data-ttu-id="7789f-137">Los desarrolladores pueden configurar sus aplicaciones para crear estas tarjetas enviando una solicitud HTTP con una carga de JSON simple a la dirección webhook de un equipo, que es una dirección URL única de ese extremo proporcionado por el asistente.</span><span class="sxs-lookup"><span data-stu-id="7789f-137">Developers can configure their applications to create these cards by sending an HTTP request with a simple JSON payload to a team’s Webhook address, which is a unique URL of that endpoint provided by the wizard.</span></span> <span data-ttu-id="7789f-138">Haga que los programadores consulten [Introducción a Office 365 Connectors for Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors), en la red de programadores de Microsoft, que tiene instrucciones detalladas y ejemplos de conectores.</span><span class="sxs-lookup"><span data-stu-id="7789f-138">Have your developers refer to [Getting started with Office 365 Connectors for Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors), on the Microsoft Developer Network, which has detailed instructions and connector samples.</span></span> <span data-ttu-id="7789f-139">Otros recursos incluyen [las aplicaciones Connect para los grupos de Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) y el [centro de desarrollo de Office (Microsoft Teams)](https://go.microsoft.com/fwlink/?linkid=855784).</span><span class="sxs-lookup"><span data-stu-id="7789f-139">Other resources include [Connect apps to your groups in Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) and the [Office Dev Center – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784).</span></span>
