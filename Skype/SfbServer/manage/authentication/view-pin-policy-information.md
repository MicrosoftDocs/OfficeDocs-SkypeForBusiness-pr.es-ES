---
title: Ver información de directivas de PIN de Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 'Resumen: Ver información de directiva del NIP de un usuario de Skype para Business Server 2015.'
ms.openlocfilehash: 57960037f5a89cd93e03dc37d3f010343313e1e6
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568769"
---
# <a name="view-pin-policy-information-in-skype-for-business-server-2015"></a><span data-ttu-id="e00e0-103">Ver información de directivas de PIN de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="e00e0-103">View PIN policy information in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e00e0-104">**Resumen:** Ver información de directiva del NIP de un usuario de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e00e0-104">**Summary:** View a user's PIN policy information for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="e00e0-105">Puede usar la ficha **Directiva de PIN** a vista identificación personal numérico (PIN) la autenticación de usuarios que se conectan a Skype para la empresa con teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="e00e0-105">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="e00e0-106">Para usar la autenticación de PIN, asegúrese de que la opción **Habilitar autenticación de PIN** esté seleccionada en la configuración del servicio web.</span><span class="sxs-lookup"><span data-stu-id="e00e0-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="e00e0-107">Siga estos pasos para modificar una directiva de PIN de nivel de usuario o de sitio.</span><span class="sxs-lookup"><span data-stu-id="e00e0-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="e00e0-108">Para ver información acerca de una directiva de PIN de Skype para Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="e00e0-108">To view information about a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="e00e0-109">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que implementa Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e00e0-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="e00e0-110">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="e00e0-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="e00e0-111">En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Directiva de PIN**.</span><span class="sxs-lookup"><span data-stu-id="e00e0-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="e00e0-112">En la página **Directiva de PIN**, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="e00e0-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e00e0-113">Ver directivas de PIN mediante el uso de Cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e00e0-113">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e00e0-114">También puede ver las directivas de PIN mediante el uso de Windows PowerShell y el cmdlet Get-CsPinPolicy.</span><span class="sxs-lookup"><span data-stu-id="e00e0-114">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="e00e0-115">Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e00e0-115">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e00e0-116">Para obtener información detallada acerca del uso de Windows PowerShell remoto para conectarse a Skype para Business Server, vea el artículo del blog ["rápido iniciar: administración de Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="e00e0-116">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="e00e0-117">El proceso es el mismo en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="e00e0-117">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-pin-policies"></a><span data-ttu-id="e00e0-118">Para ver las directivas de PIN</span><span class="sxs-lookup"><span data-stu-id="e00e0-118">To view PIN policies</span></span>

<span data-ttu-id="e00e0-119">Para ver información acerca de todas las directivas de PIN, escriba el siguiente comando en el Skype para Shell de administración de servidor empresarial y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="e00e0-119">To view information about all your PIN policies, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```
  Get-CsPinPolicy
  ```

<span data-ttu-id="e00e0-120">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="e00e0-120">That will return information similar to this:</span></span>

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

<span data-ttu-id="e00e0-121">Para obtener más información, vea el tema de ayuda para el cmdlet [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="e00e0-121">For more information, see the help topic for the [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e00e0-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="e00e0-122">See also</span></span>

[<span data-ttu-id="e00e0-123">Crear una nueva directiva PIN en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e00e0-123">Create a new PIN policy in Skype for Business Server 2015</span></span>](create-a-new-pin-policy.md)