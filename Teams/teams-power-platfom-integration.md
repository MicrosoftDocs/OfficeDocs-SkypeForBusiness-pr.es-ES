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
description: Obtenga información sobre la integración de Teams con herramientas de la plataforma Power Platform de Microsoft, como Power BI, Power Apps, Power Automate y Power Virtual Agents.
ms.openlocfilehash: 0fb05596fb5fa87ab4e209325cc35b7a3eae56d9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804570"
---
# <a name="teams-integration-with-microsoft-power-platform"></a><span data-ttu-id="b0ee1-103">Integración de Teams con Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="b0ee1-103">Teams integration with Microsoft Power Platform</span></span>

<span data-ttu-id="b0ee1-104">Microsoft Power Platform ayuda a los usuarios a acelerar su desarrollo con herramientas de código bajo para analizar datos con **Power BI,** crear aplicaciones personalizadas con **Power Apps,** automatizar procesos con **Power Automate** y crear bots inteligentes con Agentes virtuales de **Power** más rápidamente que nunca.</span><span class="sxs-lookup"><span data-stu-id="b0ee1-104">Microsoft Power Platform helps users accelerate their development with low-code tools to analyze data using **Power BI**, build custom apps using **Power Apps**, automate processes using **Power Automate**, and create intelligent bots using **Power Virtual Agents** more quickly than ever.</span></span> <span data-ttu-id="b0ee1-105">Con el cambio al trabajo remoto e híbrido, Microsoft Teams ha habilitado a los usuarios de todo el mundo para que puedan seguir crear, colaborar y comunicarse.</span><span class="sxs-lookup"><span data-stu-id="b0ee1-105">With the shift to remote and hybrid work, Microsoft Teams has enabled people around the world to continue to create, collaborate, and communicate.</span></span> <span data-ttu-id="b0ee1-106">Con más de 75 millones de usuarios activos diarios, Teams es la manera en que las personas están trabajando.</span><span class="sxs-lookup"><span data-stu-id="b0ee1-106">With more than 75 million daily active users, Teams is how people are getting work done.</span></span>

:::image type="content" source="media/teams-power-platform-integration.png" alt-text="Imagen que resume Teams y Microsoft Power Platform":::

<span data-ttu-id="b0ee1-108">La Plataforma de Microsoft Power proporciona muchas capacidades de integración con Teams, donde puede insertar informes de **Power BI** en el área de trabajo de Teams, incrustar aplicaciones creadas con **Power Apps** como pestaña o aplicación personal, desencadenar un flujo de Power **Automate** desde cualquier mensaje o usar tarjetas adaptables, y agregar su bot creado con Power **Virtual Agents** a Teams para que otros miembros de la organización interactúen con él.</span><span class="sxs-lookup"><span data-stu-id="b0ee1-108">Microsoft Power Platform provides many integration capabilities with Teams where you can embed **Power BI** reports in the Teams workspace, embed apps created using **Power Apps** as a tab or personal app, trigger a **Power Automate** flow from any message or use adaptive cards, and add your bot created using **Power Virtual Agents** to Teams for other members of your organization to interact with.</span></span>

<span data-ttu-id="b0ee1-109">A partir de septiembre de 2020, se ha mejorado la integración con Microsoft Power Platform para permitir a los usuarios hacer lo siguiente sin *salir de la interfaz de Teams:*</span><span class="sxs-lookup"><span data-stu-id="b0ee1-109">Starting September 2020, integration with Microsoft Power Platform has improved to let users do the following *without ever leaving the Teams interface*:</span></span>

- <span data-ttu-id="b0ee1-110">Cree y comparta paneles, informes y aplicaciones con **Power BI** para tomar decisiones controladas por datos.</span><span class="sxs-lookup"><span data-stu-id="b0ee1-110">Create and share dashboards, reports, and apps using **Power BI** to make data-driven decisions.</span></span>
- <span data-ttu-id="b0ee1-111">Cree y comparta aplicaciones de bajo código creadas para propósitos con un estudio de **Power Apps** integrado mediante la conexión a los datos empresariales almacenados en la nueva plataforma de datos subyacente (Microsoft Dataverse para Teams), Microsoft 365 o en otros orígenes de datos a través de conectores.</span><span class="sxs-lookup"><span data-stu-id="b0ee1-111">Create and share low-code, purpose-built apps using an integrated **Power Apps** studio by connecting to your business data stored either in the new underlying data platform (Microsoft Dataverse for Teams), Microsoft 365, or in other data sources through connectors.</span></span>
- <span data-ttu-id="b0ee1-112">Cree flujos de trabajo automatizados entre las aplicaciones y los servicios para sincronizar archivos, recibir notificaciones, recopilar datos y mucho más **con Power Automate.**</span><span class="sxs-lookup"><span data-stu-id="b0ee1-112">Create automated workflows between your apps and services to synchronize files, get notifications, collect data, and more using **Power Automate**.</span></span>
- <span data-ttu-id="b0ee1-113">Cree bots mediante una interfaz gráfica guiado sin código usando **Power Virtual Agents** para crear fácilmente asistentes digitales en Teams y hacer que estén disponibles para que sus compañeros puedan chatear con ellos.</span><span class="sxs-lookup"><span data-stu-id="b0ee1-113">Build bots using a guided, no-code graphical interface using **Power Virtual Agents** to easily create digital assistants within Teams and make them available to your colleagues to chat with.</span></span>

<span data-ttu-id="b0ee1-114">Las nuevas funcionalidades para crear aplicaciones, bots y flujos de trabajo están copia de seguridad con la nueva plataforma de datos integrada de bajo código para Teams, [Dataverse para Teams,](https://go.microsoft.com/fwlink/?linkid=2143541)que proporciona almacenamiento de datos relacional, tipos de datos enriquecidos, gobierno de nivel empresarial e implementación de soluciones de un solo clic.</span><span class="sxs-lookup"><span data-stu-id="b0ee1-114">The new capabilities to create apps, bots, and workflows are backed by the new built-in, low-code data platform for Teams, [Dataverse for Teams](https://go.microsoft.com/fwlink/?linkid=2143541), which provides relational data storage, rich data types, enterprise grade governance, and one-click solution deployment.</span></span> <span data-ttu-id="b0ee1-115">Dataverse para Teams se basa sobre Microsoft [Dataverse.](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="b0ee1-115">Dataverse for Teams is built on top of [Microsoft Dataverse](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span> <span data-ttu-id="b0ee1-116">Con Dataverse para Teams, los usuarios de Teams pueden buscar e instalar soluciones personalizadas listas para usar desde la tienda de aplicaciones de Teams que presentan escenarios comunes en diversos sectores.</span><span class="sxs-lookup"><span data-stu-id="b0ee1-116">With Dataverse for Teams, Teams users can find and install custom, ready-to-use solutions from the Teams app store that showcase common scenarios across industries.</span></span> <span data-ttu-id="b0ee1-117">Puede personalizar y ampliar estas soluciones personalizadas para adaptarlas a los requisitos y la personalización de marca de su organización.</span><span class="sxs-lookup"><span data-stu-id="b0ee1-117">You can customize and extend these custom solutions to adapt to your organization's branding and requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="b0ee1-118">Licencias</span><span class="sxs-lookup"><span data-stu-id="b0ee1-118">Licensing</span></span>

<span data-ttu-id="b0ee1-119">Las nuevas funcionalidades están disponibles para las suscripciones a Microsoft 365 que seleccione.</span><span class="sxs-lookup"><span data-stu-id="b0ee1-119">The new capabilities are available to the select Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="b0ee1-120">Para obtener más información sobre los requisitos de licencia para Power Apps, Power Automate, Power Virtual Agents y Dataverse para Teams, vea [Licencias.](https://go.microsoft.com/fwlink/?linkid=2143647)</span><span class="sxs-lookup"><span data-stu-id="b0ee1-120">For more information about licensing requirements for Power Apps, Power Automate, Power Virtual Agents, and Dataverse for Teams, see [Licensing](https://go.microsoft.com/fwlink/?linkid=2143647).</span></span>
- <span data-ttu-id="b0ee1-121">Para obtener más información sobre los requisitos de licencia para Power BI, vea [Requisitos.](https://go.microsoft.com/fwlink/?linkid=2143490)</span><span class="sxs-lookup"><span data-stu-id="b0ee1-121">For more information about licensing requirements for Power BI, see [Requirements](https://go.microsoft.com/fwlink/?linkid=2143490).</span></span>
 
## <a name="how-do-i-get-started"></a><span data-ttu-id="b0ee1-122">¿Cómo puedo empezar?</span><span class="sxs-lookup"><span data-stu-id="b0ee1-122">How do I get started?</span></span>

- [<span data-ttu-id="b0ee1-123">Power BI y Teams</span><span class="sxs-lookup"><span data-stu-id="b0ee1-123">Power BI and Teams</span></span>](https://aka.ms/pbi-teams-docs)
- [<span data-ttu-id="b0ee1-124">Power Apps y Teams</span><span class="sxs-lookup"><span data-stu-id="b0ee1-124">Power Apps and Teams</span></span>](https://aka.ms/pa-teams-docs)
- [<span data-ttu-id="b0ee1-125">Power Automate y Teams</span><span class="sxs-lookup"><span data-stu-id="b0ee1-125">Power Automate and Teams</span></span>](https://aka.ms/pauto-teams-docs)
- [<span data-ttu-id="b0ee1-126">Power Virtual Agents y Teams</span><span class="sxs-lookup"><span data-stu-id="b0ee1-126">Power Virtual Agents and Teams</span></span>](https://aka.ms/pva-teams-docs)
