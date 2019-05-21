---
title: Habilitar o deshabilitar la detección de socios de federación
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En el momento de implementar los servidores perimetrales y de habilitar la Federación de su organización, debe haber especificado si se debe admitir la detección automática de dominios federados de socios.
ms.openlocfilehash: a5569639cf870d2a5da16ef81aa733724a6701b3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280260"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a><span data-ttu-id="bc9ab-103">Habilitar o deshabilitar la detección de socios de Federación en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="bc9ab-103">Enable or disable discovery of federation partners in Skype for Business Server</span></span>

<span data-ttu-id="bc9ab-104">En el momento de implementar los servidores perimetrales y de habilitar la Federación de su organización, debe haber especificado si se debe admitir la detección automática de dominios federados de socios.</span><span class="sxs-lookup"><span data-stu-id="bc9ab-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains.</span></span> <span data-ttu-id="bc9ab-105">Use el procedimiento de este tema para cambiar esa configuración.</span><span class="sxs-lookup"><span data-stu-id="bc9ab-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]  
> <span data-ttu-id="bc9ab-106">En el procedimiento siguiente se supone que ya ha habilitado la Federación de su organización.</span><span class="sxs-lookup"><span data-stu-id="bc9ab-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="bc9ab-107">Para obtener más información sobre cómo habilitar la Federación, consulte [habilitar o deshabilitar el acceso de usuarios remotos](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="bc9ab-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="bc9ab-108">Para habilitar o deshabilitar la detección automática de dominios federados para su organización</span><span class="sxs-lookup"><span data-stu-id="bc9ab-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="bc9ab-109">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="bc9ab-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bc9ab-110">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="bc9ab-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="bc9ab-111">En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**, haga clic en **configuración del borde de Access**.</span><span class="sxs-lookup"><span data-stu-id="bc9ab-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="bc9ab-112">En la página **configuración de perímetro de Access** , haga clic en **global**, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="bc9ab-112">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="bc9ab-113">En **Editar configuración del límite de acceso**, en **habilitar las comunicaciones con usuarios federados**, Active o desactive la casilla **Habilitar la detección** de dominios asociados para habilitar o deshabilitar la detección automática de dominios asociados.</span><span class="sxs-lookup"><span data-stu-id="bc9ab-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="bc9ab-114">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="bc9ab-114">Click **Commit**.</span></span>

<span data-ttu-id="bc9ab-115">Para permitir a los usuarios federados colaborar con los usuarios de su implementación de Skype empresarial Server, también debe haber configurado al menos una directiva de acceso externa para admitir el acceso de usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="bc9ab-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="bc9ab-116">Para obtener más información, vea [habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública](enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="bc9ab-116">For details, see [Enable or disable federation and public IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md).</span></span> <span data-ttu-id="bc9ab-117">Para obtener más información sobre cómo controlar el acceso a determinados dominios federados, consulte [administrar dominios federados SIP](../sip-domains/manage-sip-federated-domains-for-your-organization.md) y [administrar proveedores federados de SIP](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="bc9ab-117">For details about controlling access for specific federated domains, see [Manage SIP federated domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md) and [Manage SIP federated providers](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="bc9ab-118">Habilitar o deshabilitar la detección de socios de Federación mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc9ab-118">Enabling or disabling discovery of federation partners by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="bc9ab-119">El descubrimiento de los socios de la Federación se puede administrar mediante Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="bc9ab-119">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="bc9ab-120">Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bc9ab-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="bc9ab-121">Para habilitar la detección de socios de Federación</span><span class="sxs-lookup"><span data-stu-id="bc9ab-121">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="bc9ab-122">Para habilitar la detección de socios de Federación, establezca el valor de la propiedad **EnablePartnerDiscovery** en True ($true).</span><span class="sxs-lookup"><span data-stu-id="bc9ab-122">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="bc9ab-123">Tenga en cuenta que debe habilitar el enrutamiento SRV de DNS para poder cambiar este valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="bc9ab-123">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="bc9ab-124">Para deshabilitar la detección de socios de Federación</span><span class="sxs-lookup"><span data-stu-id="bc9ab-124">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="bc9ab-125">Para deshabilitar la detección de socios de Federación, establezca el valor de la propiedad **EnablePartnerDiscovery** en False ($false):</span><span class="sxs-lookup"><span data-stu-id="bc9ab-125">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

