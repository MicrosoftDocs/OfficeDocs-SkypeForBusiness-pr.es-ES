---
title: Integración de Teams con Microsoft Power Platform
author: cichur
ms.author: v-cichur
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
description: Obtenga información sobre la integración de Teams con las herramientas de Microsoft Power Platform, como Power BI, Power apps, Power Automate y Power Virtual Agents.
ms.openlocfilehash: c6442cd654dd8da6e26de048d50b7c80ef95cf26
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111046"
---
# <a name="teams-integration-with-microsoft-power-platform"></a><span data-ttu-id="39484-103">Integración de Teams con Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="39484-103">Teams integration with Microsoft Power Platform</span></span>

<span data-ttu-id="39484-104">Microsoft Power Platform ayuda a los usuarios a acelerar su desarrollo con herramientas de código bajo para analizar datos con **Power BI,** crear aplicaciones personalizadas con **Power Apps,** automatizar procesos con **Power Automate** y crear bots inteligentes con Power **Virtual Agents** más rápido que nunca.</span><span class="sxs-lookup"><span data-stu-id="39484-104">Microsoft Power Platform helps users accelerate their development with low-code tools to analyze data using **Power BI**, build custom apps using **Power Apps**, automate processes using **Power Automate**, and create intelligent bots using **Power Virtual Agents** more quickly than ever.</span></span> <span data-ttu-id="39484-105">Con el cambio al trabajo remoto e híbrido, Microsoft Teams ha permitido que personas de todo el mundo puedan seguir crear, colaborar y comunicarse.</span><span class="sxs-lookup"><span data-stu-id="39484-105">With the shift to remote and hybrid work, Microsoft Teams has enabled people around the world to continue to create, collaborate, and communicate.</span></span> <span data-ttu-id="39484-106">Con más de 75 millones de usuarios activos diarios, Teams es la manera en que los usuarios realizan el trabajo.</span><span class="sxs-lookup"><span data-stu-id="39484-106">With more than 75 million daily active users, Teams is how people are getting work done.</span></span>

:::image type="content" source="media/teams-power-platform-integration.png" alt-text="Imagen que resume Teams y Microsoft Power Platform":::

<span data-ttu-id="39484-108">Microsoft Power Platform ofrece muchas capacidades de integración con Teams, donde puede insertar informes de **Power BI** en el área de trabajo de Teams, insertar aplicaciones creadas con **Power Apps** como pestaña o aplicación personal, desencadenar un flujo de **Power Automate** desde cualquier mensaje o usar tarjetas adaptables, y agregar el bot creado con Agentes virtuales de **Power** a Teams para que otros miembros de su organización interactúen con ellos.</span><span class="sxs-lookup"><span data-stu-id="39484-108">Microsoft Power Platform provides many integration capabilities with Teams where you can embed **Power BI** reports in the Teams workspace, embed apps created using **Power Apps** as a tab or personal app, trigger a **Power Automate** flow from any message or use adaptive cards, and add your bot created using **Power Virtual Agents** to Teams for other members of your organization to interact with.</span></span>

<span data-ttu-id="39484-109">A partir de septiembre de 2020, la integración con Microsoft Power Platform ha mejorado para permitir a los usuarios hacer lo siguiente sin salir nunca de *la interfaz de Teams:*</span><span class="sxs-lookup"><span data-stu-id="39484-109">Starting September 2020, integration with Microsoft Power Platform has improved to let users do the following *without ever leaving the Teams interface*:</span></span>

- <span data-ttu-id="39484-110">Cree y comparta paneles, informes y aplicaciones con **Power BI** para tomar decisiones basadas en datos.</span><span class="sxs-lookup"><span data-stu-id="39484-110">Create and share dashboards, reports, and apps using **Power BI** to make data-driven decisions.</span></span>
- <span data-ttu-id="39484-111">Cree y comparta aplicaciones diseñadas específicamente con un estudio integrado de **Power Apps** conectándose a los datos empresariales almacenados en la nueva plataforma de datos subyacente (Microsoft Dataverse para Teams), Microsoft 365 o en otros orígenes de datos a través de conectores.</span><span class="sxs-lookup"><span data-stu-id="39484-111">Create and share low-code, purpose-built apps using an integrated **Power Apps** studio by connecting to your business data stored either in the new underlying data platform (Microsoft Dataverse for Teams), Microsoft 365, or in other data sources through connectors.</span></span>
- <span data-ttu-id="39484-112">Cree flujos de trabajo automatizados entre sus aplicaciones y servicios para sincronizar archivos, recibir notificaciones, recopilar datos y mucho más con **Power Automate.**</span><span class="sxs-lookup"><span data-stu-id="39484-112">Create automated workflows between your apps and services to synchronize files, get notifications, collect data, and more using **Power Automate**.</span></span>
- <span data-ttu-id="39484-113">Cree bots con una interfaz gráfica guiada sin código con **Power Virtual Agents** para crear fácilmente asistentes digitales en Teams y que estén disponibles para sus compañeros con los que chatear.</span><span class="sxs-lookup"><span data-stu-id="39484-113">Build bots using a guided, no-code graphical interface using **Power Virtual Agents** to easily create digital assistants within Teams and make them available to your colleagues to chat with.</span></span>

<span data-ttu-id="39484-114">Las nuevas capacidades para crear aplicaciones, bots y flujos de trabajo están con el respaldo de la nueva plataforma de datos integrada y con poco código para Teams, [Dataverse para Teams,](/powerapps/teams/overview-data-platform)que proporciona almacenamiento de datos relacional, tipos de datos enriquecidos, gobierno de nivel empresarial e implementación de soluciones con un solo clic.</span><span class="sxs-lookup"><span data-stu-id="39484-114">The new capabilities to create apps, bots, and workflows are backed by the new built-in, low-code data platform for Teams, [Dataverse for Teams](/powerapps/teams/overview-data-platform), which provides relational data storage, rich data types, enterprise grade governance, and one-click solution deployment.</span></span> <span data-ttu-id="39484-115">Dataverse para Teams se basa en Microsoft [Dataverse.](/powerapps/maker/common-data-service/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="39484-115">Dataverse for Teams is built on top of [Microsoft Dataverse](/powerapps/maker/common-data-service/data-platform-intro).</span></span> <span data-ttu-id="39484-116">Con Dataverse para Teams, los usuarios de Teams pueden buscar e instalar soluciones personalizadas listas para usar desde la tienda de aplicaciones de Teams que muestran escenarios comunes en todos los sectores.</span><span class="sxs-lookup"><span data-stu-id="39484-116">With Dataverse for Teams, Teams users can find and install custom, ready-to-use solutions from the Teams app store that showcase common scenarios across industries.</span></span> <span data-ttu-id="39484-117">Puede personalizar y ampliar estas soluciones personalizadas para adaptarlas a la personalización de marca y a los requisitos de su organización.</span><span class="sxs-lookup"><span data-stu-id="39484-117">You can customize and extend these custom solutions to adapt to your organization's branding and requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="39484-118">Licencias</span><span class="sxs-lookup"><span data-stu-id="39484-118">Licensing</span></span>

<span data-ttu-id="39484-119">Las nuevas funcionalidades están disponibles para las suscripciones selectas de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="39484-119">The new capabilities are available to the select Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="39484-120">Para obtener más información sobre los requisitos de licencias para Power Apps, Power Automate, Power Virtual Agents y Dataverse para Teams, vea [Licencias.](/power-platform/admin/about-teams-environment)</span><span class="sxs-lookup"><span data-stu-id="39484-120">For more information about licensing requirements for Power Apps, Power Automate, Power Virtual Agents, and Dataverse for Teams, see [Licensing](/power-platform/admin/about-teams-environment).</span></span>
- <span data-ttu-id="39484-121">Para obtener más información sobre los requisitos de licencia para Power BI, vea [Requisitos.](/power-bi/collaborate-share/service-collaborate-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="39484-121">For more information about licensing requirements for Power BI, see [Requirements](/power-bi/collaborate-share/service-collaborate-microsoft-teams).</span></span>
 
## <a name="how-do-i-get-started"></a><span data-ttu-id="39484-122">¿Cómo puedo empezar?</span><span class="sxs-lookup"><span data-stu-id="39484-122">How do I get started?</span></span>

- [<span data-ttu-id="39484-123">Power BI y Teams</span><span class="sxs-lookup"><span data-stu-id="39484-123">Power BI and Teams</span></span>](/power-bi/collaborate-share/service-collaborate-microsoft-teams)
- [<span data-ttu-id="39484-124">Power Apps y Teams</span><span class="sxs-lookup"><span data-stu-id="39484-124">Power Apps and Teams</span></span>](/powerapps/teams/overview)
- [<span data-ttu-id="39484-125">Power Automate y Teams</span><span class="sxs-lookup"><span data-stu-id="39484-125">Power Automate and Teams</span></span>](/power-automate/teams/overview)
- [<span data-ttu-id="39484-126">Power Virtual Agents and Teams</span><span class="sxs-lookup"><span data-stu-id="39484-126">Power Virtual Agents and Teams</span></span>](/power-virtual-agents/teams/fundamentals-what-is-power-virtual-agents-teams)