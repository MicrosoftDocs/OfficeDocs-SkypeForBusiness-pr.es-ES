---
title: Calidad de las llamadas uso llamar Analytics solucionar pobre Skype para empresas
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
description: "Utilizar detalles de llamar análisis sobre conectividad, redes y dispositivos para solucionar problemas de usuarios con Skype para llamadas de negocios y reuniones."
ms.openlocfilehash: cbb728c14c58393a5ec71cc538ad958ba58fb947
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2018
---
# <a name="use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality"></a><span data-ttu-id="5a512-103">Calidad de las llamadas uso llamar Analytics solucionar pobre Skype para empresas</span><span class="sxs-lookup"><span data-stu-id="5a512-103">Use Call Analytics to troubleshoot poor Skype for Business call quality</span></span>

<span data-ttu-id="5a512-104">Llamada Analytics le ayuda a solucionar problemas de conexión o llamada con Skype para el negocio.</span><span class="sxs-lookup"><span data-stu-id="5a512-104">Call Analytics helps you to troubleshoot call or connection problems with Skype for Business.</span></span> <span data-ttu-id="5a512-105">Llamada Analytics muestra información detallada acerca de los dispositivos, redes y conectividad de las llamadas y reuniones de cada usuario en su Skype para la cuenta de empresa.</span><span class="sxs-lookup"><span data-stu-id="5a512-105">Call Analytics shows detailed information about the devices, networks, and connectivity for the calls and meetings of each user in your Skype for Business account.</span></span> <span data-ttu-id="5a512-106">Si el edificio, del sitio y de inquilinos se ha agregado información al llamar a Analytics, también se mostrará para cada llamada y sesión.</span><span class="sxs-lookup"><span data-stu-id="5a512-106">If building, site, and tenant information has been added to Call Analytics, it will also be shown for each call and session.</span></span> <span data-ttu-id="5a512-107">Información disponible a través de llamar Analytics puede ayudar a averiguar por qué un usuario tenía una llamada deficiente o experiencia de reunión.</span><span class="sxs-lookup"><span data-stu-id="5a512-107">Information available via Call Analytics can help you figure out why a user had a poor call or meeting experience.</span></span> 
  
    > [!NOTE]
    > Call Analytics is currently in preview. Text and images described here may not match your experience. 
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a><span data-ttu-id="5a512-108">Solucionar problemas de calidad de llamada utilizando Analytics llamar</span><span class="sxs-lookup"><span data-stu-id="5a512-108">Troubleshoot call quality problems using Call Analytics</span></span>

<span data-ttu-id="5a512-109">El nivel de permisos asignado a usted determina qué tipo de información tiene acceso a en llamar Analytics:</span><span class="sxs-lookup"><span data-stu-id="5a512-109">The permissions level assigned to you determines what type of information you have access to in Call Analytics:</span></span>
  
- <span data-ttu-id="5a512-110">**Skype para Business admin**: tendrá acceso a toda la información en llamar a Analytics y en el Skype para el centro de administración de negocios.</span><span class="sxs-lookup"><span data-stu-id="5a512-110">**Skype for Business admin**: You have access to all the information in Call Analytics and in the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="5a512-111">**Agente de asistencia técnica con permisos de nivel 1**: vea un conjunto limitado de datos en Analytics llamar.</span><span class="sxs-lookup"><span data-stu-id="5a512-111">**Helpdesk agent with Tier 1 permissions**: You see a limited set of data in Call Analytics.</span></span> <span data-ttu-id="5a512-112">Puede solucionar problemas de las llamadas, pero le entrega problemas con reuniones a un agente de nivel 2.</span><span class="sxs-lookup"><span data-stu-id="5a512-112">You can troubleshoot calls, but you'll hand off problems with meetings to a Tier 2 agent.</span></span> <span data-ttu-id="5a512-113">No tiene acceso al resto de la Skype para el centro de administración de negocios.</span><span class="sxs-lookup"><span data-stu-id="5a512-113">You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="5a512-114">**Agente de asistencia técnica con permisos de nivel 2**: ver todos los datos disponibles en llamar a Analytics y puede ayudar a solucionar problemas relacionados con llamadas y reuniones.</span><span class="sxs-lookup"><span data-stu-id="5a512-114">**Helpdesk agent with Tier 2 permissions**: You see all available data in Call Analytics and can help troubleshoot problems with both calls and meetings.</span></span> <span data-ttu-id="5a512-115">No tiene acceso al resto de la Skype para el centro de administración de negocios.</span><span class="sxs-lookup"><span data-stu-id="5a512-115">You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
<span data-ttu-id="5a512-116">Consulte su Skype para Business admin si necesita ayuda con los permisos.</span><span class="sxs-lookup"><span data-stu-id="5a512-116">See your Skype for Business admin if you need help with permissions.</span></span>
  
 <span data-ttu-id="5a512-117">**Abrir llamar Analytics como un agente de asistencia de nivel 1 o nivel 2**</span><span class="sxs-lookup"><span data-stu-id="5a512-117">**Open Call Analytics as a Tier 1 or Tier 2 helpdesk agent**</span></span>
  
1. <span data-ttu-id="5a512-118">Ir al centro de administración de Office 365 e inicie sesión con su cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="5a512-118">Go to the Office 365 admin center and sign in using your work or school account.</span></span> <span data-ttu-id="5a512-119">A continuación, en el explorador web vaya a *https://adminportal.services.skypeforbusiness.com*.</span><span class="sxs-lookup"><span data-stu-id="5a512-119">Then in your web browser go to *https://adminportal.services.skypeforbusiness.com*.</span></span>
    
2. <span data-ttu-id="5a512-120">En **La búsqueda de usuarios**, empiece a escribir la dirección o el nombre o el sip del usuario cuyas llamadas que desee solucionar y, a continuación, seleccione el usuario de la lista.</span><span class="sxs-lookup"><span data-stu-id="5a512-120">In **User Search**, start typing either the name or sip address of the user whose calls you want to troubleshoot and then select the user from the list.</span></span>
    
    ![Captura de pantalla del cuadro de búsqueda de usuarios de Analytics llamar en el Skype para el centro de administración de negocios.](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. <span data-ttu-id="5a512-122">En el **historial de llamadas**, seleccione la llamada o reunión que desee solucionar.</span><span class="sxs-lookup"><span data-stu-id="5a512-122">In **Call history**, select the call or meeting that you want to troubleshoot.</span></span>
    
    ![Captura de pantalla muestra la página de historial de llamadas para un usuario con información como detalles de contacto del usuario, un resumen de la calidad de 7 días y la actividad de llamadas y reuniones y un resumen de las fechas y horas, destinatarios y calidad de audio,](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. <span data-ttu-id="5a512-124">Seleccione la ficha **Avanzadas** y, a continuación, busque elementos de amarillos y rojos que indican la llamada mala calidad o problemas de conexión.</span><span class="sxs-lookup"><span data-stu-id="5a512-124">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="5a512-125">En los detalles de la sesión de cada llamada o una reunión, problemas de poca importancia aparecen en amarillo.</span><span class="sxs-lookup"><span data-stu-id="5a512-125">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="5a512-126">(Por ejemplo, en la siguiente captura de pantalla, los valores son en color amarillo para variación promedio, variación máxima y tasa de pérdida de paquetes promedio.) Si algo es amarillo, está fuera del intervalo normal y podría estar contribuyendo al problema, pero es poco probable que la causa principal del problema.</span><span class="sxs-lookup"><span data-stu-id="5a512-126">(For example, in the following screenshot, the values are in yellow for Average jitter, Max jitter, and Average packet loss rate.) If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="5a512-127">Si algo es rojo, es un problema importante, y es probable que la causa principal de la calidad de las llamadas deficiente para esta sesión.</span><span class="sxs-lookup"><span data-stu-id="5a512-127">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
    
    ![Captura de pantalla muestra la ficha Opciones avanzadas del historial de llamadas de un usuario con la sección de red entrantes expandida para mostrar que los datos de variación promedio, variación máxima y tasa de pérdida de paquetes promedio se muestran en un color amarillo, lo que significa que son problemas de poca importancia.](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
<span data-ttu-id="5a512-129">En raras ocasiones, no recibe la calidad de los datos de la experiencia para sesiones de audio.</span><span class="sxs-lookup"><span data-stu-id="5a512-129">In rare cases, quality of experience data isn't received for audio sessions.</span></span> <span data-ttu-id="5a512-130">A menudo esto se debe a la eliminación de llamada y la conexión con el cliente termina.</span><span class="sxs-lookup"><span data-stu-id="5a512-130">Often this is caused by the call dropping and connection with the client terminating.</span></span> <span data-ttu-id="5a512-131">Cuando esto ocurre, la clasificación de la sesión es "no disponible".</span><span class="sxs-lookup"><span data-stu-id="5a512-131">When this occurs, the session rating is "unavailable".</span></span>
  
<span data-ttu-id="5a512-132">Para las sesiones de audio con calidad de experiencia (QoE) datos, la tabla siguiente describe los principales problemas que califican una sesión como "pobre".</span><span class="sxs-lookup"><span data-stu-id="5a512-132">For audio sessions that do have quality of experience (QoE) data, the following table describes major issues that qualify a session as "poor."</span></span>
  
|<span data-ttu-id="5a512-133">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5a512-133">**Issue**</span></span>|<span data-ttu-id="5a512-134">**Área**</span><span class="sxs-lookup"><span data-stu-id="5a512-134">**Area**</span></span>|<span data-ttu-id="5a512-135">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5a512-135">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5a512-136">Configuración de llamada</span><span class="sxs-lookup"><span data-stu-id="5a512-136">Call setup</span></span>  <br/> |<span data-ttu-id="5a512-137">Sesión</span><span class="sxs-lookup"><span data-stu-id="5a512-137">Session</span></span>  <br/> |<span data-ttu-id="5a512-138">El código de error Ms-diag 20-29 indica error en la configuración de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5a512-138">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="5a512-139">El usuario no pudo unirse a la llamada o reunión.</span><span class="sxs-lookup"><span data-stu-id="5a512-139">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="5a512-140">Audio red clasificada llamada deficiente</span><span class="sxs-lookup"><span data-stu-id="5a512-140">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="5a512-141">Sesión</span><span class="sxs-lookup"><span data-stu-id="5a512-141">Session</span></span>  <br/> |<span data-ttu-id="5a512-142">Problemas de calidad de la red se encontraron en áreas como la pérdida de paquetes, vibración, degradación NMOS, RTT, u ocultan la relación.</span><span class="sxs-lookup"><span data-stu-id="5a512-142">Network quality issues were encountered in areas such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio.</span></span> <span data-ttu-id="5a512-143">Para obtener más información acerca de las condiciones utilizadas para clasificar las llamadas deficientes, consulte este [blog de Microsoft registra](https://go.microsoft.com/fwlink/p/?linkid=852133).</span><span class="sxs-lookup"><span data-stu-id="5a512-143">For more information about the conditions used to classify poor calls, see this [Microsoft blog post](https://go.microsoft.com/fwlink/p/?linkid=852133).</span></span>  <br/> |
|<span data-ttu-id="5a512-144">Dispositivo no funciona</span><span class="sxs-lookup"><span data-stu-id="5a512-144">Device not functioning</span></span>  <br/> |<span data-ttu-id="5a512-145">Dispositivo</span><span class="sxs-lookup"><span data-stu-id="5a512-145">Device</span></span>  <br/> | <span data-ttu-id="5a512-146">Un dispositivo no está funcionando correctamente.</span><span class="sxs-lookup"><span data-stu-id="5a512-146">A device isn't functioning correctly.</span></span> <span data-ttu-id="5a512-147">Dispositivo no funciona proporciones es:</span><span class="sxs-lookup"><span data-stu-id="5a512-147">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="5a512-148">DeviceRenderNotFunctioningEventRatio > = 0,005</span><span class="sxs-lookup"><span data-stu-id="5a512-148">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="5a512-149">DeviceCaptureNotFunctioningEventRatio > = 0,005</span><span class="sxs-lookup"><span data-stu-id="5a512-149">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="5a512-150">See also</span><span class="sxs-lookup"><span data-stu-id="5a512-150">Related topics</span></span>
[<span data-ttu-id="5a512-151">Configurar el análisis de llamadas de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="5a512-151">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="5a512-152">Diferencia entre el análisis de llamadas y el Panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="5a512-152">What's the difference between Call Analytics and Call Quality Dashboard?</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

## <a name="feedback"></a><span data-ttu-id="5a512-153">¿Comentarios?</span><span class="sxs-lookup"><span data-stu-id="5a512-153">Feedback?</span></span>
<span data-ttu-id="5a512-154">Para proporcionar comentarios sobre el producto o para hacernos saber cómo lo estamos haciendo, vea [Skype para comentarios de comercio](https://www.skypefeedback.com).</span><span class="sxs-lookup"><span data-stu-id="5a512-154">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>