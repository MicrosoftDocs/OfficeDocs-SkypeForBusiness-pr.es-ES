---
title: Ver información de directivas de PIN en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 'Resumen: vea la información de la Directiva de PIN de un usuario para Skype empresarial Server.'
ms.openlocfilehash: 5f6269b766748d5027c0a8182dd027754cd5cc00
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297592"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a><span data-ttu-id="cdf9d-103">Ver información de directivas de PIN en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="cdf9d-103">View PIN policy information in Skype for Business Server</span></span>
 
<span data-ttu-id="cdf9d-104">**Resumen:** Ver la información de la Directiva de PIN de un usuario para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="cdf9d-104">**Summary:** View a user's PIN policy information for Skype for Business Server.</span></span>
  
<span data-ttu-id="cdf9d-105">Puede usar la pestaña **Directiva de PIN** para ver la autenticación del número de identificación personal (PIN) de los usuarios que se conectan a Skype empresarial con teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="cdf9d-105">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="cdf9d-106">Para utilizar la autenticación de PIN, asegúrese de que la opción **Habilitar autenticación PIN** esté seleccionada en la configuración del servicio web.</span><span class="sxs-lookup"><span data-stu-id="cdf9d-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="cdf9d-107">Siga estos pasos para modificar una directiva de PIN de nivel de usuario o de sitio.</span><span class="sxs-lookup"><span data-stu-id="cdf9d-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="cdf9d-108">Para ver información sobre una directiva de PIN en el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="cdf9d-108">To view information about a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="cdf9d-109">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Skype empresarial Server. .</span><span class="sxs-lookup"><span data-stu-id="cdf9d-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="cdf9d-110">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="cdf9d-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="cdf9d-111">En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Directiva de PIN**.</span><span class="sxs-lookup"><span data-stu-id="cdf9d-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="cdf9d-112">En la página **Directiva de PIN**, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="cdf9d-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="cdf9d-113">Visualización de directivas de PIN con cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cdf9d-113">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="cdf9d-114">También puede ver directivas de PIN con Windows PowerShell y el cmdlet Get-CsPinPolicy.</span><span class="sxs-lookup"><span data-stu-id="cdf9d-114">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="cdf9d-115">Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cdf9d-115">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="cdf9d-116">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Skype empresarial Server, consulte el artículo del blog ["Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="cdf9d-116">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="cdf9d-117">El proceso es el mismo en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="cdf9d-117">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-pin-policies"></a><span data-ttu-id="cdf9d-118">Para ver las directivas de PIN</span><span class="sxs-lookup"><span data-stu-id="cdf9d-118">To view PIN policies</span></span>

<span data-ttu-id="cdf9d-119">Para ver información sobre todas las directivas de PIN, escriba el siguiente comando en el shell de administración de Skype empresarial Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="cdf9d-119">To view information about all your PIN policies, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```
  Get-CsPinPolicy
  ```

<span data-ttu-id="cdf9d-120">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="cdf9d-120">That will return information similar to this:</span></span>

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

<span data-ttu-id="cdf9d-121">Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="cdf9d-121">For more information, see the help topic for the [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cdf9d-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="cdf9d-122">See also</span></span>

[<span data-ttu-id="cdf9d-123">Crear una nueva Directiva de PIN en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="cdf9d-123">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)
