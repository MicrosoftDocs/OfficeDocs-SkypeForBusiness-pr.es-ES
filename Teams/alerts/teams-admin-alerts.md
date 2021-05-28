---
title: Microsoft Teams Supervisión y alertas
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
description: Obtenga información sobre las Teams de alertas y notificaciones disponibles en el centro Microsoft Teams administración.
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: c99cc9af08fb1353e0c94e6f8bf156df04327d49
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684614"
---
# <a name="microsoft-teams-monitoring-and-alerting"></a><span data-ttu-id="bed53-103">Microsoft Teams y alertas</span><span class="sxs-lookup"><span data-stu-id="bed53-103">Microsoft Teams monitoring and alerting</span></span>

<span data-ttu-id="bed53-104">Las nuevas capacidades de supervisión y alertas para Microsoft Teams están disponibles en el centro Teams administración.</span><span class="sxs-lookup"><span data-stu-id="bed53-104">New monitoring and alerting capabilities for Microsoft Teams are available in the Teams admin center.</span></span> <span data-ttu-id="bed53-105">Use diferentes conjuntos de reglas disponibles en la sección Notificaciones **& alertas** en el Centro de administración de Teams para supervisar Teams y recibir alertas.</span><span class="sxs-lookup"><span data-stu-id="bed53-105">Use different sets of rules available under the **Notifications & alerts** section in the Teams admin center to monitor Teams capabilities and receive alerts.</span></span> <span data-ttu-id="bed53-106">Por ejemplo, puede supervisar activamente el estado de Teams dispositivos como teléfonos IP, barras de colaboración y otros si se desconectan inesperadamente.</span><span class="sxs-lookup"><span data-stu-id="bed53-106">For example, you can actively monitor the health of Teams devices such as IP Phones, collaboration bars, and others if they unexpectedly go offline.</span></span>  

<span data-ttu-id="bed53-107">Su organización puede usar Teams y alertas para realizar los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="bed53-107">Your organization can use Teams monitoring and alerting to do the following items:</span></span>

- <span data-ttu-id="bed53-108">Administrar automáticamente Teams funcionalidades</span><span class="sxs-lookup"><span data-stu-id="bed53-108">Automatically manage Teams capabilities</span></span>
- <span data-ttu-id="bed53-109">Se le avisará si muestran algo inesperado.</span><span class="sxs-lookup"><span data-stu-id="bed53-109">Be alerted if they show something unexpected.</span></span>
- <span data-ttu-id="bed53-110">Realice acciones correctivas para que las cosas vuelvan a estar en marcha.</span><span class="sxs-lookup"><span data-stu-id="bed53-110">Take corrective actions to get things back on-track.</span></span>

## <a name="how-to-manage-monitoring-and-alerting"></a><span data-ttu-id="bed53-111">Cómo administrar la supervisión y las alertas</span><span class="sxs-lookup"><span data-stu-id="bed53-111">How to manage monitoring and alerting</span></span>

 <span data-ttu-id="bed53-112">Debe ser administrador global en Microsoft 365 o administrador Teams servicio para configurar reglas de alertas.</span><span class="sxs-lookup"><span data-stu-id="bed53-112">You must be a global admin in Microsoft 365 or a Teams service admin to configure alerting rules.</span></span> <span data-ttu-id="bed53-113">Vea [Usar Teams de](../using-admin-roles.md) administrador para administrar Teams para obtener más información sobre Teams de administrador y qué informes pueden tener acceso a cada rol de administrador.</span><span class="sxs-lookup"><span data-stu-id="bed53-113">See [Use Teams administrator roles to manage Teams](../using-admin-roles.md) to learn more about Teams admin roles and which reports each admin role can access.</span></span>

1. <span data-ttu-id="bed53-114">Inicie la sesión en el Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="bed53-114">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="bed53-115">En el panel de navegación izquierdo, seleccione **Notificaciones & alertas.**</span><span class="sxs-lookup"><span data-stu-id="bed53-115">From the left navigation, select **Notifications & alerts**.</span></span>
3. <span data-ttu-id="bed53-116">Elija la regla que desea configurar en **Reglas.**</span><span class="sxs-lookup"><span data-stu-id="bed53-116">Choose the rule you want to configure from **Rules**.</span></span>

## <a name="teams-monitoring-rules-reference"></a><span data-ttu-id="bed53-117">Teams de reglas de supervisión</span><span class="sxs-lookup"><span data-stu-id="bed53-117">Teams monitoring rules reference</span></span>

<span data-ttu-id="bed53-118">Seguimos agregando y mejorando la experiencia Teams supervisión mediante la adición de varias funcionalidades de supervisión y funcionalidades de configuración.</span><span class="sxs-lookup"><span data-stu-id="bed53-118">We continue adding to and improving the Teams monitoring experience by adding various monitoring capabilities and configuration functionalities.</span></span> <span data-ttu-id="bed53-119">Esta es una lista de las Teams de supervisión disponibles actualmente en el centro Teams administración.</span><span class="sxs-lookup"><span data-stu-id="bed53-119">Here's a list of the Teams monitoring rules currently available in the Teams admin center.</span></span>


|<span data-ttu-id="bed53-120">Regla</span><span class="sxs-lookup"><span data-stu-id="bed53-120">Rule</span></span>  |<span data-ttu-id="bed53-121">Capacidad de supervisión</span><span class="sxs-lookup"><span data-stu-id="bed53-121">Monitoring capability</span></span>|<span data-ttu-id="bed53-122">¿Qué se supervisa?</span><span class="sxs-lookup"><span data-stu-id="bed53-122">What's monitored?</span></span> |
|---------|---------|---------|
|[<span data-ttu-id="bed53-123">Estado del estado del dispositivo</span><span class="sxs-lookup"><span data-stu-id="bed53-123">Device health status</span></span>](device-health-status.md)  |<span data-ttu-id="bed53-124">Teams Dispositivos</span><span class="sxs-lookup"><span data-stu-id="bed53-124">Teams Devices</span></span> | <span data-ttu-id="bed53-125">Pro de forma activa Teams dispositivos si se desconectan.</span><span class="sxs-lookup"><span data-stu-id="bed53-125">Pro-actively monitor Teams devices if they go offline.</span></span>|