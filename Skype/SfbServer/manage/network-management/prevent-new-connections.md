---
title: Impedir nuevas conexiones
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 3f2ca560f934f5b907d05a1f768a0cadd8435f2a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823470"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a><span data-ttu-id="5c899-102">Impedir nuevas conexiones a Skype Empresarial Server para el mantenimiento del servidor</span><span class="sxs-lookup"><span data-stu-id="5c899-102">Preventing new connections to Skype for Business Server for server maintenance</span></span>


<span data-ttu-id="5c899-103">Skype Empresarial Server le permite desconectar un servidor (por ejemplo, para aplicar actualizaciones de software o hardware) sin pérdida de servicio para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="5c899-103">Skype for Business Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="5c899-p101">Si especifica la opción para prevenir nuevas conexiones o llamadas al servidor en un grupo de servidores, dicho grupo deja de atender nuevas conexiones o llamadas en el momento en que se implementa la opción. Dichas nuevas conexiones y llamadas se redirigen a los otros servidores del grupo. Un servidor que no permite las nuevas conexiones permite que continúen las sesiones de conexiones existentes hasta su final natural. Cuando terminan todas las sesiones iniciadas, el servidor está listo para ser desconectado.</span><span class="sxs-lookup"><span data-stu-id="5c899-p101">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option. These new connections and calls are routed through other servers in the pool. A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end. When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="5c899-108">Cuando impide nuevas conexiones a un servidor front-end, algunas características y servicios de Skype Empresarial Server dependen del equilibrio de carga de DNS para asegurarse de que funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="5c899-108">When you prevent new connections to a Front End Server, some Skype for Business Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="5c899-109">Si no usa el equilibrador de carga de DNS en el grupo de servidores, puede que las conexiones a través de dichos servicios no se redirijan a otros servidores durante el período en que el servidor no admite nuevas conexiones, por lo cual es posible que cuando el servidor se desconecte se vean interrumpidas algunas sesiones y llamadas.</span><span class="sxs-lookup"><span data-stu-id="5c899-109">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="5c899-110">Las características que dependen del equilibrador de carga de DNS para garantizar que esta opción funciona correctamente son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="5c899-110">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="5c899-111">Attendant</span><span class="sxs-lookup"><span data-stu-id="5c899-111">Attendant</span></span>

  - <span data-ttu-id="5c899-112">Aplicación de anuncio de conferencia</span><span class="sxs-lookup"><span data-stu-id="5c899-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="5c899-113">Aplicación de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="5c899-113">Response Group application</span></span>

  - <span data-ttu-id="5c899-114">Aplicación de anuncio</span><span class="sxs-lookup"><span data-stu-id="5c899-114">Announcement application</span></span>

  - <span data-ttu-id="5c899-115">Aplicación Estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="5c899-115">Call Park application</span></span>

<span data-ttu-id="5c899-116">Para obtener más información sobre el equilibrio de carga de DNS, consulte [Requisitos de equilibrio de carga.](../../plan-your-deployment/network-requirements/load-balancing.md)</span><span class="sxs-lookup"><span data-stu-id="5c899-116">For details about DNS load balancing, see [Load balancing requirements](../../plan-your-deployment/network-requirements/load-balancing.md).</span></span>

<span data-ttu-id="5c899-117">Además de impedir nuevas conexiones para todos los servicios en un servidor que ejecuta Skype Empresarial Server, también puede evitar nuevas conexiones para servicios individuales de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5c899-117">In addition to preventing new connections for all services on a server running Skype for Business Server, you can also prevent new connections for individual Skype for Business Server services.</span></span> <span data-ttu-id="5c899-118">Por ejemplo, este método es útil en una situación en la que necesita aplicar una actualización de Skype Empresarial Server que no requiere que se cierre todo el servidor.</span><span class="sxs-lookup"><span data-stu-id="5c899-118">For example, this method is useful in a situation where you need to apply a Skype for Business Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="5c899-119">Tenga en cuenta que cuando deje de admitir conexiones para un servicio, es necesario seleccionar un servicio según está agrupado y según se muestra en la lista de servicios de Windows.</span><span class="sxs-lookup"><span data-stu-id="5c899-119">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="5c899-120">Por ejemplo, el servicio de Front-End de Skype Empresarial Server y el agente de recopilación de datos para la supervisión son servicios independientes de Skype Empresarial Server, pero en la lista de servicios de Windows se consolidan y se muestran como el servicio front-end de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5c899-120">For example, the Skype for Business Server Front-End service and the data collection agent for Monitoring are separate Skype for Business Server services, but in the Windows services list they are consolidated and shown as the Skype for Business Server Front End service.</span></span> <span data-ttu-id="5c899-121">Puede evitar nuevas conexiones para el servicio front-end de Skype Empresarial Server, pero no puede evitar nuevas conexiones para estos dos servicios de Skype Empresarial Server subyacentes individuales por separado.</span><span class="sxs-lookup"><span data-stu-id="5c899-121">You can prevent new connections for the Skype for Business Server Front End service, but you cannot prevent new connections for these two individual underlying Skype for Business Server services separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c899-p104">Cuando se establece un servidor para impedir nuevas conexiones y después se reinicia el servidor, el servidor empezará de forma predeterminada y de inmediato a aceptar nuevas comunicaciones tras reiniciarse. Para evitar esto, establezca que el servidor solo pueda pausarse y reanudarse manualmente antes de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="5c899-p104">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a><span data-ttu-id="5c899-124">Para evitar nuevas conexiones a Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5c899-124">To prevent new connections to Skype for Business Server</span></span>

1.  <span data-ttu-id="5c899-125">Inicie sesión en el equipo local como miembro del grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="5c899-125">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="5c899-126">Abra la consola del complemento Servicios: **Haga** clic en Inicio , seleccione Todos los **programas,** seleccione Herramientas administrativas **y,** a continuación, haga clic en **Servicios.**</span><span class="sxs-lookup"><span data-stu-id="5c899-126">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="5c899-127">En la lista, haga doble clic en el servicio de Windows de Skype Empresarial Server al que desea impedir nuevas conexiones.</span><span class="sxs-lookup"><span data-stu-id="5c899-127">In the list, double-click the Skype for Business Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="5c899-128">En el cuadro de diálogo Propiedades, en **Estado del servicio: Iniciado**, haga clic en **Pausar**.</span><span class="sxs-lookup"><span data-stu-id="5c899-128">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="5c899-129">Como alternativa, y recomendación, junto a **Tipo de inicio**, haga clic en **Manual**.</span><span class="sxs-lookup"><span data-stu-id="5c899-129">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5c899-p105">Cuando se establece un servidor para impedir nuevas conexiones y después se reinicia el servidor, el servidor empezará de forma predeterminada y de inmediato a aceptar nuevas comunicaciones tras reiniciarse. Para evitar esto, establezca que el servidor solo pueda pausarse y reanudarse manualmente antes de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="5c899-p105">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>
