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
description: En este artículo se describe problemas conocidos de las versiones actuales de sucursal de sistemas de salón de Skype v2.
ms.openlocfilehash: cdcd33566c4e14078b14ed5d3656eb1bffee6c6a
ms.sourcegitcommit: 5a0b3fe49b64f08979c89443f66b15827034e755
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2018
---
# <a name="known-issues"></a><span data-ttu-id="7bc28-103">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="7bc28-103">Known issues</span></span> 
 
<span data-ttu-id="7bc28-104">En este artículo se enumeran los problemas conocidos para sistemas de salón de Skype v2, por área de característica.</span><span class="sxs-lookup"><span data-stu-id="7bc28-104">This article lists the known issues for Skype Room Systems v2, by feature area.</span></span>
<span data-ttu-id="7bc28-105"><!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"></a> ## Actualización</span><span class="sxs-lookup"><span data-stu-id="7bc28-105"><!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a> ## Update</span></span> 

| <span data-ttu-id="7bc28-106">Título del problema</span><span class="sxs-lookup"><span data-stu-id="7bc28-106">Issue title</span></span> |  <span data-ttu-id="7bc28-107">Comportamiento de \/ síntoma</span><span class="sxs-lookup"><span data-stu-id="7bc28-107">Behavior \/ Symptom</span></span> | <span data-ttu-id="7bc28-108">Solución conocida</span><span class="sxs-lookup"><span data-stu-id="7bc28-108">Known workaround</span></span> | <span data-ttu-id="7bc28-109">Artículo KB</span><span class="sxs-lookup"><span data-stu-id="7bc28-109">KB Article</span></span> |
|  ---        |      ---             |   ---            | --- |
|  <span data-ttu-id="7bc28-110">Aplicación caducada</span><span class="sxs-lookup"><span data-stu-id="7bc28-110">App out of date</span></span>         |    <span data-ttu-id="7bc28-111">La consola de v2 de sistemas de salón de Skype muestra un error "sistema config caducada".</span><span class="sxs-lookup"><span data-stu-id="7bc28-111">The Skype Room Systems v2 console shows a "system config out of date" error.</span></span>                |   [<span data-ttu-id="7bc28-112">Utilizar la herramienta de recuperación de sistemas de salón de Skype v2</span><span class="sxs-lookup"><span data-stu-id="7bc28-112">Use the Skype Room Systems v2 recovery tool</span></span>](recovery-tool.md)             |  <span data-ttu-id="7bc28-113">Ninguna</span><span class="sxs-lookup"><span data-stu-id="7bc28-113">None</span></span> |


<span data-ttu-id="7bc28-114"><a name="OS-conflicts"> </a></span><span class="sxs-lookup"><span data-stu-id="7bc28-114"></span></span>  
## <a name="user-interface"></a><span data-ttu-id="7bc28-115">Interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="7bc28-115">User interface</span></span> 

| <span data-ttu-id="7bc28-116">Título del problema</span><span class="sxs-lookup"><span data-stu-id="7bc28-116">Issue title</span></span> |  <span data-ttu-id="7bc28-117">Comportamiento de \/ síntoma</span><span class="sxs-lookup"><span data-stu-id="7bc28-117">Behavior \/ Symptom</span></span> | <span data-ttu-id="7bc28-118">Solución conocida</span><span class="sxs-lookup"><span data-stu-id="7bc28-118">Known workaround</span></span> | <span data-ttu-id="7bc28-119">Artículo KB</span><span class="sxs-lookup"><span data-stu-id="7bc28-119">KB Article</span></span> |
|  ---        |      ---             |   ---            | --- |
|<span data-ttu-id="7bc28-120">Falta el teclado virtual</span><span class="sxs-lookup"><span data-stu-id="7bc28-120">Virtual keyboard missing</span></span>   | <span data-ttu-id="7bc28-121">El teclado virtual no aparece cuando se necesita escribir información en sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="7bc28-121">The virtual keyboard doesn't appear when you need to enter information in Skype Room Systems v2.</span></span> <span data-ttu-id="7bc28-122">Este problema se produce después de instalar la actualización de los creadores de 10 (versión 1703) de Windows en el 4 Surface Pro en el que se ejecuta v2 de sistemas de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="7bc28-122">This issue occurs after the Windows 10 Creators Update (version 1703) is installed on the Surface Pro 4 on which Skype Room Systems v2 is running.</span></span> | <span data-ttu-id="7bc28-123">Para solucionar este problema, abra manualmente el teclado virtual.</span><span class="sxs-lookup"><span data-stu-id="7bc28-123">To work around this issue, manually open the virtual keyboard.</span></span> <span data-ttu-id="7bc28-124">Para ello, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="7bc28-124">To do this, follow these steps:</span></span><br><br> <span data-ttu-id="7bc28-125">Puntee en **1.** y mantenga la barra de tareas y, a continuación, puntee el botón **Mostrar pantalla táctil** .</span><span class="sxs-lookup"><span data-stu-id="7bc28-125">**1.** Tap and hold the task bar, and then tap **Show touch keyboard** button.</span></span> <span data-ttu-id="7bc28-126">Debería aparecer un icono de teclado en el lado derecho de la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="7bc28-126">A keyboard icon should appear on the right side of the task bar.</span></span> <br><br> <span data-ttu-id="7bc28-127">**2.** puntee el icono de teclado para abrir el teclado virtual.</span><span class="sxs-lookup"><span data-stu-id="7bc28-127">**2.** Tap the keyboard icon to open the virtual keyboard.</span></span> | [<span data-ttu-id="7bc28-128">KB4037694</span><span class="sxs-lookup"><span data-stu-id="7bc28-128">KB4037694</span></span>](https://support.microsoft.com/en-us/help/4037694/virtual-keyboard-missing-in-skype-room-systems-v2) | 
   

<span data-ttu-id="7bc28-129"><a name="Hardware"> </a></span><span class="sxs-lookup"><span data-stu-id="7bc28-129"></span></span>  
## <a name="hardware"></a><span data-ttu-id="7bc28-130">Hardware</span><span class="sxs-lookup"><span data-stu-id="7bc28-130">Hardware</span></span>

| <span data-ttu-id="7bc28-131">Título del problema</span><span class="sxs-lookup"><span data-stu-id="7bc28-131">Issue title</span></span> |  <span data-ttu-id="7bc28-132">Comportamiento de \/ síntoma</span><span class="sxs-lookup"><span data-stu-id="7bc28-132">Behavior \/ Symptom</span></span> | <span data-ttu-id="7bc28-133">Solución conocida</span><span class="sxs-lookup"><span data-stu-id="7bc28-133">Known workaround</span></span> | <span data-ttu-id="7bc28-134">Artículo KB</span><span class="sxs-lookup"><span data-stu-id="7bc28-134">KB Article</span></span> |
|  ---        |      ---             |   ---            |   --- |
| <span data-ttu-id="7bc28-135">Monitores no detectados</span><span class="sxs-lookup"><span data-stu-id="7bc28-135">Monitors not detected</span></span> | <span data-ttu-id="7bc28-136">Cuando ejecuta v2 de sistemas de salón de Skype en un dispositivo Surface Pro (modelo de 2017), no se detectan los monitores.</span><span class="sxs-lookup"><span data-stu-id="7bc28-136">When you run Skype Room Systems v2 on a Surface Pro (Model 2017) device, monitors are not detected.</span></span> |  <span data-ttu-id="7bc28-137">Mantenga presionado el botón de alimentación Surface Pro de 20 o más segundos.</span><span class="sxs-lookup"><span data-stu-id="7bc28-137">Hold down the Surface Pro power button for 20 or more seconds.</span></span> <span data-ttu-id="7bc28-138">En este caso, el dispositivo se reinicia y borra la memoria caché de gráficos.</span><span class="sxs-lookup"><span data-stu-id="7bc28-138">When you do this, the device restarts and clears the graphics cache.</span></span> |[<span data-ttu-id="7bc28-139">KB4055681</span><span class="sxs-lookup"><span data-stu-id="7bc28-139">KB4055681</span></span>](https://support.microsoft.com/en-us/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 
          
<span data-ttu-id="7bc28-140"><a name="Limits"> </a></span><span class="sxs-lookup"><span data-stu-id="7bc28-140"></span></span>
## <a name="limitations-and-expected-behaviors"></a><span data-ttu-id="7bc28-141">Limitaciones y comportamientos esperados</span><span class="sxs-lookup"><span data-stu-id="7bc28-141">Limitations and expected behaviors</span></span>
***
<span data-ttu-id="7bc28-142">Sistemas de salón de Skype v2 no es compatible con entrada HDCP, que se ha observado para provocar problemas con HDMI ingesta funcionalidad (vídeo, audio).</span><span class="sxs-lookup"><span data-stu-id="7bc28-142">Skype Room Systems v2 does not support HDCP input, which has been observed to cause issues with HDMI ingest functionality (video, audio).</span></span> <span data-ttu-id="7bc28-143">Tenga cuidado para asegurarse de que los conmutadores conectados a sistemas de salón de Skype v2 tienen opciones HDCP desactivadas.</span><span class="sxs-lookup"><span data-stu-id="7bc28-143">Take care to ensure that switches connected to Skype Room Systems v2 have HDCP options turned off.</span></span> 
***
<span data-ttu-id="7bc28-144">Una televisión de consumo usada como una parte delantera del salón de mostrar las necesidades de soporte técnico o habilitar la característica de Control de electrónica de consumidor (CEC) de HDMI para que puede cambiar automáticamente a un origen de vídeo activo de modo de espera.</span><span class="sxs-lookup"><span data-stu-id="7bc28-144">A consumer TV used as a front of room display needs to support/enable the Consumer Electronics Control (CEC) feature of HDMI so that it can switch automatically to an active video source from standby mode.</span></span> <span data-ttu-id="7bc28-145">Esta característica no se admite en todos los televisores.</span><span class="sxs-lookup"><span data-stu-id="7bc28-145">This feature is not supported on all TVs.</span></span> 
***
<span data-ttu-id="7bc28-146">Use siempre una conexión de red de 1 Gbps por cable para asegurarse de que tiene el ancho de banda necesaria.</span><span class="sxs-lookup"><span data-stu-id="7bc28-146">Always use a wired 1 Gbps network connection to assure you will have the needed bandwidth.</span></span> 
***
<span data-ttu-id="7bc28-147">Si su dispositivo v2 de sistemas de salón de Skype pierde la relación de confianza con el dominio (por ejemplo, si quita el v2 de sistemas de salón de Skype desde el dominio después de está unido al dominio), no podrá autenticar en el dispositivo y abrir seguridad de la configuración.</span><span class="sxs-lookup"><span data-stu-id="7bc28-147">If your Skype Room Systems v2 device loses trust with the domain (for example, if you remove the Skype Room Systems v2 from the domain after it is domain joined), you won't be able to authenticate into the device and open up Settings.</span></span> <span data-ttu-id="7bc28-148">La solución alternativa es iniciar sesión con la cuenta de administrador local.</span><span class="sxs-lookup"><span data-stu-id="7bc28-148">The workaround is to log in with the local Admin account.</span></span> 
***
<span data-ttu-id="7bc28-149">Ya no se admite la versión de 64 bits de edición de Windows 10 Enterprise aniversario (en inglés, versión 1607) a partir de sistemas de salón de Skype v2 versión 3.0.12.0 (actualización 3).</span><span class="sxs-lookup"><span data-stu-id="7bc28-149">The 64-bit version of Windows 10 Enterprise Anniversary edition (English language, version 1607) is no longer supported as of Skype Room Systems v2 release 3.0.12.0 (update 3).</span></span> 
***

<span data-ttu-id="7bc28-150"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="7bc28-150"></span></span>  
## <a name="see-also"></a><span data-ttu-id="7bc28-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="7bc28-151">See also</span></span>


#### 
[<span data-ttu-id="7bc28-152">Ayuda de la versión 2 de sistemas de salón de Skype</span><span class="sxs-lookup"><span data-stu-id="7bc28-152">Skype Room Systems version 2 help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="7bc28-153">Administración de salón de Skype v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="7bc28-153">Manage Skype Room Systems v2</span></span>](skype-room-systems-v2.md)
#### 
