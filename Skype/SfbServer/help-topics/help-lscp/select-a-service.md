---
title: Seleccionar un servicio
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.SelectPool
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6086162-8a41-4e75-afa3-7d1889ffdc90
description: Use el cuadro de diálogo Seleccionar un servicio para buscar servicios disponibles en su entorno. Para usar un servicio existente, haga clic en un servicio de la lista y, a continuación, haga clic en Aceptar.
ms.openlocfilehash: 06ee0217a8a495a881c9925c57e33311e4944607
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108046"
---
# <a name="select-a-service"></a><span data-ttu-id="c8937-104">Seleccionar un servicio</span><span class="sxs-lookup"><span data-stu-id="c8937-104">Select a Service</span></span>

<span data-ttu-id="c8937-105">Use el **cuadro de diálogo Seleccionar un servicio** para buscar servicios disponibles en su entorno.</span><span class="sxs-lookup"><span data-stu-id="c8937-105">Use the **Select a Service** dialog box to find services available in your environment.</span></span> <span data-ttu-id="c8937-106">Para usar un servicio existente, haga clic en un servicio de la lista y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c8937-106">To use an existing service, click a service in the list and then click **OK**.</span></span>

<span data-ttu-id="c8937-107">Para obtener información detallada sobre los diferentes procedimientos que puede realizar mediante el Panel de control de Skype Empresarial Server, vea [Manage Skype for Business Server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="c8937-107">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="c8937-108">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="c8937-108">Tasks you can perform</span></span>

<span data-ttu-id="c8937-109">Puede realizar las siguientes tareas en la **página Seleccionar un** servicio:</span><span class="sxs-lookup"><span data-stu-id="c8937-109">You can perform the following tasks on the **Select a Service** page:</span></span>

- [<span data-ttu-id="c8937-110">Configurar categorías</span><span class="sxs-lookup"><span data-stu-id="c8937-110">Configure Categories</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [<span data-ttu-id="c8937-111">Configurar complementos para salones</span><span class="sxs-lookup"><span data-stu-id="c8937-111">Configure Add-ins for Rooms</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-add-ins-for-rooms)

- [<span data-ttu-id="c8937-112">Configurar opciones de servidor de chat persistentes a nivel global o para grupos de servidores de chat persistentes</span><span class="sxs-lookup"><span data-stu-id="c8937-112">Configure Persistent Chat Server Options Globally or for Persistent Chat Server Pool</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool)

<span data-ttu-id="c8937-113">Para obtener información detallada sobre los diferentes procedimientos que puede realizar mediante el Panel de control de Skype Empresarial Server, vea [Manage Skype for Business Server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="c8937-113">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="c8937-114">Para configurar categorías para salones de chat</span><span class="sxs-lookup"><span data-stu-id="c8937-114">To configure categories for chat rooms</span></span>

<span data-ttu-id="c8937-115">En **Seleccionar un servicio,** seleccione el servicio correspondiente al grupo de servidores de chat persistente en el que debe crearse la categoría.</span><span class="sxs-lookup"><span data-stu-id="c8937-115">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="c8937-116">El servicio es el grupo de servidores de chat persistente que usa el chat persistente (cliente) para identificar a qué grupo pertenece la categoría.</span><span class="sxs-lookup"><span data-stu-id="c8937-116">The service is the Persistent Chat Server pool that the Persistent Chat (client) uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="c8937-117">Una categoría solo puede pertenecer a un grupo de servidores de chat persistente y no se puede mover a otro ni compartirse con otro grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="c8937-117">A category can belong to only one Persistent Chat Server pool, and cannot be moved to another one, or shared with another pool.</span></span>

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="c8937-118">Para configurar complementos para salas de chat</span><span class="sxs-lookup"><span data-stu-id="c8937-118">To configure add-ins for chat rooms</span></span>

<span data-ttu-id="c8937-119">En **Seleccionar un servicio,** seleccione el servicio correspondiente al grupo de servidores de chat persistente donde necesita crear el complemento.</span><span class="sxs-lookup"><span data-stu-id="c8937-119">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="c8937-120">Los complementos no se pueden mover de un grupo a otro ni compartir entre grupos distintos.</span><span class="sxs-lookup"><span data-stu-id="c8937-120">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="c8937-121">Para configurar las opciones de chat persistente para un grupo de servidores de chat persistente específico</span><span class="sxs-lookup"><span data-stu-id="c8937-121">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

<span data-ttu-id="c8937-122">En **Seleccionar un servicio,** seleccione el servicio asociado al grupo de servidores de chat persistente que se va a configurar.</span><span class="sxs-lookup"><span data-stu-id="c8937-122">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>

<span data-ttu-id="c8937-123">Para obtener más información sobre las características y capacidades del servidor de chat persistente, consulte [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) en la documentación sobre planeación.</span><span class="sxs-lookup"><span data-stu-id="c8937-123">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) in the Planning documentation.</span></span> <span data-ttu-id="c8937-124">Para obtener más información sobre cómo trabajar con configuraciones de servidor de chat persistente, consulte [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) en la documentación sobre implementación y [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) en la documentación sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="c8937-124">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in the Operations documentation.</span></span>