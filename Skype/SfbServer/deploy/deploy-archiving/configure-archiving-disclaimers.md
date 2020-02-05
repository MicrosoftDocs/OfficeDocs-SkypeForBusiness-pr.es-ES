---
title: Configurar descargos de responsabilidad de archivado para usuarios externos en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 'Resumen: Lea este tema para obtener información sobre cómo configurar una renuncia de archivado para Skype empresarial Server.'
ms.openlocfilehash: a9ffece1cefbf58b5731ce37f209733454ed1eee
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769043"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a><span data-ttu-id="d95cb-103">Configurar descargos de responsabilidad de archivado para usuarios externos en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d95cb-103">Configure archiving disclaimers for external users in Skype for Business Server</span></span>
 
<span data-ttu-id="d95cb-104">**Resumen:** Lea este tema para obtener información sobre cómo configurar una renuncia de archivado para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d95cb-104">**Summary:** Read this topic to learn how to configure an archiving disclaimer for Skype for Business Server.</span></span>
  
<span data-ttu-id="d95cb-105">Si su organización se comunica con socios externos, necesita informarles que las comunicaciones con ellos se archivan.</span><span class="sxs-lookup"><span data-stu-id="d95cb-105">If your organization communicates with external partners, you need to let them know that you are archiving communications with them.</span></span> <span data-ttu-id="d95cb-106">Al implementar un servidor perimetral y habilitar la Federación de su organización, se le preguntará si desea enviar automáticamente una renuncia de archivado a los socios externos.</span><span class="sxs-lookup"><span data-stu-id="d95cb-106">When you deploy an Edge Server and enable federation for your organization, you are asked whether you want to automatically send an archiving disclaimer to external partners.</span></span> 
  
<span data-ttu-id="d95cb-107">Si necesita cambiar esta configuración, puede usar el panel de control de Skype empresarial Server o el cmdlet **set-CsAccessEdgeConfiguration de** Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d95cb-107">If you need to change this configuration, you can use the Skype for Business Server Control Panel or the Windows PowerShell **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="d95cb-108">Los cmdlets se pueden ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d95cb-108">Cmdlets can be run either from the Skype for Business Server management shell or from a remote session of Windows PowerShell.</span></span>
  
<span data-ttu-id="d95cb-109">Para permitir que los usuarios externos colaboren con los usuarios de su implementación de Skype empresarial Server, también debe configurar al menos una directiva de acceso externo para que admita el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="d95cb-109">To enable external users to collaborate with users in your Skype for Business Server deployment, you must also configure at least one external access policy to support external user access.</span></span> <span data-ttu-id="d95cb-110">Para obtener más información, vea administrar los socios de XMPP federados de su organización.</span><span class="sxs-lookup"><span data-stu-id="d95cb-110">For details, see Manage XMPP Federated Partners for Your Organization.</span></span> <span data-ttu-id="d95cb-111">Para más detalles sobre el control de acceso para dominios federados específicos, consulte Controlar el acceso por medio de los dominios federados individuales.</span><span class="sxs-lookup"><span data-stu-id="d95cb-111">For details about controlling access for specific federated domains, see Control Access by Individual Federated Domains.</span></span>
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a><span data-ttu-id="d95cb-112">Habilitar o deshabilitar la renuncia de archivado mediante el Panel de control</span><span class="sxs-lookup"><span data-stu-id="d95cb-112">Enable or disable archiving disclaimer using the Control Panel</span></span>

1. <span data-ttu-id="d95cb-113">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="d95cb-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d95cb-114">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d95cb-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d95cb-115">En la barra de navegación izquierda, haga clic en **Federación y acceso externo** y, luego, en **Configuración perimetral de acceso**.</span><span class="sxs-lookup"><span data-stu-id="d95cb-115">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>
    
4. <span data-ttu-id="d95cb-116">En la ficha **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="d95cb-116">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="d95cb-117">En **Editar configuración perimetral de acceso**, en **Habilitar federación y conectividad pública de mensajería instantánea**, active o desactive la casilla **Enviar declinación de responsabilidades de archivado a los socios federados** para habilitar o deshabilitar el envío automático de declinaciones de responsabilidades de archivado.</span><span class="sxs-lookup"><span data-stu-id="d95cb-117">In **Edit Access Edge Configuration**, under **Enable federation and public IM connectivity**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>
    
6. <span data-ttu-id="d95cb-118">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="d95cb-118">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a><span data-ttu-id="d95cb-119">Habilitar o deshabilitar la renuncia de archivado mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d95cb-119">Enable or disable archiving disclaimer using Windows PowerShell</span></span>

<span data-ttu-id="d95cb-120">Para habilitar la declinación de responsabilidades de archivado, establezca el valor de la propiedad **EnableArchivingDisclaimer** en True ($True):</span><span class="sxs-lookup"><span data-stu-id="d95cb-120">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

<span data-ttu-id="d95cb-121">Para deshabilitar la declinación de responsabilidades de archivado, establezca el valor de la propiedad **EnableArchivingDisclaimer** en False ($False):</span><span class="sxs-lookup"><span data-stu-id="d95cb-121">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


