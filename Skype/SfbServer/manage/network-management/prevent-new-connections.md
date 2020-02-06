---
title: Prevención de nuevas conexiones
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: c2df1c491384f8a248f70b67880511a2d496c173
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817459"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a><span data-ttu-id="7b9f9-102">Prevención de nuevas conexiones a Skype empresarial Server para el mantenimiento del servidor</span><span class="sxs-lookup"><span data-stu-id="7b9f9-102">Preventing new connections to Skype for Business Server for server maintenance</span></span>


<span data-ttu-id="7b9f9-103">Skype empresarial Server le permite poner un servidor fuera de línea (por ejemplo, para aplicar actualizaciones de software o hardware) sin ninguna pérdida de servicio para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-103">Skype for Business Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="7b9f9-104">Cuando especifica la opción de evitar nuevas conexiones o llamadas a un servidor de un grupo, deja de tomarse cualquier conexión y llamada nuevas tan pronto como implemente esta opción.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-104">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option.</span></span> <span data-ttu-id="7b9f9-105">Estas nuevas conexiones y llamadas se enrutan a través de otros servidores del grupo.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-105">These new connections and calls are routed through other servers in the pool.</span></span> <span data-ttu-id="7b9f9-106">Un servidor que impide nuevas conexiones permite que las sesiones de las conexiones existentes continúen hasta que se desordenan de forma natural.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-106">A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end.</span></span> <span data-ttu-id="7b9f9-107">Cuando haya finalizado todas las sesiones existentes, el servidor estará listo para desconectarse.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-107">When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="7b9f9-108">Cuando impide nuevas conexiones a un servidor front-end, algunas características y servicios de Skype empresarial Server dependen del equilibrio de carga de DNS para asegurarse de que funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-108">When you prevent new connections to a Front End Server, some Skype for Business Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="7b9f9-109">Si no usa el equilibrio de carga de DNS en el grupo, es posible que las conexiones a través de estos servicios no se redirijan a otros servidores durante el período en el que el servidor está impidiendo las conexiones nuevas y, por lo tanto, cuando el servidor se desconecta, algunas sesiones y llamadas pueden ser interrupción.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-109">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="7b9f9-110">Las características que dependen del equilibrio de carga de DNS para asegurarse de que esta opción funciona correctamente son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="7b9f9-110">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="7b9f9-111">Operador</span><span class="sxs-lookup"><span data-stu-id="7b9f9-111">Attendant</span></span>

  - <span data-ttu-id="7b9f9-112">Aplicación de anuncio de conferencia</span><span class="sxs-lookup"><span data-stu-id="7b9f9-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="7b9f9-113">Aplicación de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="7b9f9-113">Response Group application</span></span>

  - <span data-ttu-id="7b9f9-114">Aplicación de anuncio</span><span class="sxs-lookup"><span data-stu-id="7b9f9-114">Announcement application</span></span>

  - <span data-ttu-id="7b9f9-115">Aplicación de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="7b9f9-115">Call Park application</span></span>

<span data-ttu-id="7b9f9-116">Para obtener más información sobre el equilibrio de carga de DNS, consulte [requisitos de equilibrio de carga](../../plan-your-deployment/network-requirements/load-balancing.md).</span><span class="sxs-lookup"><span data-stu-id="7b9f9-116">For details about DNS load balancing, see [Load balancing requirements](../../plan-your-deployment/network-requirements/load-balancing.md).</span></span>

<span data-ttu-id="7b9f9-117">Además de impedir nuevas conexiones para todos los servicios en un servidor con Skype empresarial Server, también puede evitar nuevas conexiones para servicios individuales de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-117">In addition to preventing new connections for all services on a server running Skype for Business Server, you can also prevent new connections for individual Skype for Business Server services.</span></span> <span data-ttu-id="7b9f9-118">Por ejemplo, este método es útil en una situación en la que necesita aplicar una actualización de Skype empresarial Server que no requiera que se cierre todo el servidor.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-118">For example, this method is useful in a situation where you need to apply a Skype for Business Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="7b9f9-119">Tenga en cuenta que cuando impide las conexiones para un servicio, debe seleccionar un servicio tal como está agrupado y se muestra en la lista de servicios de Windows.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-119">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="7b9f9-120">Por ejemplo, el servicio front-end de Skype empresarial Server y el agente de recopilación de datos para la supervisión son servicios independientes de Skype empresarial, pero en la lista de servicios de Windows se consolidan y se muestran como el front-end de Skype empresarial Server. Service.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-120">For example, the Skype for Business Server Front-End service and the data collection agent for Monitoring are separate Skype for Business Server services, but in the Windows services list they are consolidated and shown as the Skype for Business Server Front End service.</span></span> <span data-ttu-id="7b9f9-121">Puede evitar nuevas conexiones para el servicio de front-end de Skype empresarial Server, pero no puede evitar nuevas conexiones por separado para estos dos usuarios de servicios de Skype empresarial subyacentes.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-121">You can prevent new connections for the Skype for Business Server Front End service, but you cannot prevent new connections for these two individual underlying Skype for Business Server services separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7b9f9-122">Al configurar un servidor para evitar nuevas conexiones y reiniciar el servidor, de forma predeterminada, el servidor comenzará a aceptar inmediatamente nuevas conexiones después de que se inicie.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-122">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="7b9f9-123">Para evitar esto, configure el servidor para que solo PAUSE y reanude de forma manual, antes de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-123">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a><span data-ttu-id="7b9f9-124">Para evitar nuevas conexiones a Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="7b9f9-124">To prevent new connections to Skype for Business Server</span></span>

1.  <span data-ttu-id="7b9f9-125">Inicie sesión en el equipo local como miembro del grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-125">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="7b9f9-126">Abra la consola del complemento Servicios: haga clic en **Inicio**, seleccione **todos los programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **servicios**.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-126">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="7b9f9-127">En la lista, haga doble clic en el servicio de Windows de Skype empresarial Server en el que desea evitar nuevas conexiones.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-127">In the list, double-click the Skype for Business Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="7b9f9-128">En el cuadro de diálogo Propiedades, en **Estado del servicio: iniciado**, haga clic en **pausar**.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-128">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="7b9f9-129">De forma opcional, pero recomendado, junto a **tipo de inicio**, haga clic en **manual**.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-129">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7b9f9-130">Al configurar un servidor para evitar nuevas conexiones y reiniciar el servidor, de forma predeterminada, el servidor comenzará a aceptar inmediatamente nuevas conexiones después de que se inicie.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-130">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="7b9f9-131">Para evitar esto, configure el servidor para que solo PAUSE y reanude de forma manual, antes de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="7b9f9-131">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>
