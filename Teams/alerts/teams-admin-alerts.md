---
title: Supervisión y alertas de Microsoft Teams
author: vaibhav
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: vapati
f1.keywords: ''
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-collaboration
description: Obtenga información sobre las capacidades de alertas y notificaciones de Teams disponibles en el Centro de administración de Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 1be3ca52d4b03cfbf82d82310148ef4c2bb7f06d
ms.sourcegitcommit: c6b630f9193d7f82f0416bd567a1de390d4b260f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819491"
---
# <a name="microsoft-teams-monitoring-and-alerting"></a><span data-ttu-id="1415a-103">Supervisión y alertas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1415a-103">Microsoft Teams monitoring and alerting</span></span>

<span data-ttu-id="1415a-104">Las nuevas capacidades de supervisión y alertas para Microsoft Teams están disponibles en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="1415a-104">New monitoring and alerting capabilities for Microsoft Teams are available in the Teams admin center.</span></span> <span data-ttu-id="1415a-105">Use diferentes conjuntos de reglas disponibles en la sección Notificaciones **& alertas** en el Centro de administración de Teams para supervisar las capacidades de Teams y recibir alertas.</span><span class="sxs-lookup"><span data-stu-id="1415a-105">Use different sets of rules available under the **Notifications & alerts** section in the Teams admin center to monitor Teams capabilities and receive alerts.</span></span> <span data-ttu-id="1415a-106">Por ejemplo, puede supervisar activamente el estado de los dispositivos de Teams, como teléfonos IP, barras de colaboración y otros si se desconectan inesperadamente.</span><span class="sxs-lookup"><span data-stu-id="1415a-106">For example, you can actively monitor the health of Teams devices such as IP Phones, collaboration bars, and others if they unexpectedly go offline.</span></span>  

<span data-ttu-id="1415a-107">Su organización puede usar la supervisión y las alertas de Teams para realizar los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="1415a-107">Your organization can use Teams monitoring and alerting to do the following items:</span></span>

- <span data-ttu-id="1415a-108">Administrar automáticamente las capacidades de Teams</span><span class="sxs-lookup"><span data-stu-id="1415a-108">Automatically manage Teams capabilities</span></span>
- <span data-ttu-id="1415a-109">Se le avisará si muestran algo inesperado.</span><span class="sxs-lookup"><span data-stu-id="1415a-109">Be alerted if they show something unexpected.</span></span>
- <span data-ttu-id="1415a-110">Realice acciones correctivas para que las cosas vuelvan a estar en marcha.</span><span class="sxs-lookup"><span data-stu-id="1415a-110">Take corrective actions to get things back on-track.</span></span>

## <a name="how-to-manage-monitoring-and-alerting"></a><span data-ttu-id="1415a-111">Cómo administrar la supervisión y las alertas</span><span class="sxs-lookup"><span data-stu-id="1415a-111">How to manage monitoring and alerting</span></span>

 <span data-ttu-id="1415a-112">Debe ser administrador global en Microsoft 365 o administrador de servicio de Teams para configurar reglas de alertas.</span><span class="sxs-lookup"><span data-stu-id="1415a-112">You must be a global admin in Microsoft 365 or a Teams service admin to configure alerting rules.</span></span> <span data-ttu-id="1415a-113">Vea [Usar roles de administrador de Teams para administrar Teams](../using-admin-roles.md) para obtener más información sobre los roles de administrador de Teams y a qué informes puede acceder cada rol de administrador.</span><span class="sxs-lookup"><span data-stu-id="1415a-113">See [Use Teams administrator roles to manage Teams](../using-admin-roles.md) to learn more about Teams admin roles and which reports each admin role can access.</span></span>

1. <span data-ttu-id="1415a-114">Inicie la sesión en el Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="1415a-114">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="1415a-115">En el panel de navegación izquierdo, seleccione **Notificaciones & alertas.**</span><span class="sxs-lookup"><span data-stu-id="1415a-115">From the left navigation, select **Notifications & alerts**.</span></span>
3. <span data-ttu-id="1415a-116">Elija la regla que desea configurar en **Reglas.**</span><span class="sxs-lookup"><span data-stu-id="1415a-116">Choose the rule you want to configure from **Rules**.</span></span>

## <a name="teams-monitoring-rules-reference"></a><span data-ttu-id="1415a-117">Referencia de reglas de supervisión de Teams</span><span class="sxs-lookup"><span data-stu-id="1415a-117">Teams monitoring rules reference</span></span>

<span data-ttu-id="1415a-118">Seguimos agregando y mejorando la experiencia de supervisión de Teams agregando varias funcionalidades de supervisión y funcionalidades de configuración.</span><span class="sxs-lookup"><span data-stu-id="1415a-118">We continue adding to and improving the Teams monitoring experience by adding various monitoring capabilities and configuration functionalities.</span></span> <span data-ttu-id="1415a-119">Esta es una lista de las reglas de supervisión de Teams disponibles actualmente en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="1415a-119">Here's a list of the Teams monitoring rules currently available in the Teams admin center.</span></span>


|<span data-ttu-id="1415a-120">Regla</span><span class="sxs-lookup"><span data-stu-id="1415a-120">Rule</span></span>  |<span data-ttu-id="1415a-121">Capacidad de supervisión</span><span class="sxs-lookup"><span data-stu-id="1415a-121">Monitoring capability</span></span>|<span data-ttu-id="1415a-122">¿Qué se supervisa?</span><span class="sxs-lookup"><span data-stu-id="1415a-122">What's monitored?</span></span> |
|---------|---------|---------|
|[<span data-ttu-id="1415a-123">Estado del estado del dispositivo</span><span class="sxs-lookup"><span data-stu-id="1415a-123">Device health status</span></span>](device-health-status.md)  |<span data-ttu-id="1415a-124">Dispositivos de Teams</span><span class="sxs-lookup"><span data-stu-id="1415a-124">Teams Devices</span></span> | <span data-ttu-id="1415a-125">Supervisar de forma activa los dispositivos de Teams si se desconectan.</span><span class="sxs-lookup"><span data-stu-id="1415a-125">Pro-actively monitor Teams devices if they go offline.</span></span>|
