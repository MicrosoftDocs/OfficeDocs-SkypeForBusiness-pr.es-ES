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
ms.openlocfilehash: 9f86d40772eb067a561708c6170ef2354bae521b
ms.sourcegitcommit: 05411575d07d3eadc79d872d1cf81b36aae25621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2021
ms.locfileid: "52479077"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a><span data-ttu-id="81b96-103">Aplicación Walkie Talkie en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="81b96-103">Walkie Talkie app in Microsoft Teams</span></span>

<span data-ttu-id="81b96-104">La aplicación Walkie Talkie de Teams proporciona una comunicación instantánea push-to-talk (PTT) para su equipo y ahora está disponible en Android.</span><span class="sxs-lookup"><span data-stu-id="81b96-104">The Walkie Talkie app in Teams provides instant push-to-talk (PTT) communication for your team and is now available on Android.</span></span> <span data-ttu-id="81b96-105">Walkie Talkie permite a los usuarios conectarse con su equipo con los mismos canales subyacentes de los que son miembros.</span><span class="sxs-lookup"><span data-stu-id="81b96-105">Walkie Talkie allows users to connect with their team using the same underlying channels they're members of.</span></span> <span data-ttu-id="81b96-106">Solo los usuarios que se conectan a Walkie Talkie en un canal se convierten en participantes y pueden comunicarse entre sí mediante push-to-talk, de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="81b96-106">Only users who connect to Walkie Talkie in a channel become participants and can communicate with each other using push-to-talk, one at a time.</span></span>

<span data-ttu-id="81b96-107">Con Walkie Talkie en Teams, los trabajadores de Frontline ahora pueden comunicarse de forma segura con una experiencia PTT familiar sin tener que llevar radios voluminosos, y Walkie Talkie funciona en cualquier lugar con conexión WiFi o conexión a Internet móvil.</span><span class="sxs-lookup"><span data-stu-id="81b96-107">With Walkie Talkie in Teams, Frontline workers can now securely communicate with a familiar PTT experience without needing to carry bulky radios, and Walkie Talkie works anywhere with WiFi or cellular internet connectivity.</span></span>

## <a name="getting-started"></a><span data-ttu-id="81b96-108">Introducción</span><span class="sxs-lookup"><span data-stu-id="81b96-108">Getting started</span></span>

### <a name="deploying-walkie-talkie"></a><span data-ttu-id="81b96-109">Implementar Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="81b96-109">Deploying Walkie Talkie</span></span>

<span data-ttu-id="81b96-110">Actualmente, Walkie Talkie está disponible para dispositivos Android con Google Mobile Services (GMS) y no está preinstalado.</span><span class="sxs-lookup"><span data-stu-id="81b96-110">Currently, Walkie Talkie is available for Android devices with Google Mobile Services (GMS) and is not pre-installed.</span></span> <span data-ttu-id="81b96-111">Para habilitar esta característica para los usuarios de su organización, [](teams-app-setup-policies.md)debe agregar Walkie Talkie a la directiva de configuración de aplicaciones asignada a los usuarios desde el Centro de administración de   [Teams.](https://admin.teams.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="81b96-111">To enable this feature for users in your organization, you need to add Walkie Talkie to the [App Setup Policy](teams-app-setup-policies.md) assigned to users from the [Teams Admin Center](https://admin.teams.microsoft.com/).</span></span> <span data-ttu-id="81b96-112">Una vez habilitado, Walkie Talkie estará disponible en la aplicación Android en un plazo de 48 horas.</span><span class="sxs-lookup"><span data-stu-id="81b96-112">Once enabled, Walkie Talkie will become available on the Android app within 48 hours.</span></span>

### <a name="adding-walkie-talkie-to-your-app-list"></a><span data-ttu-id="81b96-113">Agregar Walkie Talkie a la lista de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="81b96-113">Adding Walkie Talkie to your app list</span></span>

<span data-ttu-id="81b96-114">En el Microsoft Teams de administración, en Teams directivas de configuración de la aplicación, debería tener permitir la anclación de  >  usuario establecida en  **On**.</span><span class="sxs-lookup"><span data-stu-id="81b96-114">In the Microsoft Teams admin center, under **Teams app** > **Setup policies**, you should have **Allow user pinning** set to **On**.</span></span> <span data-ttu-id="81b96-115">A continuación, en la sección Aplicaciones ancladas, haga clic **en +Agregar aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="81b96-115">Then, under the Pinned Apps section, click **+Add Apps**.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Muestra la sección Aplicaciones ancladas y el botón Agregar aplicaciones que se va a seleccionar.":::

<span data-ttu-id="81b96-117">En el **panel** Agregar aplicaciones ancladas que aparece  a la derecha, use el cuadro de texto Buscar para buscar Walkie Talkie.</span><span class="sxs-lookup"><span data-stu-id="81b96-117">On the **Add pinned apps** panel that appears on the right, use the **Search** textbox to look for Walkie Talkie.</span></span> <span data-ttu-id="81b96-118">Cuando lo tenga como resultado de  búsqueda, seleccione el botón Agregar a la derecha del nombre para agregarlo a la lista.</span><span class="sxs-lookup"><span data-stu-id="81b96-118">When you have it as a search result, select the **Add** button to the right of the name to add it to your list.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Muestra la barra lateral Agregar aplicaciones ancladas con Walkie escrito en el panel de búsqueda y la aplicación Walkie Talkie en los resultados de búsqueda, con el botón Agregar junto a ella.":::

<span data-ttu-id="81b96-120">La aplicación Walkie Talkie ahora debería aparecer en la lista Aplicaciones ancladas y estar disponible para su uso una vez que haga clic en **el botón** Guardar.</span><span class="sxs-lookup"><span data-stu-id="81b96-120">The Walkie Talkie app should now appear on the Pinned Apps list, and be available for use once you click the **Save** button.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Muestra la lista de aplicaciones ancladas con la aplicación Walkie Talkie agregada y el botón Guardar debajo de la lista.":::

### <a name="network-documentation"></a><span data-ttu-id="81b96-122">Documentación de red</span><span class="sxs-lookup"><span data-stu-id="81b96-122">Network documentation</span></span>

<span data-ttu-id="81b96-123">Walkie Talkie en Teams requiere conectividad a Internet y por debajo de las condiciones de red se requieren para una experiencia óptima.</span><span class="sxs-lookup"><span data-stu-id="81b96-123">Walkie Talkie in Teams requires Internet connectivity and below the network conditions are required for optimal experience.</span></span>

|<span data-ttu-id="81b96-124">Métrica</span><span class="sxs-lookup"><span data-stu-id="81b96-124">Metric</span></span> | <span data-ttu-id="81b96-125">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="81b96-125">Required</span></span> |
|---|---|
|<span data-ttu-id="81b96-126">Latencia (RTT)</span><span class="sxs-lookup"><span data-stu-id="81b96-126">Latency (RTT)</span></span> | <span data-ttu-id="81b96-127">< 300 ms</span><span class="sxs-lookup"><span data-stu-id="81b96-127">< 300ms</span></span> |
|<span data-ttu-id="81b96-128">Vibración</span><span class="sxs-lookup"><span data-stu-id="81b96-128">Jitter</span></span> |<span data-ttu-id="81b96-129">< 30 ms</span><span class="sxs-lookup"><span data-stu-id="81b96-129">< 30ms</span></span> |
|<span data-ttu-id="81b96-130">Pérdida de paquetes</span><span class="sxs-lookup"><span data-stu-id="81b96-130">Packet Loss</span></span> |<span data-ttu-id="81b96-131">< 1%</span><span class="sxs-lookup"><span data-stu-id="81b96-131">< 1%</span></span> |

<span data-ttu-id="81b96-132">Como se ha indicado anteriormente, la calidad de los medios en tiempo real a través de una red IP se encuentra muy afectada por la calidad de la conectividad de red, pero especialmente por la cantidad de:</span><span class="sxs-lookup"><span data-stu-id="81b96-132">As noted above, the quality of real-time media over an IP network is greatly impacted by the quality of the network connectivity, but especially by the amount of:</span></span>

- <span data-ttu-id="81b96-133">**Latencia:** este es el tiempo que se tarda en obtener un paquete IP desde el punto A hasta el punto B de la red.</span><span class="sxs-lookup"><span data-stu-id="81b96-133">**Latency** - This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="81b96-134">Este retraso de propagación de red está esencialmente vinculado a la distancia física entre los dos puntos y la velocidad de la luz, incluida una mayor sobrecarga de los distintos enrutadores entre sí.</span><span class="sxs-lookup"><span data-stu-id="81b96-134">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including more overhead taken by the various routers in between.</span></span> <span data-ttu-id="81b96-135">La latencia se mide como Tiempo de ida y vuelta (RTT).</span><span class="sxs-lookup"><span data-stu-id="81b96-135">Latency is measured as Round-trip Time (RTT).</span></span>
- <span data-ttu-id="81b96-136">**Vibración entre llegadas:** este es el cambio medio de retraso entre paquetes sucesivos.</span><span class="sxs-lookup"><span data-stu-id="81b96-136">**Inter-Arrival Jitter** - This is the average change in delay between successive packets.</span></span>
- <span data-ttu-id="81b96-137">**Pérdida de paquetes:** a menudo se define como un porcentaje de paquetes que se pierden en una ventana de tiempo determinada.</span><span class="sxs-lookup"><span data-stu-id="81b96-137">**Packet Loss** - This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="81b96-138">La pérdida de paquetes afecta directamente a la calidad de audio, desde pequeños paquetes perdidos individuales que casi no tienen impacto, hasta pérdidas de ráfagas back-to-back que provocan un corte total de audio.</span><span class="sxs-lookup"><span data-stu-id="81b96-138">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact, to back-to-back burst losses that cause complete audio cut-out.</span></span>

<span data-ttu-id="81b96-139">El uso de datos esperado de Walkie Talkie es de unos 20 Kb/s al enviar o recibir audio.</span><span class="sxs-lookup"><span data-stu-id="81b96-139">Expected data usage from Walkie Talkie is around 20 Kb/s when sending or receiving audio.</span></span> <span data-ttu-id="81b96-140">Cuando está inactivo, el uso de datos esperados de Walkie Talkie es insignificante.</span><span class="sxs-lookup"><span data-stu-id="81b96-140">When idle, expected data usage from Walkie Talkie is negligible.</span></span>

### <a name="walkie-talkie-devices"></a><span data-ttu-id="81b96-141">Dispositivos Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="81b96-141">Walkie Talkie devices</span></span>

<span data-ttu-id="81b96-142">Los trabajadores de primera línea a menudo necesitan hablar y recibir llamadas de Walkie Talkie incluso cuando sus teléfonos están bloqueados.</span><span class="sxs-lookup"><span data-stu-id="81b96-142">Frontline workers often need to speak and receive Walkie Talkie calls even when their phones are locked.</span></span> <span data-ttu-id="81b96-143">Esta experiencia es posible a través de dispositivos especializados con un botón PTT dedicado.</span><span class="sxs-lookup"><span data-stu-id="81b96-143">This experience is possible through specialized devices with a dedicated PTT button.</span></span>

- <span data-ttu-id="81b96-144">**Auriculares**</span><span class="sxs-lookup"><span data-stu-id="81b96-144">**Headsets**</span></span>
  - <span data-ttu-id="81b96-145">Auriculares inalámbricos</span><span class="sxs-lookup"><span data-stu-id="81b96-145">Wireless headsets</span></span> 
    - [<span data-ttu-id="81b96-146">BlueParrott</span><span class="sxs-lookup"><span data-stu-id="81b96-146">BlueParrott</span></span>](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - <span data-ttu-id="81b96-147">Auriculares con cable</span><span class="sxs-lookup"><span data-stu-id="81b96-147">Wired headsets</span></span> 
    - [<span data-ttu-id="81b96-148">Klein Electronics</span><span class="sxs-lookup"><span data-stu-id="81b96-148">Klein Electronics</span></span>](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- <span data-ttu-id="81b96-149">**Teléfonos resistentes**</span><span class="sxs-lookup"><span data-stu-id="81b96-149">**Rugged phones**</span></span>
  - <span data-ttu-id="81b96-150">Samsung [Galaxy XCover Pro,](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/) [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)</span><span class="sxs-lookup"><span data-stu-id="81b96-150">Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)</span></span>
    -  <span data-ttu-id="81b96-151">Configuración manual: con Teams instalado, vaya a Configuración > características avanzadas > XCover/Active key.</span><span class="sxs-lookup"><span data-stu-id="81b96-151">Manual setup - With Teams installed, navigate to Settings > Advanced Features > XCover/Active key.</span></span> <span data-ttu-id="81b96-152">Activa "Tecla Control XCover con la aplicación" y selecciona "Teams"</span><span class="sxs-lookup"><span data-stu-id="81b96-152">Turn on 'Control XCover key with app' and select 'Teams'</span></span>
    -  [<span data-ttu-id="81b96-153">Configuración de MDM</span><span class="sxs-lookup"><span data-stu-id="81b96-153">MDM setup</span></span>](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)

> [!NOTE]
> <span data-ttu-id="81b96-154">Estos dispositivos no están Teams certificado.</span><span class="sxs-lookup"><span data-stu-id="81b96-154">These devices are not Teams certified.</span></span> <span data-ttu-id="81b96-155">Se han validado para trabajar con Teams Walkie Talkie.</span><span class="sxs-lookup"><span data-stu-id="81b96-155">They have been validated to work with Teams Walkie Talkie.</span></span>

### <a name="license-requirements"></a><span data-ttu-id="81b96-156">Requisitos de licencia</span><span class="sxs-lookup"><span data-stu-id="81b96-156">License requirements</span></span>

<span data-ttu-id="81b96-157">La aplicación Walkie Talkie se incluye en todas las licencias de pago de Teams en [Office 365 suscripciones.](/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="81b96-157">Walkie Talkie app is included in all paid licenses of Teams in [Office 365 subscriptions](/office365/servicedescriptions/teams-service-description).</span></span> <span data-ttu-id="81b96-158">Para obtener más información sobre cómo obtener Teams, consulte [¿Cómo puedo obtener acceso](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)a Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="81b96-158">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span></span>

> [!NOTE]
> <span data-ttu-id="81b96-159">Algunas características avanzadas pueden requerir licencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="81b96-159">Certain advanced features may require additional licensing.</span></span> <span data-ttu-id="81b96-160">Por ejemplo, la integración con Samsung Galaxy XCover Pro requiere una licencia knox.</span><span class="sxs-lookup"><span data-stu-id="81b96-160">For example, integration with Samsung Galaxy XCover Pro requires a Knox license.</span></span>

## <a name="further-information"></a><span data-ttu-id="81b96-161">Más información</span><span class="sxs-lookup"><span data-stu-id="81b96-161">Further information</span></span>

- <span data-ttu-id="81b96-162">Los administradores de IT pueden mantener el control sobre quién usa Walkie Talkie a través de directivas de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="81b96-162">ITAdmins can maintain control over who is using Walkie Talkie through App Policies.</span></span>
- <span data-ttu-id="81b96-163">Si el trabajador de Frontline usa datos móviles para comunicarse Teams, Walkie Talkie usará el mismo método.</span><span class="sxs-lookup"><span data-stu-id="81b96-163">If your Frontline worker is using mobile data to communicate via Teams, Walkie Talkie will use the same method.</span></span>
- <span data-ttu-id="81b96-164">Walkie Talkie debe funcionar bien en situaciones de ancho de banda bajos o situaciones en las que el smartphone está conectado y funcionando.</span><span class="sxs-lookup"><span data-stu-id="81b96-164">Walkie Talkie should work well in low bandwidth situations, or situations where your smartphone is connected and working.</span></span> <span data-ttu-id="81b96-165">Walkie Talkie no funcionará cuando no haya ninguna conectividad.</span><span class="sxs-lookup"><span data-stu-id="81b96-165">Walkie Talkie will not work when there is no connectivity at all.</span></span>

<span data-ttu-id="81b96-166">Para obtener más información sobre la experiencia del usuario final, vea:</span><span class="sxs-lookup"><span data-stu-id="81b96-166">For further reading on the end-user experience, see:</span></span>

- [<span data-ttu-id="81b96-167">Introducción a Teams Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="81b96-167">Get started with Teams Walkie Talkie</span></span>](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [<span data-ttu-id="81b96-168">Comunicarse con su equipo con Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="81b96-168">Communicate with your team with Walkie Talkie</span></span>](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
