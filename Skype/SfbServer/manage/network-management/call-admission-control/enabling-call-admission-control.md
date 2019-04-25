---
title: Habilitar el control de admisión de llamadas
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: " Después de configurar la red de (CAC) del control de admisión de llamadas, debe habilitar el CAC para exigir la aplicación de las limitaciones de ancho de banda."
ms.openlocfilehash: a683fe0f437fc1c3fa92784313135d094e43c8b1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32228410"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="5c823-103">Habilitar el control de admisión de llamadas en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5c823-103">Enabling call admission control in Skype for Business Server</span></span>

<span data-ttu-id="5c823-104">El control de admisión de llamadas (CAC) es una red de regiones, sitios y subredes que permiten colocar restricciones en las transmisiones de audio y vídeo según el ancho de banda disponible.</span><span class="sxs-lookup"><span data-stu-id="5c823-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="5c823-105">Después de configurar la red CAC, debe habilitar el CAC para exigir la aplicación de las limitaciones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="5c823-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="5c823-106">Puede usar el Skype para el Panel de Control de servidor empresarial para ello.</span><span class="sxs-lookup"><span data-stu-id="5c823-106">You can use the Skype for Business Server Control Panel to do this.</span></span>


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a><span data-ttu-id="5c823-107">Para habilitar el CAC desde el Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="5c823-107">To enable CAC from the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="5c823-108">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="5c823-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5c823-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="5c823-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5c823-110">En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **Global**.</span><span class="sxs-lookup"><span data-stu-id="5c823-110">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="5c823-111">En la página **Global** , haga clic en la configuración **Global** .</span><span class="sxs-lookup"><span data-stu-id="5c823-111">On the **Global** page, click the **Global** configuration.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="5c823-112">Sólo una red se puede configurar para cualquier Skype para la implementación de servidor empresarial, por lo que nunca será más de una configuración de red en la lista.</span><span class="sxs-lookup"><span data-stu-id="5c823-112">Only one network can be configured for any Skype for Business Server deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="5c823-113">No se puede cambiar el nombre de la configuración Global.</span><span class="sxs-lookup"><span data-stu-id="5c823-113">You cannot rename the Global configuration.</span></span>

5.  <span data-ttu-id="5c823-114">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="5c823-114">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="5c823-115">En la página **Editar configuración Global** , active la casilla de verificación **Habilitar el control de admisión de llamadas** y, a continuación, haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5c823-115">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="5c823-116">Al hacer clic en **Confirmar**, se ejecuta una prueba de la configuración.</span><span class="sxs-lookup"><span data-stu-id="5c823-116">When you click **Commit**, you run a test of the configuration.</span></span> <span data-ttu-id="5c823-117">Cierra el cuadro de diálogo **Editar configuración Global** , regresará a la página **Global** .</span><span class="sxs-lookup"><span data-stu-id="5c823-117">The **Edit Global Settings** dialog box closes, returning you to the **Global** page.</span></span> <span data-ttu-id="5c823-118">Recibirá una advertencia si se detectan los errores o incoherencias en su configuración de red que impedirá que funciona correctamente (por ejemplo, si cada región no está conectado a todas las regiones a través de una ruta entre regiones).</span><span class="sxs-lookup"><span data-stu-id="5c823-118">You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="5c823-119">Si realiza cambios en la configuración de red, puede ejecutar la comprobación de validación de nuevo abrir la configuración Global y haciendo clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5c823-119">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**.</span></span> <span data-ttu-id="5c823-120">No es necesario deshabilitar el CAC en primer lugar: deje activada la casilla de verificación y haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5c823-120">You do not need to disable CAC first: leave the check box checked and click **Commit**.</span></span> <span data-ttu-id="5c823-121">Puede hacerlo en cualquier momento, sin realizar ningún cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="5c823-121">You can do this at any time without making any configuration changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c823-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c823-122">See Also</span></span>

[<span data-ttu-id="5c823-123">Planificar el servicio de control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="5c823-123">Plan for call admission control</span></span>](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[<span data-ttu-id="5c823-124">Implementar el control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="5c823-124">Deploy call admission control</span></span>](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[<span data-ttu-id="5c823-125">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="5c823-125">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[<span data-ttu-id="5c823-126">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="5c823-126">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[<span data-ttu-id="5c823-127">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="5c823-127">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
