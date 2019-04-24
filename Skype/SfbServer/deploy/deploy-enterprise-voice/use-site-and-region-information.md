---
title: Configurar la configuración global de desvío de medios en Skype para Business Server usar la información de sitio y región
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Configurar el desvío de medios que se usará para sólo ciertos sitios y regiones en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 93cc6bea9a4f130bd4b2c0e455b979b477888eeb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222572"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a><span data-ttu-id="0fe98-103">Configurar la configuración global de desvío de medios en Skype para Business Server usar la información de sitio y región</span><span class="sxs-lookup"><span data-stu-id="0fe98-103">Configure media bypass global settings in Skype for Business Server to use site and region information</span></span>
 
<span data-ttu-id="0fe98-104">Configurar el desvío de medios que se usará para sólo ciertos sitios y regiones en Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="0fe98-104">Configure media bypass to be used for only certain sites and regions in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="0fe98-105">Si usa el desvío de los pasos descritos en este tema para establecer la configuración global para los medios, la suposición es que no tienen una buena conectividad entre todos los Skype para los extremos de negocio y cualquier elemento del mismo nivel para los que ha configurado el desvío de medios en la conexión del tronco.</span><span class="sxs-lookup"><span data-stu-id="0fe98-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you do not have good connectivity between all Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0fe98-p101">La información de región de red y sitio de red se comparte entre las características de Enterprise Voice avanzadas del control de admisión de llamadas y el desvío de medios cuando ambos están habilitados. Por consiguiente, si ya ha configurado el control de admisión de llamadas, no es necesario que realice el siguiente procedimiento para editar la información de región y sitio específica para la omisión de medios. Siga los pasos de este procedimiento si todavía no ha configurado los sitios y regiones de red para el control de admisión de llamadas y desea cambiar las opciones del omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="0fe98-p101">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled. Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass. Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span> 
  
<span data-ttu-id="0fe98-109">El desvío de medios para que funcione correctamente debe haber coherencia entre un sitio como se define en el generador de topología y tal y como se define al configurar regiones de red y sitios de red.</span><span class="sxs-lookup"><span data-stu-id="0fe98-109">For media bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="0fe98-110">Por ejemplo, si tiene un sitio de sucursal que definido en el generador con sólo una puerta de enlace RTC implementada, a continuación, ese sitio de sucursal debe estar configurado con una directiva de Enterprise Voice que permite a los usuarios del sitio de sucursal tiene sus llamadas RTC se enrutan a través de la RTC puerta de enlace en el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="0fe98-110">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="0fe98-111">Configurar la información de sitio y región para el desvío de medios</span><span class="sxs-lookup"><span data-stu-id="0fe98-111">To Configure Site and Region Information for Media Bypass</span></span>

1. <span data-ttu-id="0fe98-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="0fe98-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
2. <span data-ttu-id="0fe98-113">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="0fe98-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="0fe98-114">Haga doble clic en la configuración **Global** de la tabla.</span><span class="sxs-lookup"><span data-stu-id="0fe98-114">Double-click the **Global** configuration in the table.</span></span>
    
4. <span data-ttu-id="0fe98-115">En la página **Editar configuración global**, seleccione la casilla **Habilitar omisión de medios**.</span><span class="sxs-lookup"><span data-stu-id="0fe98-115">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="0fe98-116">Haga clic en **Usar la configuración de sitios y regiones**.</span><span class="sxs-lookup"><span data-stu-id="0fe98-116">Click **Use sites and region configuration**.</span></span>
    
6. <span data-ttu-id="0fe98-117">Si es necesario, seleccione la casilla **Habilitar omisión para sitios sin asignar**.</span><span class="sxs-lookup"><span data-stu-id="0fe98-117">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0fe98-p103">Seleccione esta casilla solamente si dispone de uno o más sitios grandes asociados a la misma región que no tengan restricciones de ancho de banda (por ejemplo, un sitio central grande) y si dispone también de algunas sucursales asociadas con la misma región que no tienen restricciones de ancho de banda. Cuando habilita la omisión para sitios sin asignar, la configuración se simplifica ya que solo especifica subredes asociadas con las sucursales, en lugar de tener que especificar todas las subredes asociadas a todos los sitios. Se recomienda no activar esta casilla si se ha habilitado el control de admisión de llamadas.</span><span class="sxs-lookup"><span data-stu-id="0fe98-p103">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints. When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites. We recommend that you do not select this check box if call admission control is enabled.</span></span> 
  
7. <span data-ttu-id="0fe98-121">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="0fe98-121">Click **Commit**.</span></span>
    
<span data-ttu-id="0fe98-p104">A continuación, agregue subredes al sitio de red, como se describe en [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets). Cuando haya asociado todas las subredes a sitios de red, la implementación de la omisión de medios habrá finalizado.</span><span class="sxs-lookup"><span data-stu-id="0fe98-p104">Next, add subnets to the network site, as described in [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets). After you associate all subnets with network sites, media bypass deployment is complete.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="0fe98-124">Si todavía no ha creado regiones de red y sitios de red, deberá crearlos en primer lugar para poder continuar con la implementación de la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="0fe98-124">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="0fe98-125">Para obtener información detallada, consulte [Deploy regiones de red, sitios y las subredes de Skype para la empresa](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="0fe98-125">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0fe98-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="0fe98-126">See also</span></span>

[<span data-ttu-id="0fe98-127">Associate a subnet with a network site</span><span class="sxs-lookup"><span data-stu-id="0fe98-127">Associate a subnet with a network site</span></span>](deploy-network.md#BKMK_AssociateSubnets)

