---
title: Aplicación Walkie Talkie en Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Cómo configurar la aplicación Walkie Talkie en Microsoft Teams, desde una perspectiva de ITAdmin.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb00501a0c795f754c927dd9ed3bd5114f61fab7
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875050"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a><span data-ttu-id="f28ff-103">Aplicación Walkie Talkie en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f28ff-103">Walkie Talkie app in Microsoft Teams</span></span>

<span data-ttu-id="f28ff-104">La aplicación Walkie Talkie de Teams proporciona comunicaciones instantáneas push-to-talk (PTT) para su equipo y ahora está disponible en Android.</span><span class="sxs-lookup"><span data-stu-id="f28ff-104">The Walkie Talkie app in Teams provides instant push-to-talk (PTT) communication for your team and is now available on Android.</span></span> <span data-ttu-id="f28ff-105">Walkie Talkie permite a los usuarios conectarse con su equipo con los mismos canales subyacentes de los que son miembros.</span><span class="sxs-lookup"><span data-stu-id="f28ff-105">Walkie Talkie allows users to connect with their team using the same underlying channels they're members of.</span></span> <span data-ttu-id="f28ff-106">Solo los usuarios que se conectan a Walkie Talkie en un canal se convierten en participantes y pueden comunicarse entre sí mediante push-to-talk, de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="f28ff-106">Only users who connect to Walkie Talkie in a channel become participants and can communicate with each other using push-to-talk, one at a time.</span></span>

<span data-ttu-id="f28ff-107">Con Walkie Talkie en Teams, los trabajadores de Frontline ahora pueden comunicarse de forma segura con una experiencia de PTT familiar sin tener que llevar radios voluminosos, y Walkie Talkie funciona en cualquier lugar con conexión a Internet móvil o WiFi.</span><span class="sxs-lookup"><span data-stu-id="f28ff-107">With Walkie Talkie in Teams, Frontline workers can now securely communicate with a familiar PTT experience without needing to carry bulky radios, and Walkie Talkie works anywhere with WiFi or cellular internet connectivity.</span></span>

## <a name="getting-started"></a><span data-ttu-id="f28ff-108">Introducción</span><span class="sxs-lookup"><span data-stu-id="f28ff-108">Getting started</span></span>

### <a name="deploying-walkie-talkie"></a><span data-ttu-id="f28ff-109">Implementar Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="f28ff-109">Deploying Walkie Talkie</span></span>

<span data-ttu-id="f28ff-110">Actualmente, Walkie Talkie no está preinstalado.</span><span class="sxs-lookup"><span data-stu-id="f28ff-110">Currently, Walkie Talkie is not pre-installed.</span></span> <span data-ttu-id="f28ff-111">Para habilitar esta característica para los usuarios de su organización, [](teams-app-setup-policies.md)debe agregar Walkie Talkie a la directiva de configuración de aplicaciones asignada a los usuarios desde el Centro de   administración de [Teams.](https://admin.teams.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="f28ff-111">To enable this feature for users in your organization, you need to add Walkie Talkie to the [App Setup Policy](teams-app-setup-policies.md) assigned to users from the [Teams Admin Center](https://admin.teams.microsoft.com/).</span></span>

<span data-ttu-id="f28ff-112">Una vez habilitado, Walkie Talkie estará disponible en la aplicación Android en un plazo de 48 horas.</span><span class="sxs-lookup"><span data-stu-id="f28ff-112">Once enabled, Walkie Talkie will become available on the Android app within 48 hours.</span></span>

### <a name="adding-walkie-talkie-to-your-app-list"></a><span data-ttu-id="f28ff-113">Agregar Walkie Talkie a la lista de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="f28ff-113">Adding Walkie Talkie to your app list</span></span>

<span data-ttu-id="f28ff-114">En el Centro de administración de Microsoft Teams, en Directivas de configuración de la aplicación **de Teams,** debería tener permitir la  >   **anclación de usuario** establecida en **On**.</span><span class="sxs-lookup"><span data-stu-id="f28ff-114">In the Microsoft Teams admin center, under **Teams app** > **Setup policies**, you should have **Allow user pinning** set to **On**.</span></span> <span data-ttu-id="f28ff-115">A continuación, en la sección Aplicaciones ancladas, haga clic **en +Agregar aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="f28ff-115">Then, under the Pinned Apps section, click **+Add Apps**.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Muestra la sección Aplicaciones ancladas y el botón Agregar aplicaciones que se va a seleccionar.":::

<span data-ttu-id="f28ff-117">En el **panel** Agregar aplicaciones ancladas que aparece  a la derecha, use el cuadro de texto Buscar para buscar Walkie Talkie.</span><span class="sxs-lookup"><span data-stu-id="f28ff-117">On the **Add pinned apps** panel that appears on the right, use the **Search** textbox to look for Walkie Talkie.</span></span> <span data-ttu-id="f28ff-118">Cuando lo tenga como resultado de  búsqueda, seleccione el botón Agregar a la derecha del nombre para agregarlo a la lista.</span><span class="sxs-lookup"><span data-stu-id="f28ff-118">When you have it as a search result, select the **Add** button to the right of the name to add it to your list.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Muestra la barra lateral Agregar aplicaciones ancladas con Walkie escrito en el panel de búsqueda y la aplicación Walkie Talkie en los resultados de búsqueda, con el botón Agregar junto a ella.":::

<span data-ttu-id="f28ff-120">La aplicación Walkie Talkie ahora debería aparecer en la lista Aplicaciones ancladas y estar disponible para su uso una vez que haga clic en **el botón** Guardar.</span><span class="sxs-lookup"><span data-stu-id="f28ff-120">The Walkie Talkie app should now appear on the Pinned Apps list, and be available for use once you click the **Save** button.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Muestra la lista de aplicaciones ancladas con la aplicación Walkie Talkie agregada y el botón Guardar debajo de la lista.":::

### <a name="network-documentation"></a><span data-ttu-id="f28ff-122">Documentación de red</span><span class="sxs-lookup"><span data-stu-id="f28ff-122">Network documentation</span></span>

<span data-ttu-id="f28ff-123">Walkie Talkie en Teams requiere conectividad a Internet y por debajo de las condiciones de red son necesarias para una experiencia óptima.</span><span class="sxs-lookup"><span data-stu-id="f28ff-123">Walkie Talkie in Teams requires Internet connectivity and below the network conditions are required for optimal experience.</span></span>

|<span data-ttu-id="f28ff-124">Métrica</span><span class="sxs-lookup"><span data-stu-id="f28ff-124">Metric</span></span> | <span data-ttu-id="f28ff-125">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="f28ff-125">Required</span></span> |
|---|---|
|<span data-ttu-id="f28ff-126">Latencia (RTT)</span><span class="sxs-lookup"><span data-stu-id="f28ff-126">Latency (RTT)</span></span> | <span data-ttu-id="f28ff-127">< 300 ms</span><span class="sxs-lookup"><span data-stu-id="f28ff-127">< 300ms</span></span> |
|<span data-ttu-id="f28ff-128">Vibración</span><span class="sxs-lookup"><span data-stu-id="f28ff-128">Jitter</span></span> |<span data-ttu-id="f28ff-129">< 30 ms</span><span class="sxs-lookup"><span data-stu-id="f28ff-129">< 30ms</span></span> |
|<span data-ttu-id="f28ff-130">Pérdida de paquetes</span><span class="sxs-lookup"><span data-stu-id="f28ff-130">Packet Loss</span></span> |<span data-ttu-id="f28ff-131">< 1%</span><span class="sxs-lookup"><span data-stu-id="f28ff-131">< 1%</span></span> |

<span data-ttu-id="f28ff-132">Como se ha indicado anteriormente, la calidad de los medios en tiempo real a través de una red IP se encuentra muy afectada por la calidad de la conectividad de red, pero especialmente por la cantidad de:</span><span class="sxs-lookup"><span data-stu-id="f28ff-132">As noted above, the quality of real-time media over an IP network is greatly impacted by the quality of the network connectivity, but especially by the amount of:</span></span>

- <span data-ttu-id="f28ff-133">**Latencia:** este es el tiempo que se tarda en obtener un paquete IP desde el punto A hasta el punto B de la red.</span><span class="sxs-lookup"><span data-stu-id="f28ff-133">**Latency** - This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="f28ff-134">Este retraso de propagación de red está esencialmente vinculado a la distancia física entre los dos puntos y la velocidad de la luz, incluida una mayor sobrecarga de los distintos enrutadores entre sí.</span><span class="sxs-lookup"><span data-stu-id="f28ff-134">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including more overhead taken by the various routers in between.</span></span> <span data-ttu-id="f28ff-135">La latencia se mide como Tiempo de ida y vuelta (RTT).</span><span class="sxs-lookup"><span data-stu-id="f28ff-135">Latency is measured as Round-trip Time (RTT).</span></span>
- <span data-ttu-id="f28ff-136">**Pérdida de paquetes:** a menudo se define como un porcentaje de paquetes que se pierden en una ventana de tiempo determinada.</span><span class="sxs-lookup"><span data-stu-id="f28ff-136">**Packet Loss** - This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="f28ff-137">La pérdida de paquetes afecta directamente a la calidad de audio, desde pequeños paquetes perdidos individuales que casi no tienen impacto, hasta pérdidas de ráfagas back-to-back que provocan un corte total de audio.</span><span class="sxs-lookup"><span data-stu-id="f28ff-137">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact, to back-to-back burst losses that cause complete audio cut-out.</span></span>
- <span data-ttu-id="f28ff-138">**Vibración:** este es el cambio promedio de retraso entre paquetes sucesivos.</span><span class="sxs-lookup"><span data-stu-id="f28ff-138">**Jitter** - This is the average change in delay between successive packets.</span></span>

<span data-ttu-id="f28ff-139">El uso de datos esperado de Walkie Talkie es de unos 20 KB/s al enviar o recibir audio.</span><span class="sxs-lookup"><span data-stu-id="f28ff-139">Expected data usage from Walkie Talkie is around 20KB/s when sending or receiving audio.</span></span> <span data-ttu-id="f28ff-140">Cuando está inactivo, el uso de datos esperados de Walkie Talkie es insignificante.</span><span class="sxs-lookup"><span data-stu-id="f28ff-140">When idle, expected data usage from Walkie Talkie is negligible.</span></span>

### <a name="walkie-talkie-devices"></a><span data-ttu-id="f28ff-141">Dispositivos Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="f28ff-141">Walkie Talkie devices</span></span>

<span data-ttu-id="f28ff-142">Los trabajadores de primera línea a menudo necesitan hablar y recibir llamadas de Walkie Talkie incluso cuando sus teléfonos están bloqueados.</span><span class="sxs-lookup"><span data-stu-id="f28ff-142">Frontline workers often need to speak and receive Walkie Talkie calls even when their phones are locked.</span></span> <span data-ttu-id="f28ff-143">Esta experiencia es posible a través de dispositivos especializados con un botón PTT dedicado.</span><span class="sxs-lookup"><span data-stu-id="f28ff-143">This experience is possible through specialized devices with a dedicated PTT button.</span></span>

- <span data-ttu-id="f28ff-144">Auriculares</span><span class="sxs-lookup"><span data-stu-id="f28ff-144">Headsets</span></span>
  - <span data-ttu-id="f28ff-145">Auriculares con cable ([Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/))</span><span class="sxs-lookup"><span data-stu-id="f28ff-145">Wired headsets ([Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/))</span></span>
  - <span data-ttu-id="f28ff-146">Auriculares inalámbricos ([Jabra BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie))</span><span class="sxs-lookup"><span data-stu-id="f28ff-146">Wireless headsets ([Jabra BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie))</span></span>
- <span data-ttu-id="f28ff-147">Teléfonos resistentes</span><span class="sxs-lookup"><span data-stu-id="f28ff-147">Rugged phones</span></span>
  - <span data-ttu-id="f28ff-148">Samsung Galaxy XCover Pro</span><span class="sxs-lookup"><span data-stu-id="f28ff-148">Samsung Galaxy XCover Pro</span></span>
    - <span data-ttu-id="f28ff-149">[Más información](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).</span><span class="sxs-lookup"><span data-stu-id="f28ff-149">[More info](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).</span></span>
    - <span data-ttu-id="f28ff-150">[Guía de configuración](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).</span><span class="sxs-lookup"><span data-stu-id="f28ff-150">[Setup guide](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).</span></span>

> [!NOTE]
> <span data-ttu-id="f28ff-151">Estos dispositivos no están certificados por Teams.</span><span class="sxs-lookup"><span data-stu-id="f28ff-151">These devices are not Teams certified.</span></span> <span data-ttu-id="f28ff-152">Se han validado para trabajar con Teams Walkie Talkie.</span><span class="sxs-lookup"><span data-stu-id="f28ff-152">They have been validated to work with Teams Walkie Talkie.</span></span>

### <a name="license-requirements"></a><span data-ttu-id="f28ff-153">Requisitos de licencia</span><span class="sxs-lookup"><span data-stu-id="f28ff-153">License requirements</span></span>

<span data-ttu-id="f28ff-154">La aplicación Walkie Talkie se incluye en todas las licencias de pago de Teams en las suscripciones de [Office 365.](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)</span><span class="sxs-lookup"><span data-stu-id="f28ff-154">Walkie Talkie app is included in all paid licenses of Teams in [Office 365 subscriptions](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing).</span></span> <span data-ttu-id="f28ff-155">Para obtener más información sobre cómo obtener Teams, consulte [¿Cómo obtendría acceso a Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)</span><span class="sxs-lookup"><span data-stu-id="f28ff-155">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span></span>

> [!NOTE]
> <span data-ttu-id="f28ff-156">Algunas características avanzadas pueden requerir licencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="f28ff-156">Certain advanced features may require additional licensing.</span></span> <span data-ttu-id="f28ff-157">Por ejemplo, la integración con Samsung Galaxy XCover Pro requiere una licencia knox.</span><span class="sxs-lookup"><span data-stu-id="f28ff-157">For example, integration with Samsung Galaxy XCover Pro requires a Knox license.</span></span>

## <a name="further-information"></a><span data-ttu-id="f28ff-158">Más información</span><span class="sxs-lookup"><span data-stu-id="f28ff-158">Further information</span></span>

- <span data-ttu-id="f28ff-159">Los administradores de IT pueden mantener el control sobre quién usa Walkie Talkie a través de directivas de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f28ff-159">ITAdmins can maintain control over who is using Walkie Talkie through App Policies.</span></span>
- <span data-ttu-id="f28ff-160">Si el trabajador de Frontline usa datos móviles para comunicarse a través de Teams, Walkie Talkie usará el mismo método.</span><span class="sxs-lookup"><span data-stu-id="f28ff-160">If your Frontline worker is using mobile data to communicate via Teams, Walkie Talkie will use the same method.</span></span>
- <span data-ttu-id="f28ff-161">Walkie Talkie debe funcionar bien en situaciones de ancho de banda bajos o situaciones en las que el smartphone está conectado y funcionando.</span><span class="sxs-lookup"><span data-stu-id="f28ff-161">Walkie Talkie should work well in low bandwidth situations, or situations where your smartphone is connected and working.</span></span> <span data-ttu-id="f28ff-162">Walkie Talkie no funcionará cuando no haya ninguna conectividad.</span><span class="sxs-lookup"><span data-stu-id="f28ff-162">Walkie Talkie will not work when there is no connectivity at all.</span></span>

<span data-ttu-id="f28ff-163">Para obtener más información sobre la experiencia del usuario final, vea:</span><span class="sxs-lookup"><span data-stu-id="f28ff-163">For further reading on the end-user experience, see:</span></span>

- [<span data-ttu-id="f28ff-164">Introducción a Teams Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="f28ff-164">Get started with Teams Walkie Talkie</span></span>](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [<span data-ttu-id="f28ff-165">Comunicarse con su equipo con Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="f28ff-165">Communicate with your team with Walkie Talkie</span></span>](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
