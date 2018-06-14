---
title: Problemas conocidos
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En este artículo se describe los problemas conocidos para sistemas de salón de Skype v2, por área de característica.
ms.openlocfilehash: 2fde12d616260963dc342df2d9cef94acf616756
ms.sourcegitcommit: dc7a7da270121c3702f38614158c9067ad38f12a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2018
ms.locfileid: "19881545"
---
# <a name="known-issues"></a><span data-ttu-id="cd501-103">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cd501-103">Known issues</span></span> 
 
<span data-ttu-id="cd501-104">En este artículo se enumeran los problemas conocidos para sistemas de salón de Skype v2, por área de característica.</span><span class="sxs-lookup"><span data-stu-id="cd501-104">This article lists the known issues for Skype Room Systems v2, by feature area.</span></span>
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<span data-ttu-id="cd501-105"><a name="update"> </a></span><span class="sxs-lookup"><span data-stu-id="cd501-105"></span></span>  
## <a name="update"></a><span data-ttu-id="cd501-106">Actualización</span><span class="sxs-lookup"><span data-stu-id="cd501-106">Update</span></span> 

| <span data-ttu-id="cd501-107">Título del problema</span><span class="sxs-lookup"><span data-stu-id="cd501-107">Issue title</span></span> |  <span data-ttu-id="cd501-108">Comportamiento de \/ síntoma</span><span class="sxs-lookup"><span data-stu-id="cd501-108">Behavior \/ Symptom</span></span> | <span data-ttu-id="cd501-109">Solución conocida</span><span class="sxs-lookup"><span data-stu-id="cd501-109">Known workaround</span></span> | <span data-ttu-id="cd501-110">Artículo KB</span><span class="sxs-lookup"><span data-stu-id="cd501-110">KB Article</span></span> |
|  ---        |      ---             |   ---            | --- |
|  <span data-ttu-id="cd501-111">Aplicación caducada</span><span class="sxs-lookup"><span data-stu-id="cd501-111">App out of date</span></span>         |    <span data-ttu-id="cd501-112">La consola de v2 de sistemas de salón de Skype muestra un error "sistema config caducada".</span><span class="sxs-lookup"><span data-stu-id="cd501-112">The Skype Room Systems v2 console shows a "system config out of date" error.</span></span>                |   [<span data-ttu-id="cd501-113">Utilizar la herramienta de recuperación de sistemas de salón de Skype v2</span><span class="sxs-lookup"><span data-stu-id="cd501-113">Use the Skype Room Systems v2 recovery tool</span></span>](recovery-tool.md)             |  <span data-ttu-id="cd501-114">Ninguna</span><span class="sxs-lookup"><span data-stu-id="cd501-114">None</span></span> |


<span data-ttu-id="cd501-115"><a name="OS-conflicts"> </a></span><span class="sxs-lookup"><span data-stu-id="cd501-115"></span></span>  
## <a name="user-interface"></a><span data-ttu-id="cd501-116">Interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="cd501-116">User interface</span></span> 

| <span data-ttu-id="cd501-117">Título del problema</span><span class="sxs-lookup"><span data-stu-id="cd501-117">Issue title</span></span> |  <span data-ttu-id="cd501-118">Comportamiento de \/ síntoma</span><span class="sxs-lookup"><span data-stu-id="cd501-118">Behavior \/ Symptom</span></span> | <span data-ttu-id="cd501-119">Solución conocida</span><span class="sxs-lookup"><span data-stu-id="cd501-119">Known workaround</span></span> | <span data-ttu-id="cd501-120">Artículo KB</span><span class="sxs-lookup"><span data-stu-id="cd501-120">KB Article</span></span> |
|  ---        |      ---             |   ---            | --- |
|<span data-ttu-id="cd501-121">Falta el teclado virtual</span><span class="sxs-lookup"><span data-stu-id="cd501-121">Virtual keyboard missing</span></span>   | <span data-ttu-id="cd501-122">El teclado virtual no aparece cuando se necesita escribir información en sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="cd501-122">The virtual keyboard doesn't appear when you need to enter information in Skype Room Systems v2.</span></span> <span data-ttu-id="cd501-123">Este problema se produce después de instalar la actualización de los creadores de 10 (versión 1703) de Windows en el 4 Surface Pro en el que se ejecuta v2 de sistemas de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="cd501-123">This issue occurs after the Windows 10 Creators Update (version 1703) is installed on the Surface Pro 4 on which Skype Room Systems v2 is running.</span></span> | <span data-ttu-id="cd501-124">Para solucionar este problema, abra manualmente el teclado virtual.</span><span class="sxs-lookup"><span data-stu-id="cd501-124">To work around this issue, manually open the virtual keyboard.</span></span> <span data-ttu-id="cd501-125">Para ello, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="cd501-125">To do this, follow these steps:</span></span><br><br> <span data-ttu-id="cd501-126">Puntee en **1.** y mantenga la barra de tareas y, a continuación, puntee el botón **Mostrar pantalla táctil** .</span><span class="sxs-lookup"><span data-stu-id="cd501-126">**1.** Tap and hold the task bar, and then tap **Show touch keyboard** button.</span></span> <span data-ttu-id="cd501-127">Debería aparecer un icono de teclado en el lado derecho de la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="cd501-127">A keyboard icon should appear on the right side of the task bar.</span></span> <br><br> <span data-ttu-id="cd501-128">**2.** puntee el icono de teclado para abrir el teclado virtual.</span><span class="sxs-lookup"><span data-stu-id="cd501-128">**2.** Tap the keyboard icon to open the virtual keyboard.</span></span> | [<span data-ttu-id="cd501-129">KB4037694</span><span class="sxs-lookup"><span data-stu-id="cd501-129">KB4037694</span></span>](https://support.microsoft.com/en-us/help/4037694/virtual-keyboard-missing-in-skype-room-systems-v2) | 
   

<span data-ttu-id="cd501-130"><a name="Hardware"> </a></span><span class="sxs-lookup"><span data-stu-id="cd501-130"></span></span>  
## <a name="hardware"></a><span data-ttu-id="cd501-131">Hardware</span><span class="sxs-lookup"><span data-stu-id="cd501-131">Hardware</span></span>

| <span data-ttu-id="cd501-132">Título del problema</span><span class="sxs-lookup"><span data-stu-id="cd501-132">Issue title</span></span> |  <span data-ttu-id="cd501-133">Comportamiento de \/ síntoma</span><span class="sxs-lookup"><span data-stu-id="cd501-133">Behavior \/ Symptom</span></span> | <span data-ttu-id="cd501-134">Solución conocida</span><span class="sxs-lookup"><span data-stu-id="cd501-134">Known workaround</span></span> | <span data-ttu-id="cd501-135">Artículo KB</span><span class="sxs-lookup"><span data-stu-id="cd501-135">KB Article</span></span> |
|  ---        |      ---             |   ---            |   --- |
| <span data-ttu-id="cd501-136">Monitores no detectados</span><span class="sxs-lookup"><span data-stu-id="cd501-136">Monitors not detected</span></span> | <span data-ttu-id="cd501-137">Cuando ejecuta v2 de sistemas de salón de Skype en un dispositivo Surface Pro (modelo de 2017), no se detectan los monitores.</span><span class="sxs-lookup"><span data-stu-id="cd501-137">When you run Skype Room Systems v2 on a Surface Pro (Model 2017) device, monitors are not detected.</span></span> |  <span data-ttu-id="cd501-138">Mantenga presionado el botón de alimentación Surface Pro de 20 o más segundos.</span><span class="sxs-lookup"><span data-stu-id="cd501-138">Hold down the Surface Pro power button for 20 or more seconds.</span></span> <span data-ttu-id="cd501-139">En este caso, el dispositivo se reinicia y borra la memoria caché de gráficos.</span><span class="sxs-lookup"><span data-stu-id="cd501-139">When you do this, the device restarts and clears the graphics cache.</span></span> |[<span data-ttu-id="cd501-140">KB4055681</span><span class="sxs-lookup"><span data-stu-id="cd501-140">KB4055681</span></span>](https://support.microsoft.com/en-us/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 
          
<span data-ttu-id="cd501-141"><a name="Limits"> </a></span><span class="sxs-lookup"><span data-stu-id="cd501-141"></span></span>
## <a name="limitations-and-expected-behaviors"></a><span data-ttu-id="cd501-142">Limitaciones y comportamientos esperados</span><span class="sxs-lookup"><span data-stu-id="cd501-142">Limitations and expected behaviors</span></span>
***
<span data-ttu-id="cd501-143">Sistemas de salón de Skype v2 no es compatible con entrada HDCP, que se ha observado para provocar problemas con HDMI ingesta funcionalidad (vídeo, audio).</span><span class="sxs-lookup"><span data-stu-id="cd501-143">Skype Room Systems v2 does not support HDCP input, which has been observed to cause issues with HDMI ingest functionality (video, audio).</span></span> <span data-ttu-id="cd501-144">Tenga cuidado para asegurarse de que los conmutadores conectados a sistemas de salón de Skype v2 tienen opciones HDCP desactivadas.</span><span class="sxs-lookup"><span data-stu-id="cd501-144">Take care to ensure that switches connected to Skype Room Systems v2 have HDCP options turned off.</span></span> 
***
<span data-ttu-id="cd501-145">Una televisión de consumo usada como una parte delantera del salón de mostrar las necesidades de soporte técnico o habilitar la característica de Control de electrónica de consumidor (CEC) de HDMI para que puede cambiar automáticamente a un origen de vídeo activo de modo de espera.</span><span class="sxs-lookup"><span data-stu-id="cd501-145">A consumer TV used as a front of room display needs to support/enable the Consumer Electronics Control (CEC) feature of HDMI so that it can switch automatically to an active video source from standby mode.</span></span> <span data-ttu-id="cd501-146">Esta característica no se admite en todos los televisores.</span><span class="sxs-lookup"><span data-stu-id="cd501-146">This feature is not supported on all TVs.</span></span> 
***
<span data-ttu-id="cd501-147">Use siempre una conexión de red de 1 Gbps por cable para asegurarse de que tiene el ancho de banda necesaria.</span><span class="sxs-lookup"><span data-stu-id="cd501-147">Always use a wired 1 Gbps network connection to assure you will have the needed bandwidth.</span></span> 
***
<span data-ttu-id="cd501-148">Si su dispositivo v2 de sistemas de salón de Skype pierde la relación de confianza con el dominio (por ejemplo, si quita el v2 de sistemas de salón de Skype desde el dominio después de está unido al dominio), no podrá autenticar en el dispositivo y abrir seguridad de la configuración.</span><span class="sxs-lookup"><span data-stu-id="cd501-148">If your Skype Room Systems v2 device loses trust with the domain (for example, if you remove the Skype Room Systems v2 from the domain after it is domain joined), you won't be able to authenticate into the device and open up Settings.</span></span> <span data-ttu-id="cd501-149">La solución alternativa es iniciar sesión con la cuenta de administrador local.</span><span class="sxs-lookup"><span data-stu-id="cd501-149">The workaround is to log in with the local Admin account.</span></span> 
***
<span data-ttu-id="cd501-150">Ya no se admite la versión de 64 bits de edición de Windows 10 Enterprise aniversario (en inglés, versión 1607) a partir de sistemas de salón de Skype v2 versión 3.0.12.0.</span><span class="sxs-lookup"><span data-stu-id="cd501-150">The 64-bit version of Windows 10 Enterprise Anniversary edition (English language, version 1607) is no longer supported as of Skype Room Systems v2 release 3.0.12.0.</span></span> 
***

<span data-ttu-id="cd501-151"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="cd501-151"></span></span>  
## <a name="see-also"></a><span data-ttu-id="cd501-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd501-152">See also</span></span>

[<span data-ttu-id="cd501-153">Ayuda de la versión 2 de sistemas de salón de Skype</span><span class="sxs-lookup"><span data-stu-id="cd501-153">Skype Room Systems version 2 help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="cd501-154">Administración de salón de Skype v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="cd501-154">Manage Skype Room Systems v2</span></span>](skype-room-systems-v2.md)