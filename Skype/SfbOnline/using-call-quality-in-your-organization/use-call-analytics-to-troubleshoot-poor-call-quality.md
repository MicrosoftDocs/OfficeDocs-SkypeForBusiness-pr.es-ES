---
title: Calidad de las llamadas análisis de uso de llamadas para solucionar problemas de Skype deficiente para la empresa
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Use llamar análisis obtener información detallada sobre los dispositivos, redes y conectividad para solucionar los problemas de los usuarios con Skype para reuniones y llamadas de trabajo.
ms.openlocfilehash: cb887a1c582c9547616c2133c2f175ac634e2da8
ms.sourcegitcommit: 5a0b3fe49b64f08979c89443f66b15827034e755
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2018
---
# <a name="use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality"></a><span data-ttu-id="89fbe-103">Calidad de las llamadas análisis de uso de llamadas para solucionar problemas de Skype deficiente para la empresa</span><span class="sxs-lookup"><span data-stu-id="89fbe-103">Use Call Analytics to troubleshoot poor Skype for Business call quality</span></span>

<span data-ttu-id="89fbe-104">Análisis de llamada le ayuda a solucionar los problemas de conexión o llamada con Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="89fbe-104">Call Analytics helps you to troubleshoot call or connection problems with Skype for Business.</span></span> <span data-ttu-id="89fbe-105">Análisis de la llamada muestran información detallada acerca de los dispositivos, redes y conectividad para las llamadas y las reuniones de cada usuario en su Skype para la cuenta de empresa.</span><span class="sxs-lookup"><span data-stu-id="89fbe-105">Call Analytics shows detailed information about the devices, networks, and connectivity for the calls and meetings of each user in your Skype for Business account.</span></span> <span data-ttu-id="89fbe-106">Si crear, del sitio y de inquilinos se ha agregado información para análisis de llamadas, también se mostrarán para cada llamada y la sesión.</span><span class="sxs-lookup"><span data-stu-id="89fbe-106">If building, site, and tenant information has been added to Call Analytics, it will also be shown for each call and session.</span></span> <span data-ttu-id="89fbe-107">Información disponible a través de análisis de llamadas puede ayudar a averiguar por qué un usuario tuvo una llamada deficiente o experiencia de reunión.</span><span class="sxs-lookup"><span data-stu-id="89fbe-107">Information available via Call Analytics can help you figure out why a user had a poor call or meeting experience.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="89fbe-108">Análisis de la llamada está actualmente en la vista previa.</span><span class="sxs-lookup"><span data-stu-id="89fbe-108">Call Analytics is currently in preview.</span></span> <span data-ttu-id="89fbe-109">Texto e imágenes que se describen aquí no pueden coincidir con su experiencia.</span><span class="sxs-lookup"><span data-stu-id="89fbe-109">Text and images described here may not match your experience.</span></span>
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a><span data-ttu-id="89fbe-110">Solucionar los problemas de calidad de llamada mediante el análisis de llamadas</span><span class="sxs-lookup"><span data-stu-id="89fbe-110">Troubleshoot call quality problems using Call Analytics</span></span>

<span data-ttu-id="89fbe-111">El nivel de permisos que se le han asignado determina qué tipo de información tiene acceso a llamar análisis de:</span><span class="sxs-lookup"><span data-stu-id="89fbe-111">The permissions level assigned to you determines what type of information you have access to in Call Analytics:</span></span>
  
- <span data-ttu-id="89fbe-112">**Skype para administración empresarial**: tener acceso a toda la información en análisis de llamadas y en el Skype para el centro de administración de negocio.</span><span class="sxs-lookup"><span data-stu-id="89fbe-112">**Skype for Business admin**: You have access to all the information in Call Analytics and in the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="89fbe-113">**Agente de departamento de soporte técnico con permisos de nivel 1**: vea un conjunto limitado de datos de análisis de llamadas.</span><span class="sxs-lookup"><span data-stu-id="89fbe-113">**Helpdesk agent with Tier 1 permissions**: You see a limited set of data in Call Analytics.</span></span> <span data-ttu-id="89fbe-114">Puede solucionar problemas de las llamadas, pero podrá entregar problemas con las reuniones a un agente de nivel 2.</span><span class="sxs-lookup"><span data-stu-id="89fbe-114">You can troubleshoot calls, but you'll hand off problems with meetings to a Tier 2 agent.</span></span> <span data-ttu-id="89fbe-115">No tiene acceso al resto de la Skype para el centro de administración de negocio.</span><span class="sxs-lookup"><span data-stu-id="89fbe-115">You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="89fbe-116">**Agente de departamento de soporte técnico con permisos de nivel 2**: vea todos los datos disponibles en análisis de llamadas y puede ayudar a solucionar los problemas con las llamadas y las reuniones.</span><span class="sxs-lookup"><span data-stu-id="89fbe-116">**Helpdesk agent with Tier 2 permissions**: You see all available data in Call Analytics and can help troubleshoot problems with both calls and meetings.</span></span> <span data-ttu-id="89fbe-117">No tiene acceso al resto de la Skype para el centro de administración de negocio.</span><span class="sxs-lookup"><span data-stu-id="89fbe-117">You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
<span data-ttu-id="89fbe-118">Si necesita ayuda con los permisos, vea su Skype para administración empresarial.</span><span class="sxs-lookup"><span data-stu-id="89fbe-118">See your Skype for Business admin if you need help with permissions.</span></span>
  
 <span data-ttu-id="89fbe-119">**Análisis de llamar Open como un agente de departamento de soporte técnico de nivel 1 o nivel 2**</span><span class="sxs-lookup"><span data-stu-id="89fbe-119">**Open Call Analytics as a Tier 1 or Tier 2 helpdesk agent**</span></span>
  
1. <span data-ttu-id="89fbe-120">Vaya al centro de administración de Office 365 e iniciar sesión con su cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="89fbe-120">Go to the Office 365 admin center and sign in using your work or school account.</span></span> <span data-ttu-id="89fbe-121">A continuación, en el explorador web vaya a *https://adminportal.services.skypeforbusiness.com*.</span><span class="sxs-lookup"><span data-stu-id="89fbe-121">Then in your web browser go to *https://adminportal.services.skypeforbusiness.com*.</span></span>
    
2. <span data-ttu-id="89fbe-122">En la **Búsqueda de usuarios**, empiece a escribir el nombre o el sip dirección del usuario cuyas llamadas que desea solucionar problemas y, a continuación, seleccione el usuario en la lista.</span><span class="sxs-lookup"><span data-stu-id="89fbe-122">In **User Search**, start typing either the name or sip address of the user whose calls you want to troubleshoot and then select the user from the list.</span></span>
    
    ![Captura de pantalla del cuadro de búsqueda de usuarios del análisis de llamadas en la Skype para el centro de administración de negocio.](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. <span data-ttu-id="89fbe-124">En el **historial de llamadas**, seleccione la llamada o reunión que va a solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="89fbe-124">In **Call history**, select the call or meeting that you want to troubleshoot.</span></span>
    
    ![Captura de pantalla muestra la página de historial de llamadas para un usuario con información como detalles de contacto del usuario, un resumen de la actividad para las reuniones y las llamadas y calidad de 7 días e información general de las fechas y horas, destinatarios y una calidad de audio,](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. <span data-ttu-id="89fbe-126">Seleccione la ficha **Opciones avanzadas** y, a continuación, busque elementos de amarillos y rojos que indican problemas de calidad o conexión llamada deficiente.</span><span class="sxs-lookup"><span data-stu-id="89fbe-126">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="89fbe-127">En los detalles de la sesión para cada llamada o una reunión, problemas secundarias aparecen en amarillo.</span><span class="sxs-lookup"><span data-stu-id="89fbe-127">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="89fbe-128">(Por ejemplo, en la siguiente captura de pantalla, los valores están en amarillo para vibración Media, la vibración de Max y la frecuencia de pérdida de paquetes promedio.) Si algo es el amarillo, está fuera del intervalo normal y puede contribuir al problema, pero es poco probable que sea la causa principal del problema.</span><span class="sxs-lookup"><span data-stu-id="89fbe-128">(For example, in the following screenshot, the values are in yellow for Average jitter, Max jitter, and Average packet loss rate.) If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="89fbe-129">Si algo es rojo, es un problema importante, y es probable que es la causa principal de la calidad de llamadas deficientes para esta sesión.</span><span class="sxs-lookup"><span data-stu-id="89fbe-129">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
    
    ![Captura de pantalla muestra la ficha Avanzadas del historial de llamadas de un usuario con la sección de red entrantes expandida para mostrar que se muestran los datos de vibración Media, Vibración máxima y tasa de pérdida de paquetes Media en un color amarillo, lo que significa que son secundarias problemas.](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
<span data-ttu-id="89fbe-131">En algunos casos poco frecuentes, no se recibió calidad de experiencia de datos para las sesiones de audioconferencias.</span><span class="sxs-lookup"><span data-stu-id="89fbe-131">In rare cases, quality of experience data isn't received for audio sessions.</span></span> <span data-ttu-id="89fbe-132">A menudo esto está causado por la llamada quitando y la conexión con el cliente de terminación.</span><span class="sxs-lookup"><span data-stu-id="89fbe-132">Often this is caused by the call dropping and connection with the client terminating.</span></span> <span data-ttu-id="89fbe-133">Cuando esto ocurre, la clasificación de la sesión es "no disponible".</span><span class="sxs-lookup"><span data-stu-id="89fbe-133">When this occurs, the session rating is "unavailable".</span></span>
  
<span data-ttu-id="89fbe-134">Para las sesiones de audioconferencias que tienen la calidad de los datos de la experiencia (QoE), en la siguiente tabla se describe los problemas principales que calificar una sesión como "malo".</span><span class="sxs-lookup"><span data-stu-id="89fbe-134">For audio sessions that do have quality of experience (QoE) data, the following table describes major issues that qualify a session as "poor."</span></span>
  
|<span data-ttu-id="89fbe-135">**Problema**</span><span class="sxs-lookup"><span data-stu-id="89fbe-135">**Issue**</span></span>|<span data-ttu-id="89fbe-136">**Área**</span><span class="sxs-lookup"><span data-stu-id="89fbe-136">**Area**</span></span>|<span data-ttu-id="89fbe-137">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="89fbe-137">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="89fbe-138">Programa de instalación de la llamada</span><span class="sxs-lookup"><span data-stu-id="89fbe-138">Call setup</span></span>  <br/> |<span data-ttu-id="89fbe-139">Sesión</span><span class="sxs-lookup"><span data-stu-id="89fbe-139">Session</span></span>  <br/> |<span data-ttu-id="89fbe-140">El código de error de que MS-diag 20-29 indica el error en la configuración de la llamada.</span><span class="sxs-lookup"><span data-stu-id="89fbe-140">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="89fbe-141">El usuario no puede unirse a la llamada o reunión.</span><span class="sxs-lookup"><span data-stu-id="89fbe-141">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="89fbe-142">Red audio clasificados llamada deficiente</span><span class="sxs-lookup"><span data-stu-id="89fbe-142">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="89fbe-143">Sesión</span><span class="sxs-lookup"><span data-stu-id="89fbe-143">Session</span></span>  <br/> |<span data-ttu-id="89fbe-144">Problemas de calidad de red se han producido en áreas como la pérdida de paquetes, vibración, degradación de NMOS, RTT, u ocultan relación.</span><span class="sxs-lookup"><span data-stu-id="89fbe-144">Network quality issues were encountered in areas such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio.</span></span> <span data-ttu-id="89fbe-145">Para obtener más información acerca de las condiciones que se usan para clasificar las llamadas deficientes, vea esta [entrada de blog de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=852133).</span><span class="sxs-lookup"><span data-stu-id="89fbe-145">For more information about the conditions used to classify poor calls, see this [Microsoft blog post](https://go.microsoft.com/fwlink/p/?linkid=852133).</span></span>  <br/> |
|<span data-ttu-id="89fbe-146">Dispositivo no funciona</span><span class="sxs-lookup"><span data-stu-id="89fbe-146">Device not functioning</span></span>  <br/> |<span data-ttu-id="89fbe-147">Dispositivo</span><span class="sxs-lookup"><span data-stu-id="89fbe-147">Device</span></span>  <br/> | <span data-ttu-id="89fbe-148">Un dispositivo no está funcionando correctamente.</span><span class="sxs-lookup"><span data-stu-id="89fbe-148">A device isn't functioning correctly.</span></span> <span data-ttu-id="89fbe-149">Dispositivo no funciona proporciones es:</span><span class="sxs-lookup"><span data-stu-id="89fbe-149">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="89fbe-150">DeviceRenderNotFunctioningEventRatio > = 0,005</span><span class="sxs-lookup"><span data-stu-id="89fbe-150">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="89fbe-151">DeviceCaptureNotFunctioningEventRatio > = 0,005</span><span class="sxs-lookup"><span data-stu-id="89fbe-151">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="89fbe-152">See also</span><span class="sxs-lookup"><span data-stu-id="89fbe-152">Related topics</span></span>
[<span data-ttu-id="89fbe-153">Configurar el análisis de llamadas de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="89fbe-153">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="89fbe-154">Análisis de llamada y el panel de calidad de llamada</span><span class="sxs-lookup"><span data-stu-id="89fbe-154">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 