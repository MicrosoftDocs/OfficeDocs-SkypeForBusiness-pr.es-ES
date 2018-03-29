---
title: Crear vínculos de regiones de red en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Crear o modificar vínculos de región de red, que son utilizados por el control de admisión de llamadas de Telefonía IP empresarial en Skype para Business Server.
ms.openlocfilehash: f2b9ba5d6ccf2c2648bf755306001350f82c2931
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-network-region-links-in-skype-for-business-server-2015"></a><span data-ttu-id="70902-103">Crear vínculos de regiones de red en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="70902-103">Create network region links in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="70902-104">Crear o modificar vínculos de región de red, que son utilizados por el control de admisión de llamadas de Telefonía IP empresarial en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="70902-104">Create or modify network region links, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="70902-105">Las regiones de una red se vinculan mediante conexiones de red WAN físicas.</span><span class="sxs-lookup"><span data-stu-id="70902-105">Regions within a network are linked through physical WAN connectivity.</span></span> <span data-ttu-id="70902-106">Un vínculo de la región de red crea un vínculo entre dos regiones configurado para Control de admisión llamar (CAC) y establece las limitaciones de ancho de banda en el tráfico de audio y vídeo entre estas regiones.</span><span class="sxs-lookup"><span data-stu-id="70902-106">A network region link creates a link between two regions configured for Call Admission Control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>
  
<span data-ttu-id="70902-107">La topología de ejemplo tiene un vínculo entre las regiones de Norteamérica y APAC, y uno entre las regiones de EMEA y APAC.</span><span class="sxs-lookup"><span data-stu-id="70902-107">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="70902-108">Cada uno de estos vínculos de región está limitado por el ancho de banda WAN, como se describe en la tabla de información de ancho de banda del vínculo de región en [ejemplo: recopilación de requisitos para el control de admisión de llamada en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70902-108">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in [Example: Gathering requirements for call admission control in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="70902-109">Para crear vínculos de red de área mediante Skype para el Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="70902-109">To create network region links by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="70902-110">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="70902-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="70902-p103">Ejecute el cmdlet New-CsNetworkRegionLink para crear vínculos de región de red y aplicar los correspondientes perfiles de directiva de ancho de banda. Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="70902-p103">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles. For example, run:</span></span>
    
   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="70902-113">Para crear vínculos de red de área mediante Skype para Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="70902-113">To create network region links by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="70902-114">Abre Skype para Panel de Control del servidor de empresa.</span><span class="sxs-lookup"><span data-stu-id="70902-114">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="70902-115">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="70902-115">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="70902-116">Haga clic en el botón de navegación **Vínculo de región**.</span><span class="sxs-lookup"><span data-stu-id="70902-116">Click the **Region Link** navigation button.</span></span>
    
4. <span data-ttu-id="70902-117">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="70902-117">Click **New**.</span></span>
    
5. <span data-ttu-id="70902-118">En la página **Nuevo vínculo de región**, haga clic en **Nombre** y asigne un nombre al vínculo de región de red.</span><span class="sxs-lookup"><span data-stu-id="70902-118">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>
    
6. <span data-ttu-id="70902-119">Haga clic en **Región de red #1** y, en la lista, seleccione la región de red que desea vincular con Región de red #2.</span><span class="sxs-lookup"><span data-stu-id="70902-119">Click **Network Region #1**, and then click the network region in the list that you want to link to Network Region #2.</span></span>
    
7. <span data-ttu-id="70902-120">Haga clic en **Región de red #2** y, en la lista, seleccione la región de red que desea vincular con Región de red #1.</span><span class="sxs-lookup"><span data-stu-id="70902-120">Click **Network Region #2**, and then click a network region in the list that you want to link to Network Region #1.</span></span>
    
8. <span data-ttu-id="70902-121">También puede hacer clic en **Directiva de ancho de banda** y seleccionar el perfil de directiva de ancho de banda que desea aplicar al vínculo de región de red.</span><span class="sxs-lookup"><span data-stu-id="70902-121">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="70902-122">Aplique una directiva de ancho de banda únicamente si el vínculo de región de red tiene restricciones de ancho de banda y desea usar control de admisión de llamadas para controlar el tráfico de medios en ese vínculo.</span><span class="sxs-lookup"><span data-stu-id="70902-122">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span> 
  
9. <span data-ttu-id="70902-123">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="70902-123">Click **Commit**.</span></span>
    
10. <span data-ttu-id="70902-124">Para terminar de crear vínculos de región de red para la topología, repita los pasos del 4 al 9 con parámetros para otras regiones.</span><span class="sxs-lookup"><span data-stu-id="70902-124">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="70902-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="70902-125">See also</span></span>

#### 

[<span data-ttu-id="70902-126">Nueva CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="70902-126">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="70902-127">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="70902-127">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="70902-128">Conjunto de CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="70902-128">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="70902-129">Quitar CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="70902-129">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)

