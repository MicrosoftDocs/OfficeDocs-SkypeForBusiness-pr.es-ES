---
title: Configurar tipos de dirección IP en Skype Empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 'Resumen: Revise las consideraciones de tipo de dirección IP a continuación antes de implementar Skype empresarial Server.'
ms.openlocfilehash: 21e6254255766874872a342a2316dc8cddd5f9d2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297053"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a><span data-ttu-id="9186e-103">Configurar tipos de dirección IP en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="9186e-103">Configure IP address types in Skype for Business</span></span>

<span data-ttu-id="9186e-104">**Resumen:** Revise las consideraciones de tipo de dirección IP a continuación antes de implementar Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="9186e-104">**Summary:** Review the IP Address type considerations below before implementing Skype for Business Server.</span></span>

<span data-ttu-id="9186e-105">Para implementar los tipos de dirección IP, use la configuración de topología que configure en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="9186e-105">You deploy IP address types by using topology settings that you configure in Topology Builder.</span></span> <span data-ttu-id="9186e-106">En esta sección se describe cómo implementar los tipos de direcciones IP en servidores front-end, servidores de mediación y servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="9186e-106">This section describes how to deploy IP address types on Front End Servers, Mediation Servers, and Edge Servers.</span></span>

## <a name="deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="9186e-107">Implementar tipos de direcciones IP en un servidor front-end</span><span class="sxs-lookup"><span data-stu-id="9186e-107">Deploy IP address types on a Front End Server</span></span>

<span data-ttu-id="9186e-108">Con el generador de topologías, siga los pasos que se indican en el siguiente procedimiento para implementar tipos de direcciones IP en un servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="9186e-108">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="9186e-109">Para implementar los tipos de direcciones IP en un servidor front-end</span><span class="sxs-lookup"><span data-stu-id="9186e-109">To deploy IP address types on a Front End Server</span></span>

1. <span data-ttu-id="9186e-p102">En **Grupo de servidores front-end Enterprise Edition**, haga clic con el botón secundario dentro de un grupo y seleccione **Editar propiedades** (también puede seleccionar el servidor y hacer clic en **Editar propiedades** en el menú **Acción**).</span><span class="sxs-lookup"><span data-stu-id="9186e-p102">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**. (Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="9186e-112">En el cuadro de diálogo **Editar propiedades**, seleccione el tipo de dirección IP que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="9186e-112">In the **Edit Properties** dialog box, select the IP address type that you want to configure.</span></span> <span data-ttu-id="9186e-113">Para obtener una configuración de pila doble, seleccione **Habilitar IPv4** y **Habilitar IPv6**.</span><span class="sxs-lookup"><span data-stu-id="9186e-113">For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**.</span></span>

   <span data-ttu-id="9186e-114">**Cuadro de diálogo Editar propiedades para el grupo de servidores front-end**</span><span class="sxs-lookup"><span data-stu-id="9186e-114">**Edit Properties dialog box for the Front End Server pool**</span></span>

   - <span data-ttu-id="9186e-p104">**Usar todas las direcciones IP configuradas**. Seleccione esta opción si desea que se usen todas las direcciones IP definidas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="9186e-p104">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

     > [!NOTE]
     > <span data-ttu-id="9186e-117">Esta es la opción recomendada para la configuración para IP versión 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="9186e-117">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

   - <span data-ttu-id="9186e-p105">**Limitar el uso del servicio a las direcciones IP seleccionadas**. Seleccione esta opción para determinar una dirección específica en el servidor nuevo. Si selecciona esta opción, necesita introducir un valor para la **dirección IP principal**.</span><span class="sxs-lookup"><span data-stu-id="9186e-p105">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for **Primary IP address**.</span></span>

   - <span data-ttu-id="9186e-p106">**Dirección IP principal**. Introduzca una dirección IP que el servidor usará para todas las comunicaciones excepto para red telefónica conmutada (RTC). La dirección IP introducida necesita coincidir con el formato del tipo de dirección seleccionado.</span><span class="sxs-lookup"><span data-stu-id="9186e-p106">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

   - <span data-ttu-id="9186e-p107">**Dirección IP de RTC**. Defina una dirección IP para la RTC cuando asigne un servidor de mediación en el servidor front-end. Esta dirección necesita coincidir con el formato del tipo de dirección seleccionado.</span><span class="sxs-lookup"><span data-stu-id="9186e-p107">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>

> [!NOTE]
> <span data-ttu-id="9186e-127">La instalación de tarjetas de interfaz de red (NICs) adicionales para admitir la configuración de la dirección IP de RTC (o por cualquier otro motivo) en los servidores front-end no es compatible.</span><span class="sxs-lookup"><span data-stu-id="9186e-127">The installation of additional network interface cards (NICs) to support the PSTN IP address configuration (or for any other reason) on Front End Servers is not supported.</span></span> <span data-ttu-id="9186e-128">Para obtener más información sobre las configuraciones de NIC compatibles con Skype empresarial Server, consulte [plataformas de hardware de servidor para Lync Server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span><span class="sxs-lookup"><span data-stu-id="9186e-128">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span></span>

## <a name="deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="9186e-129">Implementar tipos de dirección IP en un servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="9186e-129">Deploy IP address types on a Mediation Server</span></span>

<span data-ttu-id="9186e-130">Con el generador de topologías, siga los pasos que se indican en el siguiente procedimiento para implementar tipos de direcciones IP en un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="9186e-130">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="9186e-131">Para implementar tipos de direcciones IP en un servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="9186e-131">To deploy IP address types on a Mediation Server</span></span>

- <span data-ttu-id="9186e-132">En el generador de topologías, en **grupos**de mediación, haga clic con el botón secundario en el servidor de un grupo y seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9186e-132">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="9186e-133">(También puede seleccionar el servidor y, a continuación, hacer clic en **Editar propiedades** en el menú **acción** ).</span><span class="sxs-lookup"><span data-stu-id="9186e-133">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

- <span data-ttu-id="9186e-p110">En el cuadro de diálogo **Editar propiedades**, seleccione el tipo de dirección IP que desea configurar. Para establecer una configuración de doble pila, seleccione **Habilitar IPv4** y **Habilitar IPv6**, como se muestra en la figura siguiente.</span><span class="sxs-lookup"><span data-stu-id="9186e-p110">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>

   <span data-ttu-id="9186e-136">**Cuadro de diálogo Editar propiedades para el grupo Servidor de mediación**</span><span class="sxs-lookup"><span data-stu-id="9186e-136">**Edit Properties dialog box for the Mediation Server pool**</span></span>

  - <span data-ttu-id="9186e-p111">**Usar todas las direcciones IP configuradas**. Seleccione esta opción si desea que se usen todas las direcciones IP definidas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="9186e-p111">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9186e-139">Esta es la opción recomendada para la configuración para IP versión 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="9186e-139">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

  - <span data-ttu-id="9186e-p112">**Limitar el uso del servicio a las direcciones IP seleccionadas**. Seleccione esta opción para determinar una dirección específica en el servidor nuevo. Si selecciona esta opción, necesita introducir un valor para la dirección IP principal.</span><span class="sxs-lookup"><span data-stu-id="9186e-p112">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>

  - <span data-ttu-id="9186e-p113">**Dirección IP principal**. Introduzca una dirección IP que el servidor usará para todas las comunicaciones excepto para red telefónica conmutada (RTC). La dirección IP introducida necesita coincidir con el formato del tipo de dirección seleccionado.</span><span class="sxs-lookup"><span data-stu-id="9186e-p113">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

  - <span data-ttu-id="9186e-p114">**Dirección IP de RTC**. Defina una dirección IP para la RTC cuando asigne un servidor de mediación en el servidor front-end. Esta dirección necesita coincidir con el formato del tipo de dirección seleccionado.</span><span class="sxs-lookup"><span data-stu-id="9186e-p114">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="9186e-149">Solo admitimos dos tarjetas de red en servidores de mediación *dedicados* .</span><span class="sxs-lookup"><span data-stu-id="9186e-149">We only support two network cards on *dedicated* Mediation Servers.</span></span> <span data-ttu-id="9186e-150">Si el rol de SServer de mediación se encuentra en el front-end, no se admiten las tarjetas de red dobles.</span><span class="sxs-lookup"><span data-stu-id="9186e-150">If the Mediation Sserver role is collocated on the Front End, then dual network cards are not supported.</span></span> 

> [!NOTE]
> - <span data-ttu-id="9186e-151">Para obtener más información sobre las configuraciones de NIC compatibles con Skype empresarial Server 2015, consulte [hardware para Skype empresarial server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="9186e-151">For more information about supported NIC configurations for Skype for Business Server 2015, see [Hardware for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span></span>
> - <span data-ttu-id="9186e-152">Para obtener más información sobre las configuraciones de NIC compatibles con Skype empresarial Server 2019, consulte [hardware para Skype empresarial server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span><span class="sxs-lookup"><span data-stu-id="9186e-152">For more information about supported NIC configurations for Skype for Business Server 2019, see [Hardware for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span></span>



## <a name="deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="9186e-153">Implementar tipos de dirección IP en un servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="9186e-153">Deploy IP address types on an Edge Server</span></span>

<span data-ttu-id="9186e-154">Siga estos pasos para usar el generador de topología:</span><span class="sxs-lookup"><span data-stu-id="9186e-154">Using Topology Builder, perform the following steps:</span></span>

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="9186e-155">Para implementar tipos de direcciones IP en un servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="9186e-155">To deploy IP address types on an Edge Server</span></span>

1. <span data-ttu-id="9186e-156">En el generador de topologías, en **grupos de límites**, haga clic con el botón secundario en el servidor dentro de un grupo y seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9186e-156">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="9186e-157">(También puede seleccionar el servidor y, a continuación, hacer clic en **Editar propiedades** en el menú **acción** ).</span><span class="sxs-lookup"><span data-stu-id="9186e-157">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="9186e-158">En la ventana **Editar propiedades**, seleccione la configuración de dirección IP que quiera admitir.</span><span class="sxs-lookup"><span data-stu-id="9186e-158">In the **Edit Properties** window, select the IP address configuration that you want to support.</span></span>

3. <span data-ttu-id="9186e-159">Es preciso proporcionar las direcciones internas y externas apropiadas para cada tipo de dirección que seleccione.</span><span class="sxs-lookup"><span data-stu-id="9186e-159">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>
