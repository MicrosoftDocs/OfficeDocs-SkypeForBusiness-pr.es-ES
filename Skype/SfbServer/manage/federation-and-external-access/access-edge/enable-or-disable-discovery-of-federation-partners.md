---
title: Habilitar o deshabilitar la detección de socios de federación
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En el momento en que implementan los servidores perimetrales y habilitado la federación para su organización, debe ha especificado si desea admitir la detección automática de dominios de socios federados.
ms.openlocfilehash: de61d8180a8f4e8f8be13abaab3d8911d2c6e22c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888001"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a><span data-ttu-id="8f94c-103">Habilitar o deshabilitar la detección de los socios de federación de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8f94c-103">Enable or disable discovery of federation partners in Skype for Business Server</span></span>

<span data-ttu-id="8f94c-104">En el momento en que implementan los servidores perimetrales y habilitado la federación para su organización, debe ha especificado si desea admitir la detección automática de dominios de socios federados.</span><span class="sxs-lookup"><span data-stu-id="8f94c-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains.</span></span> <span data-ttu-id="8f94c-105">Use el procedimiento de este tema para cambiar dicha configuración.</span><span class="sxs-lookup"><span data-stu-id="8f94c-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]  
> <span data-ttu-id="8f94c-106">El siguiente procedimiento se supone que ya ha habilitado la federación para su organización.</span><span class="sxs-lookup"><span data-stu-id="8f94c-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="8f94c-107">Para obtener información detallada acerca de cómo habilitar la federación, vea [Habilitar o deshabilitar el acceso de usuarios remotos](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="8f94c-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="8f94c-108">Para habilitar o deshabilitar la detección automática de dominios federados para la organización</span><span class="sxs-lookup"><span data-stu-id="8f94c-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="8f94c-109">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="8f94c-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8f94c-110">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="8f94c-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="8f94c-111">En la barra de navegación izquierda, haga clic en **Acceso de usuarios externos**, haga clic en **Configuración perimetral de acceso**.</span><span class="sxs-lookup"><span data-stu-id="8f94c-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="8f94c-112">En la página **Configuración perimetral de acceso** , haga clic en **Global**, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="8f94c-112">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="8f94c-113">En **Editar configuración perimetral de acceso**, en **Habilitar las comunicaciones con los usuarios federados**, active o desactive la casilla de verificación **Habilitar la detección de dominio de socio** para habilitar o deshabilitar la detección automática de dominios de socios.</span><span class="sxs-lookup"><span data-stu-id="8f94c-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="8f94c-114">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8f94c-114">Click **Commit**.</span></span>

<span data-ttu-id="8f94c-115">Para habilitar los usuarios federados puedan colaborar con los usuarios de su Skype para la implementación de Business Server, debe haber configurado también al menos una directiva de acceso externo para admitir el acceso de usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="8f94c-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="8f94c-116">Para obtener información detallada, vea [Habilitar o deshabilitar la federación y la conectividad de mensajería instantánea pública](enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="8f94c-116">For details, see [Enable or disable federation and public IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md).</span></span> <span data-ttu-id="8f94c-117">Para obtener información detallada acerca de cómo controlar el acceso de dominios federados concretos, vea [Administrar SIP dominios federados](../sip-domains/manage-sip-federated-domains-for-your-organization.md) y [Administrar SIP proveedores federados](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="8f94c-117">For details about controlling access for specific federated domains, see [Manage SIP federated domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md) and [Manage SIP federated providers](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8f94c-118">Habilitar o deshabilitar la detección de socios federados mediante el uso de cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f94c-118">Enabling or disabling discovery of federation partners by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="8f94c-119">Detección de socios federados se puede administrar mediante Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="8f94c-119">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="8f94c-120">Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f94c-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="8f94c-121">Para habilitar la detección de los socios federados</span><span class="sxs-lookup"><span data-stu-id="8f94c-121">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="8f94c-122">Para habilitar la detección de socios federados, establezca el valor de la propiedad **EnablePartnerDiscovery** en True ($True).</span><span class="sxs-lookup"><span data-stu-id="8f94c-122">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="8f94c-123">Tenga en cuenta que debe habilitar DNS SRV enrutamiento con el fin de cambiar este valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="8f94c-123">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="8f94c-124">Para deshabilitar la detección de socios federados</span><span class="sxs-lookup"><span data-stu-id="8f94c-124">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="8f94c-125">Para deshabilitar la detección de socios federados, establezca el valor de la propiedad **EnablePartnerDiscovery** en False ($False):</span><span class="sxs-lookup"><span data-stu-id="8f94c-125">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

