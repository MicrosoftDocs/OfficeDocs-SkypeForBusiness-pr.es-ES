---
title: Habilitar o deshabilitar la detección de socios de federación
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: En el momento en que implementa los servidores perimetrales y habilita la federación para la organización, debe especificar si se va a admitir la detección automática de los dominios de socios federados.
ms.openlocfilehash: e1f076b725dff149f024a3fd59f9f7d52da4e6a8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817430"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a><span data-ttu-id="91da3-103">Habilitar o deshabilitar la detección de socios de federación en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="91da3-103">Enable or disable discovery of federation partners in Skype for Business Server</span></span>

<span data-ttu-id="91da3-p101">En el momento en que implementa los servidores perimetrales y habilita la federación para la organización, debe especificar si se va a admitir la detección automática de los dominios de socios federados. Para cambiar esa configuración, siga el procedimiento de este tema.</span><span class="sxs-lookup"><span data-stu-id="91da3-p101">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains. Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]  
> <span data-ttu-id="91da3-106">En el procedimiento siguiente, se presupone que ya ha habilitado la federación para la organización.</span><span class="sxs-lookup"><span data-stu-id="91da3-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="91da3-107">Para obtener más información sobre cómo habilitar la federación, vea [Habilitar o deshabilitar el acceso de usuarios remotos.](enable-or-disable-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="91da3-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="91da3-108">Para habilitar o deshabilitar la detección automática de dominios federados para la organización</span><span class="sxs-lookup"><span data-stu-id="91da3-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="91da3-109">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="91da3-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="91da3-110">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="91da3-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="91da3-111">En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y en **Configuración perimetral de acceso**.</span><span class="sxs-lookup"><span data-stu-id="91da3-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="91da3-112">En la página **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y, a continuación en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="91da3-112">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="91da3-113">En **Editar configuración perimetral de acceso**, en **Habilitar comunicaciones con usuarios federados**, active o desactive la casilla **Habilitar detección de dominio de socio** para habilitar o deshabilitar la detección automática de dominios de socios.</span><span class="sxs-lookup"><span data-stu-id="91da3-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="91da3-114">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="91da3-114">Click **Commit**.</span></span>

<span data-ttu-id="91da3-115">Para permitir que los usuarios federados colaboren con usuarios en su implementación de Skype Empresarial Server, también debe haber configurado al menos una directiva de acceso externo para admitir el acceso de usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="91da3-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="91da3-116">Para obtener más información, consulte [Habilitar o deshabilitar la federación y la conectividad de mensajería instantánea pública.](enable-or-disable-federation-and-public-im-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="91da3-116">For details, see [Enable or disable federation and public IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md).</span></span> <span data-ttu-id="91da3-117">Para obtener más información sobre cómo controlar el acceso a dominios federados específicos, consulte Administrar dominios [federados SIP](../sip-domains/manage-sip-federated-domains-for-your-organization.md) y [Administrar proveedores federados SIP.](../sip-providers/manage-sip-federated-providers-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="91da3-117">For details about controlling access for specific federated domains, see [Manage SIP federated domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md) and [Manage SIP federated providers](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="91da3-118">Habilitar o deshabilitar la detección de socios de federación mediante cmdlets Windows PowerShell federación</span><span class="sxs-lookup"><span data-stu-id="91da3-118">Enabling or disabling discovery of federation partners by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="91da3-119">La detección de socios de federación se puede administrar mediante Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration federación.</span><span class="sxs-lookup"><span data-stu-id="91da3-119">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="91da3-120">Este cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91da3-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="91da3-121">Para habilitar la detección de socios de federación</span><span class="sxs-lookup"><span data-stu-id="91da3-121">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="91da3-p105">Para habilitar la detección de socios federados, establezca el valor de la propiedad **EnablePartnerDiscovery** en True ($True). Tenga en cuenta que debe habilitar el enrutamiento SRV de DNS para poder cambiar el valor de esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="91da3-p105">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True). Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="91da3-124">Para deshabilitar la detección de socios de federación</span><span class="sxs-lookup"><span data-stu-id="91da3-124">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="91da3-125">Para deshabilitar la detección de socios federados, establezca el valor de la propiedad **EnablePartnerDiscovery** en False ($False).</span><span class="sxs-lookup"><span data-stu-id="91da3-125">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

