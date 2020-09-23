---
title: Integración de equipos con Microsoft Power Platform
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: kvivek
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Obtenga más información sobre la integración de Teams con las herramientas de Power Platform de Microsoft, como Power BI, Power Apps, Power Powers y los agentes virtuales de Power.
ms.openlocfilehash: 2dfcf0dffec420e70d8f90c669bb64d2e9236c3e
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48204006"
---
# <a name="teams-integration-with-microsoft-power-platform"></a><span data-ttu-id="f05bc-103">Integración de equipos con Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="f05bc-103">Teams integration with Microsoft Power Platform</span></span>

<span data-ttu-id="f05bc-104">Microsoft Power Platform ayuda a los usuarios a acelerar su desarrollo con herramientas de bajo código para analizar datos con **Power BI**, crear aplicaciones personalizadas con **Power apps**, automatizar procesos mediante la **automatización de energía**y crear bots inteligentes **con más rapidez** que nunca.</span><span class="sxs-lookup"><span data-stu-id="f05bc-104">Microsoft Power Platform helps users accelerate their development with low-code tools to analyze data using **Power BI**, build custom apps using **Power Apps**, automate processes using **Power Automate**, and create intelligent bots using **Power Virtual Agents** more quickly than ever.</span></span> <span data-ttu-id="f05bc-105">Con el cambio en el trabajo híbrido y remoto, Microsoft Teams ha habilitado a personas de todo el mundo para que puedan continuar con la creación, la colaboración y la comunicación.</span><span class="sxs-lookup"><span data-stu-id="f05bc-105">With the shift to remote and hybrid work, Microsoft Teams has enabled people around the world to continue to create, collaborate, and communicate.</span></span> <span data-ttu-id="f05bc-106">Con más de 75 millones usuarios activos diarios, Teams es la manera en que los usuarios hacen el trabajo.</span><span class="sxs-lookup"><span data-stu-id="f05bc-106">With more than 75 million daily active users, Teams is how people are getting work done.</span></span>

:::image type="content" source="media/teams-power-platform-integration.png" alt-text="Resumen de la imagen de Teams y Microsoft Power Platform":::

<span data-ttu-id="f05bc-108">Microsoft Power Platform proporciona muchas capacidades de integración con equipos en los que puede insertar informes de **Power BI** en el área de trabajo de Teams, insertar aplicaciones creadas con **Power apps** como una pestaña o una aplicación personal, desencadenar un flujo de **automatización** desde cualquier mensaje o usar tarjetas adaptativas, y agregar un bot creado con **agentes de Power virtual** a equipos para que otros miembros de su organización puedan interactuar.</span><span class="sxs-lookup"><span data-stu-id="f05bc-108">Microsoft Power Platform provides many integration capabilities with Teams where you can embed **Power BI** reports in the Teams workspace, embed apps created using **Power Apps** as a tab or personal app, trigger a **Power Automate** flow from any message or use adaptive cards, and add your bot created using **Power Virtual Agents** to Teams for other members of your organization to interact with.</span></span>

<span data-ttu-id="f05bc-109">A partir del 2020 de septiembre, la integración con Microsoft Power Platform ha mejorado para permitir que los usuarios hagan lo siguiente *sin salir de la interfaz de Teams*:</span><span class="sxs-lookup"><span data-stu-id="f05bc-109">Starting September 2020, integration with Microsoft Power Platform has improved to let users do the following *without ever leaving the Teams interface*:</span></span>

- <span data-ttu-id="f05bc-110">Cree y comparta paneles, informes y aplicaciones con **Power BI** para tomar decisiones controladas por datos.</span><span class="sxs-lookup"><span data-stu-id="f05bc-110">Create and share dashboards, reports, and apps using **Power BI** to make data-driven decisions.</span></span>
- <span data-ttu-id="f05bc-111">Cree y comparta aplicaciones de bajo código con fines creados con un estudio de **Power apps** integrado conectándose a los datos profesionales almacenados en la nueva plataforma de datos subyacente (Project Oakdale), Microsoft 365 o en otros orígenes de datos a través de conectores.</span><span class="sxs-lookup"><span data-stu-id="f05bc-111">Create and share low-code, purpose-built apps using an integrated **Power Apps** studio by connecting to your business data stored either in the new underlying data platform (Project Oakdale), Microsoft 365, or in other data sources through connectors.</span></span>
- <span data-ttu-id="f05bc-112">Cree flujos de trabajo automatizados entre sus aplicaciones y servicios para sincronizar archivos, recibir notificaciones, recopilar datos y mucho más con **Power Automate**.</span><span class="sxs-lookup"><span data-stu-id="f05bc-112">Create automated workflows between your apps and services to synchronize files, get notifications, collect data, and more using **Power Automate**.</span></span>
- <span data-ttu-id="f05bc-113">Cree bots con una interfaz gráfica guiada y sin código usando **Power virtual Agents** para crear fácilmente asistentes digitales dentro de equipos y hacer que estén disponibles para que sus colegas puedan conversar con ellos.</span><span class="sxs-lookup"><span data-stu-id="f05bc-113">Build bots using a guided, no-code graphical interface using **Power Virtual Agents** to easily create digital assistants within Teams and make them available to your colleagues to chat with.</span></span>

<span data-ttu-id="f05bc-114">Las nuevas capacidades de creación de aplicaciones, bots y flujos de trabajo están respaldadas por la nueva plataforma de datos integrada y de bajo código para Teams, [Project Oakdale](https://go.microsoft.com/fwlink/?linkid=2143541), que proporciona almacenamiento de datos relacionales, tipos de datos enriquecidos, gobierno de nivel empresarial y la implementación de soluciones con un solo clic.</span><span class="sxs-lookup"><span data-stu-id="f05bc-114">The new capabilities to create apps, bots, and workflows are backed by the new built-in, low-code data platform for Teams, [Project Oakdale](https://go.microsoft.com/fwlink/?linkid=2143541), which provides relational data storage, rich data types, enterprise grade governance, and one-click solution deployment.</span></span> <span data-ttu-id="f05bc-115">Project Oakdale está basado en el [servicio de datos común](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span><span class="sxs-lookup"><span data-stu-id="f05bc-115">Project Oakdale is built on top of [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span> <span data-ttu-id="f05bc-116">Con Project Oakdale, los usuarios de Teams pueden buscar e instalar soluciones personalizadas y listas para usar desde la tienda de aplicaciones de teams que exhibe escenarios comunes en todas las industrias.</span><span class="sxs-lookup"><span data-stu-id="f05bc-116">With Project Oakdale, Teams users can find and install custom, ready-to-use solutions from the Teams app store that showcase common scenarios across industries.</span></span> <span data-ttu-id="f05bc-117">Puede personalizar y ampliar estas soluciones personalizadas para adaptarse a la marca y los requisitos de la organización.</span><span class="sxs-lookup"><span data-stu-id="f05bc-117">You can customize and extend these custom solutions to adapt to your organization's branding and requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="f05bc-118">Licencias</span><span class="sxs-lookup"><span data-stu-id="f05bc-118">Licensing</span></span>

<span data-ttu-id="f05bc-119">Las nuevas capacidades están disponibles para las suscripciones a Microsoft 365 seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="f05bc-119">The new capabilities are available to the select Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="f05bc-120">Para obtener más información sobre los requisitos de licencia para Power Apps, Power automatization, los agentes virtuales de Power y Project Oakdale, consulte [Licensing](https://go.microsoft.com/fwlink/?linkid=2143647).</span><span class="sxs-lookup"><span data-stu-id="f05bc-120">For more information about licensing requirements for Power Apps, Power Automate, Power Virtual Agents, and Project Oakdale, see [Licensing](https://go.microsoft.com/fwlink/?linkid=2143647).</span></span>
- <span data-ttu-id="f05bc-121">Para obtener más información sobre los requisitos de licencia para Power BI, consulte [requisitos](https://go.microsoft.com/fwlink/?linkid=2143490).</span><span class="sxs-lookup"><span data-stu-id="f05bc-121">For more information about licensing requirements for Power BI, see [Requirements](https://go.microsoft.com/fwlink/?linkid=2143490).</span></span>
 
## <a name="how-do-i-get-started"></a><span data-ttu-id="f05bc-122">¿Cómo puedo comenzar?</span><span class="sxs-lookup"><span data-stu-id="f05bc-122">How do I get started?</span></span>

- [<span data-ttu-id="f05bc-123">Power BI y Teams</span><span class="sxs-lookup"><span data-stu-id="f05bc-123">Power BI and Teams</span></span>](https://aka.ms/pbi-teams-docs)
- [<span data-ttu-id="f05bc-124">Power apps y Teams</span><span class="sxs-lookup"><span data-stu-id="f05bc-124">Power Apps and Teams</span></span>](https://aka.ms/pa-teams-docs)
- [<span data-ttu-id="f05bc-125">Automatización y equipos de Power</span><span class="sxs-lookup"><span data-stu-id="f05bc-125">Power Automate and Teams</span></span>](https://aka.ms/pauto-teams-docs)
- [<span data-ttu-id="f05bc-126">Agentes y equipos de Power virtual</span><span class="sxs-lookup"><span data-stu-id="f05bc-126">Power Virtual Agents and Teams</span></span>](https://aka.ms/pva-teams-docs)
