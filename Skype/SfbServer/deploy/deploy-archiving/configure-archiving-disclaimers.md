---
title: Configurar avisos de declinación de responsabilidades de archivado para usuarios externos en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 'Resumen: lea este tema para obtener información sobre cómo configurar un aviso de declinación de responsabilidades de archivado para Skype Empresarial Server.'
ms.openlocfilehash: 055c94f0fba18dcd9de35ff5a73e37de0b45595b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820670"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a><span data-ttu-id="bd98c-103">Configurar avisos de declinación de responsabilidades de archivado para usuarios externos en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="bd98c-103">Configure archiving disclaimers for external users in Skype for Business Server</span></span>
 
<span data-ttu-id="bd98c-104">**Resumen:** Lea este tema para obtener información sobre cómo configurar un aviso de declinación de responsabilidades de archivado para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="bd98c-104">**Summary:** Read this topic to learn how to configure an archiving disclaimer for Skype for Business Server.</span></span>
  
<span data-ttu-id="bd98c-105">Si su organización se comunica con socios externos, debe comunicarles que está archivando las comunicaciones con ellos.</span><span class="sxs-lookup"><span data-stu-id="bd98c-105">If your organization communicates with external partners, you need to let them know that you are archiving communications with them.</span></span> <span data-ttu-id="bd98c-106">Al implementar un servidor perimetral y habilitar la federación para su organización, se le preguntará si desea enviar automáticamente un aviso de declinación de responsabilidades de archivado a socios externos.</span><span class="sxs-lookup"><span data-stu-id="bd98c-106">When you deploy an Edge Server and enable federation for your organization, you are asked whether you want to automatically send an archiving disclaimer to external partners.</span></span> 
  
<span data-ttu-id="bd98c-107">Si necesita cambiar esta configuración, puede usar el Panel de control de Skype Empresarial Server o el cmdlet **Windows PowerShell Set-CsAccessEdgeConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="bd98c-107">If you need to change this configuration, you can use the Skype for Business Server Control Panel or the Windows PowerShell **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="bd98c-108">Los cmdlets se pueden ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd98c-108">Cmdlets can be run either from the Skype for Business Server management shell or from a remote session of Windows PowerShell.</span></span>
  
<span data-ttu-id="bd98c-109">Para permitir que los usuarios externos colaboren con usuarios en su implementación de Skype Empresarial Server, también debe configurar al menos una directiva de acceso externo para admitir el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="bd98c-109">To enable external users to collaborate with users in your Skype for Business Server deployment, you must also configure at least one external access policy to support external user access.</span></span> <span data-ttu-id="bd98c-110">Para obtener más información, consulte Administrar socios federados XMPP para su organización.</span><span class="sxs-lookup"><span data-stu-id="bd98c-110">For details, see Manage XMPP Federated Partners for Your Organization.</span></span> <span data-ttu-id="bd98c-111">Para obtener más información sobre cómo controlar el acceso a dominios federados específicos, consulte Control access by Individual Federated Domains.</span><span class="sxs-lookup"><span data-stu-id="bd98c-111">For details about controlling access for specific federated domains, see Control Access by Individual Federated Domains.</span></span>
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a><span data-ttu-id="bd98c-112">Habilitar o deshabilitar la declinación de responsabilidades de archivado con el Panel de control</span><span class="sxs-lookup"><span data-stu-id="bd98c-112">Enable or disable archiving disclaimer using the Control Panel</span></span>

1. <span data-ttu-id="bd98c-113">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="bd98c-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="bd98c-114">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="bd98c-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="bd98c-115">En el barra de navegación izquierda, haga clic en **Federación y acceso externo** y luego en **Configuración perimetral de acceso**.</span><span class="sxs-lookup"><span data-stu-id="bd98c-115">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>
    
4. <span data-ttu-id="bd98c-116">En la pestaña **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="bd98c-116">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="bd98c-117">En **Editar** configuración perimetral de acceso, en Habilitar federación  y conectividad de mensajería instantánea **pública,** active o desactive la casilla Enviar declinación de responsabilidades de archivado a socios federados para habilitar o deshabilitar el envío automático del aviso de declinación de responsabilidades de archivado.</span><span class="sxs-lookup"><span data-stu-id="bd98c-117">In **Edit Access Edge Configuration**, under **Enable federation and public IM connectivity**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>
    
6. <span data-ttu-id="bd98c-118">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="bd98c-118">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a><span data-ttu-id="bd98c-119">Habilitar o deshabilitar la declinación de responsabilidades de archivado mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd98c-119">Enable or disable archiving disclaimer using Windows PowerShell</span></span>

<span data-ttu-id="bd98c-120">Para habilitar la renuncia de archivado, establezca la propiedad **EnableArchivingDisclaimer** en True ($True):</span><span class="sxs-lookup"><span data-stu-id="bd98c-120">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

<span data-ttu-id="bd98c-121">Para deshabilitar la renuncia de archivado, establezca la propiedad **EnableArchivingDisclaimer** en False ($False):</span><span class="sxs-lookup"><span data-stu-id="bd98c-121">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


