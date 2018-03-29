---
title: Configurar la declinación de responsabilidades del archivado para los usuarios externos en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 'Resumen: Leer este tema para aprender a configurar una renuncia de archivado para Skype para Business Server 2015.'
ms.openlocfilehash: 3790160024010084c69df7d9865f17622fca4f0d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server-2015"></a><span data-ttu-id="e95f4-103">Configurar la declinación de responsabilidades del archivado para los usuarios externos en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="e95f4-103">Configure archiving disclaimers for external users in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e95f4-104">**Resumen:** Lea este tema para aprender a configurar una renuncia de archivado para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e95f4-104">**Summary:** Read this topic to learn how to configure an archiving disclaimer for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="e95f4-105">Si su organización se comunica con socios externos, necesita informarles que las comunicaciones con ellos se archivan.</span><span class="sxs-lookup"><span data-stu-id="e95f4-105">If your organization communicates with external partners, you need to let them know that you are archiving communications with them.</span></span> <span data-ttu-id="e95f4-106">Cuando se implementa un servidor perimetral y habilitar la federación para su organización, le pregunta si desea enviar automáticamente una archiving renuncia a socios externos.</span><span class="sxs-lookup"><span data-stu-id="e95f4-106">When you deploy an Edge Server and enable federation for your organization, you are asked whether you want to automatically send an archiving disclaimer to external partners.</span></span> 
  
<span data-ttu-id="e95f4-107">Si necesita cambiar esta configuración, puede utilizar el Skype para el Panel de Control de servidor de negocios o el cmdlet de Windows PowerShell **Set-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="e95f4-107">If you need to change this configuration, you can use the Skype for Business Server Control Panel or the Windows PowerShell **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="e95f4-108">Los cmdlets se puede ejecutar desde el Skype para el shell de administración de Business Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e95f4-108">Cmdlets can be run either from the Skype for Business Server management shell or from a remote session of Windows PowerShell.</span></span>
  
<span data-ttu-id="e95f4-109">Para permitir que los usuarios externos colaborar con los usuarios de su Skype para la implementación de Business Server, también debe configurar al menos una directiva de acceso externo para admitir el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="e95f4-109">To enable external users to collaborate with users in your Skype for Business Server deployment, you must also configure at least one external access policy to support external user access.</span></span> <span data-ttu-id="e95f4-110">Para obtener más información, vea a administrar socios federados de XMPP para su organización.</span><span class="sxs-lookup"><span data-stu-id="e95f4-110">For details, see Manage XMPP Federated Partners for Your Organization.</span></span> <span data-ttu-id="e95f4-111">Para más detalles sobre el control de acceso para dominios federados específicos, consulte Controlar el acceso por medio de los dominios federados individuales.</span><span class="sxs-lookup"><span data-stu-id="e95f4-111">For details about controlling access for specific federated domains, see Control Access by Individual Federated Domains.</span></span>
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a><span data-ttu-id="e95f4-112">Habilitar o deshabilitar la renuncia de archivado mediante el Panel de control</span><span class="sxs-lookup"><span data-stu-id="e95f4-112">Enable or disable archiving disclaimer using the Control Panel</span></span>

1. <span data-ttu-id="e95f4-113">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="e95f4-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e95f4-114">Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="e95f4-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="e95f4-115">En la barra de navegación izquierda, haga clic en **Federación y acceso externo** y, luego, en **Configuración perimetral de acceso**.</span><span class="sxs-lookup"><span data-stu-id="e95f4-115">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>
    
4. <span data-ttu-id="e95f4-116">En la ficha **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="e95f4-116">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="e95f4-117">En **Editar configuración perimetral de acceso**, en **Habilitar federación y conectividad pública de mensajería instantánea**, active o desactive la casilla **Enviar declinación de responsabilidades de archivado a los socios federados** para habilitar o deshabilitar el envío automático de declinaciones de responsabilidades de archivado.</span><span class="sxs-lookup"><span data-stu-id="e95f4-117">In **Edit Access Edge Configuration**, under **Enable federation and public IM connectivity**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>
    
6. <span data-ttu-id="e95f4-118">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e95f4-118">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a><span data-ttu-id="e95f4-119">Habilitar o deshabilitar la renuncia de archivado mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e95f4-119">Enable or disable archiving disclaimer using Windows PowerShell</span></span>

<span data-ttu-id="e95f4-120">Para habilitar la declinación de responsabilidades de archivado, establezca el valor de la propiedad **EnableArchivingDisclaimer** en True ($True):</span><span class="sxs-lookup"><span data-stu-id="e95f4-120">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

<span data-ttu-id="e95f4-121">Para deshabilitar la declinación de responsabilidades de archivado, establezca el valor de la propiedad **EnableArchivingDisclaimer** en False ($False):</span><span class="sxs-lookup"><span data-stu-id="e95f4-121">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


