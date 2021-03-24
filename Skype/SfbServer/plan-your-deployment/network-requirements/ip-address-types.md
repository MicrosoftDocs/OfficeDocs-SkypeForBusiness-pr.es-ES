---
title: Configurar tipos de direcciones IP en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 'Summary: Review the IP Address type considerations below before implementing Skype for Business Server.'
ms.openlocfilehash: ba10dd223e7e099d27e31bddce478603f50e49a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101256"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a><span data-ttu-id="66154-103">Configurar tipos de direcciones IP en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="66154-103">Configure IP address types in Skype for Business</span></span>

<span data-ttu-id="66154-104">**Resumen:** Revise las consideraciones de tipo de dirección IP que se indican a continuación antes de implementar Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="66154-104">**Summary:** Review the IP Address type considerations below before implementing Skype for Business Server.</span></span>

<span data-ttu-id="66154-105">Los tipos de direcciones IP se implementan mediante la configuración de topología que se configura en el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="66154-105">You deploy IP address types by using topology settings that you configure in Topology Builder.</span></span> <span data-ttu-id="66154-106">En esta sección se describe cómo implementar tipos de direcciones IP en servidores front-end, servidores de mediación y servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="66154-106">This section describes how to deploy IP address types on Front End Servers, Mediation Servers, and Edge Servers.</span></span>

## <a name="deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="66154-107">Implementar tipos de direcciones IP en un servidor front-end</span><span class="sxs-lookup"><span data-stu-id="66154-107">Deploy IP address types on a Front End Server</span></span>

<span data-ttu-id="66154-108">Con el Generador de topologías, realice los pasos del siguiente procedimiento para implementar tipos de direcciones IP en un servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="66154-108">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="66154-109">Para implementar los tipos de direcciones IP en un servidor front-end</span><span class="sxs-lookup"><span data-stu-id="66154-109">To deploy IP address types on a Front End Server</span></span>

1. <span data-ttu-id="66154-p102">En **Grupo de servidores front-end Enterprise Edition**, haga clic con el botón secundario dentro de un grupo y seleccione **Editar propiedades**. (También puede seleccionar el servidor y hacer clic en **Editar propiedades** en el menú **Acción**).</span><span class="sxs-lookup"><span data-stu-id="66154-p102">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**. (Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="66154-112">En el cuadro de diálogo **Editar propiedades**, seleccione el tipo de dirección IP que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="66154-112">In the **Edit Properties** dialog box, select the IP address type that you want to configure.</span></span> <span data-ttu-id="66154-113">Para una configuración de doble pila, seleccione **Habilitar IPv4** y **Habilitar IPv6**.</span><span class="sxs-lookup"><span data-stu-id="66154-113">For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**.</span></span>

   <span data-ttu-id="66154-114">**Cuadro de diálogo Editar propiedades para el grupo de servidores front-end**</span><span class="sxs-lookup"><span data-stu-id="66154-114">**Edit Properties dialog box for the Front End Server pool**</span></span>

   - <span data-ttu-id="66154-p104">**Use todas las direcciones IP configuradas**. Seleccione esta opción si desea que se usen todas las direcciones IP definidas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="66154-p104">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

     > [!NOTE]
     > <span data-ttu-id="66154-117">Esta es la opción recomendada para la configuración para IP versión 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="66154-117">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

   - <span data-ttu-id="66154-p105">**Limitar el uso del servicio a las direcciones IP seleccionadas**. Seleccione esta opción para determinar una dirección específica en el servidor nuevo. Si selecciona esta opción, debe introducir un valor para la **dirección IP principal**.</span><span class="sxs-lookup"><span data-stu-id="66154-p105">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for **Primary IP address**.</span></span>

   - <span data-ttu-id="66154-p106">**Dirección IP principal**. Introduzca una dirección IP que el servidor usará para todas las comunicaciones excepto para red telefónica conmutada (RTC). La dirección IP introducida debe coincidir con el formato del tipo de dirección seleccionado.</span><span class="sxs-lookup"><span data-stu-id="66154-p106">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

   - <span data-ttu-id="66154-p107">**Dirección IP de RTC**. Defina una dirección IP para la RTC cuando asigne un servidor de mediación en el servidor front-end. Esta dirección debe coincidir con el formato del tipo de dirección seleccionado.</span><span class="sxs-lookup"><span data-stu-id="66154-p107">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>

> [!NOTE]
> <span data-ttu-id="66154-127">No se admite la instalación de tarjetas de interfaz de red (NIC) adicionales para admitir la configuración de direcciones IP RTC (o por cualquier otro motivo) en servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="66154-127">The installation of additional network interface cards (NICs) to support the PSTN IP address configuration (or for any other reason) on Front End Servers is not supported.</span></span> <span data-ttu-id="66154-128">Para obtener más información acerca de las configuraciones de NIC admitidas para Skype Empresarial Server, vea Plataformas de hardware de servidor para [Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms).</span><span class="sxs-lookup"><span data-stu-id="66154-128">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms).</span></span>

## <a name="deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="66154-129">Implementar tipos de direcciones IP en un servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="66154-129">Deploy IP address types on a Mediation Server</span></span>

<span data-ttu-id="66154-130">Con el Generador de topologías, realice los pasos del siguiente procedimiento para implementar tipos de direcciones IP en un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="66154-130">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="66154-131">Para implementar tipos de direcciones IP en un servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="66154-131">To deploy IP address types on a Mediation Server</span></span>

- <span data-ttu-id="66154-132">En el Generador de topologías, en **Grupos de servidores de mediación,** haga clic con el botón secundario en el servidor de un grupo de servidores y, a continuación, seleccione Editar **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="66154-132">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="66154-133">(También puede seleccionar el servidor y hacer clic en **Editar propiedades** en el menú **Acción**).</span><span class="sxs-lookup"><span data-stu-id="66154-133">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

- <span data-ttu-id="66154-p110">En el cuadro de diálogo **Editar propiedades**, seleccione el tipo de dirección IP que desea configurar. Para establecer una configuración de doble pila, seleccione **Habilitar IPv4** y **Habilitar IPv6**, como se muestra en la figura siguiente.</span><span class="sxs-lookup"><span data-stu-id="66154-p110">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>

   <span data-ttu-id="66154-136">**Cuadro de diálogo Editar propiedades para el grupo Servidor de mediación**</span><span class="sxs-lookup"><span data-stu-id="66154-136">**Edit Properties dialog box for the Mediation Server pool**</span></span>

  - <span data-ttu-id="66154-p111">**Use todas las direcciones IP configuradas**. Seleccione esta opción si desea que se usen todas las direcciones IP definidas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="66154-p111">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

    > [!NOTE]
    > <span data-ttu-id="66154-139">Esta es la opción recomendada para las configuraciones de IP versión 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="66154-139">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

  - <span data-ttu-id="66154-p112">**Limitar el uso del servicio a las direcciones especificadas**. Seleccione esta opción para especificar una dirección concreta para usarla en el nuevo servidor. Si selecciona esta opción, debe indicar un valor de dirección IP principal.</span><span class="sxs-lookup"><span data-stu-id="66154-p112">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>

  - <span data-ttu-id="66154-p113">**Dirección IP principal**. Escriba una dirección IP que va a utilizar el servidor para todas las comunicaciones excepto la red telefónica conmutada (RTC) pública. La dirección IP escrita debe coincidir con el formato del tipo de dirección seleccionado.</span><span class="sxs-lookup"><span data-stu-id="66154-p113">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

  - <span data-ttu-id="66154-p114">**Dirección IP de RTC**. Defina una dirección IP para la RTC cuando asigne un servidor de mediación en el servidor front-end. Esta dirección debe coincidir con el formato del tipo de dirección seleccionado.</span><span class="sxs-lookup"><span data-stu-id="66154-p114">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="66154-149">Solo se admiten dos tarjetas de red en *servidores de* mediación dedicados.</span><span class="sxs-lookup"><span data-stu-id="66154-149">We only support two network cards on *dedicated* Mediation Servers.</span></span> <span data-ttu-id="66154-150">Si el rol Servidor de mediación está situado en front-end, no se admiten tarjetas de red duales.</span><span class="sxs-lookup"><span data-stu-id="66154-150">If the Mediation Sserver role is collocated on the Front End, then dual network cards are not supported.</span></span> 

> [!NOTE]
> - <span data-ttu-id="66154-151">Para obtener más información acerca de las configuraciones de NIC compatibles para Skype Empresarial Server 2015, vea [Hardware for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="66154-151">For more information about supported NIC configurations for Skype for Business Server 2015, see [Hardware for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span></span>
> - <span data-ttu-id="66154-152">Para obtener más información acerca de las configuraciones de NIC compatibles para Skype Empresarial Server 2019, vea [Hardware for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span><span class="sxs-lookup"><span data-stu-id="66154-152">For more information about supported NIC configurations for Skype for Business Server 2019, see [Hardware for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span></span>



## <a name="deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="66154-153">Implementar tipos de direcciones IP en un servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="66154-153">Deploy IP address types on an Edge Server</span></span>

<span data-ttu-id="66154-154">Con el Generador de topologías, realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="66154-154">Using Topology Builder, perform the following steps:</span></span>

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="66154-155">Para implementar tipos de direcciones IP en un servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="66154-155">To deploy IP address types on an Edge Server</span></span>

1. <span data-ttu-id="66154-156">En el Generador de topologías, en **Grupos perimetrales,** haga clic con el botón secundario en el servidor de un grupo de servidores y, a continuación, **seleccione Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="66154-156">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="66154-157">(También puede seleccionar el servidor y hacer clic en **Editar propiedades** en el menú **Acción**).</span><span class="sxs-lookup"><span data-stu-id="66154-157">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="66154-158">En la ventana **Editar propiedades**, seleccione la configuración de dirección IP que quiera admitir.</span><span class="sxs-lookup"><span data-stu-id="66154-158">In the **Edit Properties** window, select the IP address configuration that you want to support.</span></span>

3. <span data-ttu-id="66154-159">Debe proporcionar las direcciones internas y externas apropiadas para cada tipo de dirección que seleccione.</span><span class="sxs-lookup"><span data-stu-id="66154-159">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>