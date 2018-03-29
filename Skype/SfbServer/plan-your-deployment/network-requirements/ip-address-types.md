---
title: Configurar tipos de dirección IP en Skype Empresarial
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/22/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 'Resumen: Revisar las consideraciones de tipo de dirección IP a continuación antes de implementar Skype para Business Server 2015.'
ms.openlocfilehash: facfff432cfcde74af737b5a7c5db87d36f3eb41
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-ip-address-types-in-skype-for-business"></a><span data-ttu-id="0847b-103">Configurar tipos de dirección IP en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="0847b-103">Configure IP address types in Skype for Business</span></span>
 
<span data-ttu-id="0847b-104">**Resumen:** Revisar las consideraciones de tipo de dirección IP a continuación antes de implementar Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0847b-104">**Summary:** Review the IP Address type considerations below before implementing Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="0847b-105">Implementar tipos de direcciones IP mediante la configuración de la topología que se configura en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="0847b-105">You deploy IP address types by using topology settings that you configure in Topology Builder.</span></span> <span data-ttu-id="0847b-106">En esta sección se describe cómo implementar tipos de direcciones IP en los servidores frontales, los servidores de mediación y servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="0847b-106">This section describes how to deploy IP address types on Front End Servers, Mediation Servers, and Edge Servers.</span></span>
  
## <a name="deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="0847b-107">Implementar tipos de direcciones IP en un servidor front-end</span><span class="sxs-lookup"><span data-stu-id="0847b-107">Deploy IP address types on a Front End Server</span></span>

<span data-ttu-id="0847b-108">Con el generador de topología, realice los pasos del procedimiento siguiente para implementar tipos de direcciones IP en un servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="0847b-108">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>
  
### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="0847b-109">Para implementar los tipos de direcciones IP en un servidor front-end</span><span class="sxs-lookup"><span data-stu-id="0847b-109">To deploy IP address types on a Front End Server</span></span>

1. <span data-ttu-id="0847b-p102">En **Grupo de servidores front-end Enterprise Edition**, haga clic con el botón secundario dentro de un grupo y seleccione **Editar propiedades** (también puede seleccionar el servidor y hacer clic en **Editar propiedades** en el menú **Acción**).</span><span class="sxs-lookup"><span data-stu-id="0847b-p102">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**. (Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>
    
2. <span data-ttu-id="0847b-p103">En el cuadro de diálogo **Editar propiedades**, seleccione el tipo de dirección IP que desea configurar. Para establecer una configuración de doble pila, seleccione **Habilitar IPv4** y **Habilitar IPv6**, como se muestra en la figura siguiente.</span><span class="sxs-lookup"><span data-stu-id="0847b-p103">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
   <span data-ttu-id="0847b-114">**Editar el cuadro de diálogo Propiedades para el grupo de servidor Front-End**</span><span class="sxs-lookup"><span data-stu-id="0847b-114">**Edit Properties dialog box for the Front End Server pool**</span></span>

  - <span data-ttu-id="0847b-p104">**Usar todas las direcciones IP configuradas**. Seleccione esta opción si desea que se usen todas las direcciones IP definidas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="0847b-p104">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="0847b-117">Esta es la opción recomendada para la configuración para IP versión 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="0847b-117">This is the recommended option for IP version 6 (IPv6) configurations.</span></span> 
  
  - <span data-ttu-id="0847b-p105">**Limitar el uso del servicio a las direcciones IP seleccionadas**. Seleccione esta opción para determinar una dirección específica en el servidor nuevo. Si selecciona esta opción, necesita introducir un valor para la **dirección IP principal**.</span><span class="sxs-lookup"><span data-stu-id="0847b-p105">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for **Primary IP address**.</span></span>
    
  - <span data-ttu-id="0847b-p106">**Dirección IP principal**. Introduzca una dirección IP que el servidor usará para todas las comunicaciones excepto para red telefónica conmutada (RTC). La dirección IP introducida necesita coincidir con el formato del tipo de dirección seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0847b-p106">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
  - <span data-ttu-id="0847b-p107">**Dirección IP de RTC**. Defina una dirección IP para la RTC cuando asigne un servidor de mediación en el servidor front-end. Esta dirección necesita coincidir con el formato del tipo de dirección seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0847b-p107">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0847b-127">No se admite la instalación de tarjetas de interfaz de red adicionales (NIC) para admitir la configuración de direcciones IP PSTN en servidores frontales.</span><span class="sxs-lookup"><span data-stu-id="0847b-127">The installation of additional network interface cards (NICs) to support the PSTN IP address configuration on Front End Servers is not supported.</span></span> <span data-ttu-id="0847b-128">Para obtener más información acerca de configuraciones compatibles de NIC para Skype para Business Server, vea [plataformas de hardware de servidor para Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span><span class="sxs-lookup"><span data-stu-id="0847b-128">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span></span> 
  
## <a name="deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="0847b-129">Implementar tipos de dirección IP en un servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="0847b-129">Deploy IP address types on a Mediation Server</span></span>

<span data-ttu-id="0847b-130">Con el generador de topología, realice los pasos del procedimiento siguiente para implementar tipos de direcciones IP en un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="0847b-130">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>
  
### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="0847b-131">Para implementar tipos de direcciones IP en un servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="0847b-131">To deploy IP address types on a Mediation Server</span></span>

- <span data-ttu-id="0847b-132">Generador de topología, en **grupos de mediación**, (ratón) en el servidor dentro de un grupo y, a continuación, seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0847b-132">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="0847b-133">(Como alternativa, seleccione el servidor y, a continuación, haga clic en **Editar propiedades** en el menú **acción** .)</span><span class="sxs-lookup"><span data-stu-id="0847b-133">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>
    
- <span data-ttu-id="0847b-p110">En el cuadro de diálogo **Editar propiedades**, seleccione el tipo de dirección IP que desea configurar. Para establecer una configuración de doble pila, seleccione **Habilitar IPv4** y **Habilitar IPv6**, como se muestra en la figura siguiente.</span><span class="sxs-lookup"><span data-stu-id="0847b-p110">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
   <span data-ttu-id="0847b-136">**Editar el cuadro de diálogo Propiedades para el grupo de servidor de mediación**</span><span class="sxs-lookup"><span data-stu-id="0847b-136">**Edit Properties dialog box for the Mediation Server pool**</span></span>

  - <span data-ttu-id="0847b-p111">**Usar todas las direcciones IP configuradas**. Seleccione esta opción si desea que se usen todas las direcciones IP definidas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="0847b-p111">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="0847b-139">Esta es la opción recomendada para la configuración para IP versión 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="0847b-139">This is the recommended option for IP version 6 (IPv6) configurations.</span></span> 
  
  - <span data-ttu-id="0847b-p112">**Limitar el uso del servicio a las direcciones IP seleccionadas**. Seleccione esta opción para determinar una dirección específica en el servidor nuevo. Si selecciona esta opción, necesita introducir un valor para la dirección IP principal.</span><span class="sxs-lookup"><span data-stu-id="0847b-p112">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>
    
  - <span data-ttu-id="0847b-p113">**Dirección IP principal**. Introduzca una dirección IP que el servidor usará para todas las comunicaciones excepto para red telefónica conmutada (RTC). La dirección IP introducida necesita coincidir con el formato del tipo de dirección seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0847b-p113">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
  - <span data-ttu-id="0847b-p114">**Dirección IP de RTC**. Defina una dirección IP para la RTC cuando asigne un servidor de mediación en el servidor front-end. Esta dirección necesita coincidir con el formato del tipo de dirección seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0847b-p114">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0847b-149">No se admite la instalación de NIC adicionales para admitir la configuración de direcciones IP PSTN en servidores independientes de mediación.</span><span class="sxs-lookup"><span data-stu-id="0847b-149">The installation of additional NICs to support the PSTN IP address configuration on stand-alone Mediation Servers is not supported.</span></span> <span data-ttu-id="0847b-150">Para obtener más información acerca de configuraciones compatibles de NIC para Skype para Business Server, vea [plataformas de hardware de servidor para Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span><span class="sxs-lookup"><span data-stu-id="0847b-150">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span></span> 
  
## <a name="deploy-ip-address-types-on-a-edge-server"></a><span data-ttu-id="0847b-151">Implementar tipos de dirección IP en un servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="0847b-151">Deploy IP address types on a Edge Server</span></span>

<span data-ttu-id="0847b-152">Con el generador de topología, realice los pasos del procedimiento siguiente para implementar tipos de direcciones IP en un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="0847b-152">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on an Edge Server.</span></span>
  
### <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="0847b-153">Para implementar tipos de direcciones IP en un servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="0847b-153">To deploy IP address types on an Edge Server</span></span>

1. <span data-ttu-id="0847b-154">Generador de topología, en **grupos de borde**, (ratón) en el servidor dentro de un grupo y, a continuación, seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0847b-154">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="0847b-155">(Como alternativa, seleccione el servidor y, a continuación, haga clic en **Editar propiedades** en el menú **acción** .)</span><span class="sxs-lookup"><span data-stu-id="0847b-155">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>
    
2. <span data-ttu-id="0847b-p117">En la ventana **Editar propiedades**, seleccione la configuración de dirección IP que quiera admitir. En las siguientes figuras se muestra una configuración de pila dual para la interfaz interna y la interfaz externa.</span><span class="sxs-lookup"><span data-stu-id="0847b-p117">In the **Edit Properties** window, select the IP address configuration that you want to support. The following figures show a dual stack configuration for the internal interface and the external interface.</span></span>
    
   <span data-ttu-id="0847b-158">**Doble interfaz interna del servidor perimetral de apilada**</span><span class="sxs-lookup"><span data-stu-id="0847b-158">**Dual stacked Edge Server internal interface**</span></span>

   <span data-ttu-id="0847b-159">**Apiladas servidor perimetral externo interfaz dual**</span><span class="sxs-lookup"><span data-stu-id="0847b-159">**Dual stacked Edge Server external interface**</span></span>

3. <span data-ttu-id="0847b-160">Es preciso proporcionar las direcciones internas y externas apropiadas para cada tipo de dirección que seleccione.</span><span class="sxs-lookup"><span data-stu-id="0847b-160">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>
    

