---
title: Aplicación de walkie talkie en Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Cómo configurar la aplicación de talkie de walkie en Microsoft Teams, desde una perspectiva de ITAdmin.
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
ms.openlocfilehash: 9369cf56a32142d6527fcb86271d8d0fa56718ec
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2020
ms.locfileid: "45043019"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a><span data-ttu-id="94b39-103">Aplicación talkie de walkie en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="94b39-103">Walkie Talkie app in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="94b39-104">La aplicación de talkie de walkie de Teams ofrece una comunicación instantánea inmediata (PTT) para su equipo y pronto estará disponible en la versión preliminar pública de Android.</span><span class="sxs-lookup"><span data-stu-id="94b39-104">The Walkie Talkie app in Teams provides instant push-to-talk (PTT) communication for your team and will soon be available in Public Preview on Android.</span></span> <span data-ttu-id="94b39-105">Walkie talkie permite que los usuarios se conecten con su equipo usando los mismos canales subyacentes de los que son miembros.</span><span class="sxs-lookup"><span data-stu-id="94b39-105">Walkie Talkie allows users to connect with their team using the same underlying channels they're members of.</span></span> <span data-ttu-id="94b39-106">Solo los usuarios que se conectan a walkie talkie de un canal se convierten en participantes y pueden comunicarse entre sí usando Push para hablar, de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="94b39-106">Only users who connect to Walkie Talkie in a channel become participants and can communicate with each other using push-to-talk, one at a time.</span></span>

<span data-ttu-id="94b39-107">Con walkie talkie en Teams, los Firstline los trabajadores pueden comunicarse con seguridad con una experiencia de PTT que les resulte familiar sin necesidad de transportar radios de gran volumen y walkie talkie funciona en cualquier lugar con conectividad WiFi o de Internet de telefonía móvil.</span><span class="sxs-lookup"><span data-stu-id="94b39-107">With Walkie Talkie in Teams, firstline workers can now securely communicate with a familiar PTT experience without needing to carry bulky radios, and Walkie Talkie works anywhere with WiFi or cellular internet connectivity.</span></span>

## <a name="getting-started"></a><span data-ttu-id="94b39-108">Introducción</span><span class="sxs-lookup"><span data-stu-id="94b39-108">Getting started</span></span>

### <a name="deploying-walkie-talkie"></a><span data-ttu-id="94b39-109">Implementación de walkie talkie</span><span class="sxs-lookup"><span data-stu-id="94b39-109">Deploying Walkie Talkie</span></span>

<span data-ttu-id="94b39-110">Durante la versión preliminar pública, walkie talkie no está preinstalado.</span><span class="sxs-lookup"><span data-stu-id="94b39-110">During the Public Preview, Walkie Talkie is not pre-installed.</span></span> <span data-ttu-id="94b39-111">Para habilitar esta característica para los usuarios de su organización, debe agregar walkie talkie a la Directiva de configuración de la [aplicación](teams-app-setup-policies.md)   asignada a los usuarios desde el [centro de administración de Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="94b39-111">To enable this feature for users in your organization, you need to add Walkie Talkie to the [App Setup Policy](teams-app-setup-policies.md) assigned to users from the [Teams Admin Center](https://admin.teams.microsoft.com/).</span></span>

<span data-ttu-id="94b39-112">Una vez habilitado, walkie talkie estará disponible en la aplicación de Android en 48 horas.</span><span class="sxs-lookup"><span data-stu-id="94b39-112">Once enabled, Walkie Talkie will become available on the Android app within 48 hours.</span></span>

### <a name="adding-walkie-talkie-to-your-app-list"></a><span data-ttu-id="94b39-113">Agregar walkie talkie a la lista de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="94b39-113">Adding Walkie Talkie to your app list</span></span>

<span data-ttu-id="94b39-114">En el centro de administración de Microsoft Teams, en directivas de configuración de la **aplicación de Teams**  >  **Setup policies**, debe **permitir el anclaje de usuario** establecido en **activado**.</span><span class="sxs-lookup"><span data-stu-id="94b39-114">In the Microsoft Teams admin center, under **Teams app** > **Setup policies**, you should have **Allow user pinning** set to **On**.</span></span> <span data-ttu-id="94b39-115">Después, en la sección aplicaciones ancladas, haga clic en **+ agregar aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="94b39-115">Then, under the Pinned Apps section, click **+Add Apps**.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Muestra la sección aplicaciones ancladas y el botón agregar aplicaciones para que se seleccionen.":::

<span data-ttu-id="94b39-117">En el panel **agregar aplicaciones ancladas** que aparece a la derecha, use el cuadro de texto de **búsqueda** para buscar walkie talkie.</span><span class="sxs-lookup"><span data-stu-id="94b39-117">On the **Add pinned apps** panel that appears on the right, use the **Search** textbox to look for Walkie Talkie.</span></span> <span data-ttu-id="94b39-118">Cuando la haya obtenido como resultado de la búsqueda, haga clic en el botón **Agregar** a la derecha del nombre para agregarlo a la lista.</span><span class="sxs-lookup"><span data-stu-id="94b39-118">When you have it as a search result, click the **Add** button to the right of the name to add it to your list.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Muestra la barra lateral agregar aplicaciones ancladas con walkie introducido en el panel de búsqueda y la aplicación de walkie talkie en los resultados de la búsqueda, con el botón Agregar junto a él.":::

<span data-ttu-id="94b39-120">Ahora, la aplicación walkie talkie debería aparecer en la lista de aplicaciones ancladas y estará disponible para su uso una vez que haga clic en el botón **Guardar** .</span><span class="sxs-lookup"><span data-stu-id="94b39-120">The Walkie Talkie app should now appear on the Pinned Apps list, and be available for use once you click the **Save** button.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Muestra la lista de aplicaciones ancladas con la aplicación walkie talkie agregada y el botón Guardar situado debajo de la lista.":::

### <a name="network-documentation"></a><span data-ttu-id="94b39-122">Documentación de red</span><span class="sxs-lookup"><span data-stu-id="94b39-122">Network documentation</span></span>

<span data-ttu-id="94b39-123">Walkie talkie en Teams requiere conexión a Internet y, por lo más, las condiciones de la red son necesarias para una experiencia óptima.</span><span class="sxs-lookup"><span data-stu-id="94b39-123">Walkie Talkie in Teams requires Internet connectivity and below the network conditions are required for optimal experience.</span></span>

<span data-ttu-id="94b39-124">Latencia (RTT) < 300ms | Vibración < 30ms | Pérdida de paquetes < 1%</span><span class="sxs-lookup"><span data-stu-id="94b39-124">Latency (RTT) < 300ms | Jitter < 30ms | Packet Loss < 1%</span></span>

<span data-ttu-id="94b39-125">Como se mencionó anteriormente, la calidad de los medios en tiempo real a través de una red IP se ve afectada en gran medida por la calidad de la conectividad de la red, pero especialmente por la cantidad de:</span><span class="sxs-lookup"><span data-stu-id="94b39-125">As noted above, the quality of real-time media over an IP network is greatly impacted by the quality of the network connectivity, but especially by the amount of:</span></span>

- <span data-ttu-id="94b39-126">**Latencia** : es el tiempo que se tarda en obtener un paquete IP del punto a al punto B de la red.</span><span class="sxs-lookup"><span data-stu-id="94b39-126">**Latency** - This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="94b39-127">Este retraso de propagación de red está esencialmente unido a la distancia física entre los dos puntos y la velocidad de luz, incluida la sobrecarga adicional que realizan los distintos enrutadores entre.</span><span class="sxs-lookup"><span data-stu-id="94b39-127">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including additional overhead taken by the various routers in between.</span></span> <span data-ttu-id="94b39-128">La latencia se mide como un tiempo de ida y vuelta (RTT).</span><span class="sxs-lookup"><span data-stu-id="94b39-128">Latency is measured as Round-trip Time (RTT).</span></span>
- <span data-ttu-id="94b39-129">**Pérdida de paquetes** : suele definirse como un porcentaje de paquetes que se pierden en una ventana determinada de tiempo.</span><span class="sxs-lookup"><span data-stu-id="94b39-129">**Packet Loss** - This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="94b39-130">La pérdida de paquetes afecta directamente a la calidad del audio, desde pequeños paquetes perdidos individuales, casi sin impacto, hasta pérdidas de ráfagas en el fondo que causan un recorte completo del audio.</span><span class="sxs-lookup"><span data-stu-id="94b39-130">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact, to back-to-back burst losses that cause complete audio cut-out.</span></span>
- <span data-ttu-id="94b39-131">**Vibración** : este es el cambio medio en el retraso entre paquetes sucesivos.</span><span class="sxs-lookup"><span data-stu-id="94b39-131">**Jitter** - This is the average change in delay between successive packets.</span></span>

<span data-ttu-id="94b39-132">El uso de datos esperado de walkie talkie está cerca de 20KB/s al enviar o recibir audio.</span><span class="sxs-lookup"><span data-stu-id="94b39-132">Expected data usage from Walkie Talkie is around 20KB/s when sending or receiving audio.</span></span> <span data-ttu-id="94b39-133">Cuando está inactivo, el uso de datos esperado de walkie talkie es insignificante.</span><span class="sxs-lookup"><span data-stu-id="94b39-133">When idle, expected data usage from Walkie Talkie is negligible.</span></span>

### <a name="walkie-talkie-devices"></a><span data-ttu-id="94b39-134">Walkie talkie dispositivos</span><span class="sxs-lookup"><span data-stu-id="94b39-134">Walkie Talkie devices</span></span>

<span data-ttu-id="94b39-135">Los trabajadores de los Firstline a menudo necesitan hablar y recibir llamadas de talkie walkie incluso cuando sus teléfonos están bloqueados.</span><span class="sxs-lookup"><span data-stu-id="94b39-135">FirstLine workers often need to speak and receive Walkie Talkie calls even when their phones are locked.</span></span> <span data-ttu-id="94b39-136">Esta experiencia es posible mediante dispositivos especializados con un botón de PTT dedicado.</span><span class="sxs-lookup"><span data-stu-id="94b39-136">This experience is possible through specialized devices with a dedicated PTT button.</span></span>

- <span data-ttu-id="94b39-137">Teléfonos existentes</span><span class="sxs-lookup"><span data-stu-id="94b39-137">Existing phones</span></span>
  - <span data-ttu-id="94b39-138">Auriculares con cable ([Klein Electronics](https://www.kleinelectronics.com/))</span><span class="sxs-lookup"><span data-stu-id="94b39-138">Wired headsets ([Klein Electronics](https://www.kleinelectronics.com/))</span></span>
  - <span data-ttu-id="94b39-139">Auriculares con micrófono inalámbricos ([Jabra BlueParrott](https://www.blueparrott.com/))</span><span class="sxs-lookup"><span data-stu-id="94b39-139">Wireless headsets ([Jabra BlueParrott](https://www.blueparrott.com/))</span></span>
- <span data-ttu-id="94b39-140">Teléfonos resistentes</span><span class="sxs-lookup"><span data-stu-id="94b39-140">Rugged phones</span></span>
  - <span data-ttu-id="94b39-141">Samsung Galaxy XCover Pro</span><span class="sxs-lookup"><span data-stu-id="94b39-141">Samsung Galaxy XCover Pro</span></span>
    - <span data-ttu-id="94b39-142">[Más información](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).</span><span class="sxs-lookup"><span data-stu-id="94b39-142">[More info](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).</span></span>
    - <span data-ttu-id="94b39-143">[Guía de configuración](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).</span><span class="sxs-lookup"><span data-stu-id="94b39-143">[Setup guide](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).</span></span>

> [!NOTE]
> <span data-ttu-id="94b39-144">Estos dispositivos no tienen la certificación de equipos.</span><span class="sxs-lookup"><span data-stu-id="94b39-144">These devices are not Teams certified.</span></span> <span data-ttu-id="94b39-145">Se han validado para trabajar con Teams walkie talkie.</span><span class="sxs-lookup"><span data-stu-id="94b39-145">They have been validated to work with Teams Walkie Talkie.</span></span>

### <a name="license-requirements"></a><span data-ttu-id="94b39-146">Requisitos de licencia</span><span class="sxs-lookup"><span data-stu-id="94b39-146">License requirements</span></span>

<span data-ttu-id="94b39-147">Walkie talkie aplicación está incluida en todas las licencias de pagos de Teams en [Office 365 suscripciones](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing).</span><span class="sxs-lookup"><span data-stu-id="94b39-147">Walkie Talkie app is included in all paid licenses of Teams in [Office 365 subscriptions](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing).</span></span> <span data-ttu-id="94b39-148">Para obtener más información sobre la obtención de equipos, consulte [¿Cómo puedo obtener acceso a Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span><span class="sxs-lookup"><span data-stu-id="94b39-148">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span></span>

> [!NOTE]
> <span data-ttu-id="94b39-149">Ciertas características avanzadas pueden requerir licencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="94b39-149">Certain advanced features may require additional licensing.</span></span> <span data-ttu-id="94b39-150">Por ejemplo, la integración con Samsung Galaxy XCover Pro requiere una licencia de Knox.</span><span class="sxs-lookup"><span data-stu-id="94b39-150">For example, integration with Samsung Galaxy XCover Pro requires a Knox license.</span></span>

## <a name="further-information"></a><span data-ttu-id="94b39-151">Más información</span><span class="sxs-lookup"><span data-stu-id="94b39-151">Further information</span></span>

- <span data-ttu-id="94b39-152">ITAdmins puede mantener el control sobre quién está usando walkie talkie a través de las directivas de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="94b39-152">ITAdmins can maintain control over who is using Walkie Talkie through App Policies.</span></span>
- <span data-ttu-id="94b39-153">Si su trabajador de los Firstline usa datos móviles para comunicarse a través de Teams, walkie talkie usará el mismo método.</span><span class="sxs-lookup"><span data-stu-id="94b39-153">If your firstline worker is using mobile data to communicate via Teams, Walkie Talkie will use the same method.</span></span>
- <span data-ttu-id="94b39-154">Walkie talkie debería funcionar bien en situaciones de bajo ancho de banda o en situaciones en las que el smartphone está conectado y funcionando.</span><span class="sxs-lookup"><span data-stu-id="94b39-154">Walkie Talkie should work well in low bandwidth situations, or situations where your smartphone is connected and working.</span></span> <span data-ttu-id="94b39-155">Walkie talkie no funcionará cuando no haya conectividad.</span><span class="sxs-lookup"><span data-stu-id="94b39-155">Walkie Talkie will not work when there is no connectivity at all.</span></span>

<span data-ttu-id="94b39-156">Para obtener más lecturas sobre la experiencia del usuario final, vea:</span><span class="sxs-lookup"><span data-stu-id="94b39-156">For further reading on the end-user experience, see:</span></span>

- [<span data-ttu-id="94b39-157">Introducción a teams walkie talkie</span><span class="sxs-lookup"><span data-stu-id="94b39-157">Get started with Teams Walkie Talkie</span></span>](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [<span data-ttu-id="94b39-158">Comuníquese con su equipo con walkie talkie</span><span class="sxs-lookup"><span data-stu-id="94b39-158">Communicate with your team with Walkie Talkie</span></span>](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
