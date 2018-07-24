---
title: Informe de detalles de conferencia en Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 'Resumen: Información sobre el informe de detalles de conferencia usadas en Skype para Business Server.'
ms.openlocfilehash: ebccaf35464c54eac6c1b8c5a2febf2ebea02b7e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20971318"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a><span data-ttu-id="d1dbd-103">Informe de detalles de conferencia en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="d1dbd-103">Conference Detail Report in Skype for Business Server</span></span>
 
<span data-ttu-id="d1dbd-104">**Resumen:** Obtenga información sobre el informe de detalles de conferencia usadas en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="d1dbd-104">**Summary:** Learn about the Conference Detail Report used in Skype for Business Server.</span></span>
  
<span data-ttu-id="d1dbd-p101">El Informe de detalles de conferencia proporciona información detallada sobre todos los usuarios que participaron en una conferencia. Por ejemplo, puede ver información como la fecha y hora en que un usuario se conectó a la conferencia, la fecha y hora en la que el usuario se desconectó de la conferencia y el agente del usuario del extremo que se utilizó para conectar a ese usuario a la conferencia. También puede ver información sobre el rol del usuario en cada conferencia (por ejemplo, moderador o asistente). Quizás lo más importante, puede ver rápidamente qué usuarios se conectan satisfactoriamente y finalizan la conferencia y qué usuarios no pudieron conectarse satisfactoriamente ni finalizar la conferencia.</span><span class="sxs-lookup"><span data-stu-id="d1dbd-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>
  
## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="d1dbd-109">Acceso al Informe de detalles de conferencia</span><span class="sxs-lookup"><span data-stu-id="d1dbd-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="d1dbd-110">Es posible obtener acceso al Informe de detalles de conferencia a partir de los siguientes informes:</span><span class="sxs-lookup"><span data-stu-id="d1dbd-110">The Conference Detail Report can be accessed from the following reports:</span></span>
  
- <span data-ttu-id="d1dbd-111">El [Informe del Control de admisión de llamadas en Skype para Business Server](call-admission-control-report.md) (haciendo clic en la métrica detalle de una conferencia)</span><span class="sxs-lookup"><span data-stu-id="d1dbd-111">The [Call Admission Control Report in Skype for Business Server](call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>
    
- <span data-ttu-id="d1dbd-112">El [Informe de lista de errores en Skype para Business Server](failure-list-report.md) (haciendo clic en la métrica conferencia)</span><span class="sxs-lookup"><span data-stu-id="d1dbd-112">The [Failure List Report in Skype for Business Server](failure-list-report.md) (by clicking the Conference metric)</span></span>
    
- <span data-ttu-id="d1dbd-113">El [Informe de actividad de usuario en Skype para Business Server](user-activity-report.md) (haciendo clic en la métrica URI de conferencia)</span><span class="sxs-lookup"><span data-stu-id="d1dbd-113">The [User Activity Report in Skype for Business Server](user-activity-report.md) (by clicking the Conference URI metric)</span></span>
    
<span data-ttu-id="d1dbd-114">Desde el informe de detalles de conferencia, puede acceder al [Informe de diagnóstico en Skype para Business Server](diagnostic-report.md) haciendo clic en la métrica informe de diagnósticos (detalle).</span><span class="sxs-lookup"><span data-stu-id="d1dbd-114">From the Conference Detail Report you can access the [Diagnostic Report in Skype for Business Server](diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>
  
## <a name="filters"></a><span data-ttu-id="d1dbd-115">Filtros</span><span class="sxs-lookup"><span data-stu-id="d1dbd-115">Filters</span></span>

<span data-ttu-id="d1dbd-p102">Ninguno. No se puede filtrar el Informe de detalles de conferencia.</span><span class="sxs-lookup"><span data-stu-id="d1dbd-p102">None. You cannot filter on the Conference Detail Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="d1dbd-118">Métricas</span><span class="sxs-lookup"><span data-stu-id="d1dbd-118">Metrics</span></span>

<span data-ttu-id="d1dbd-119">La siguiente tabla muestra la información brindada en la sección Información de conferencia del Informe de detalles de conferencia.</span><span class="sxs-lookup"><span data-stu-id="d1dbd-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>
  
<span data-ttu-id="d1dbd-120">**Métricas de Información de conferencia**</span><span class="sxs-lookup"><span data-stu-id="d1dbd-120">**Conference Information Metrics**</span></span>

|<span data-ttu-id="d1dbd-121">**Nombre.**</span><span class="sxs-lookup"><span data-stu-id="d1dbd-121">**Name**</span></span>|<span data-ttu-id="d1dbd-122">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d1dbd-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d1dbd-123">**URI de conferencia**</span><span class="sxs-lookup"><span data-stu-id="d1dbd-123">**Conference URI**</span></span> <br/> |<span data-ttu-id="d1dbd-p103">URI asignado a la conferencia. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d1dbd-p103">URI assigned to the conference. For example:</span></span>  <br/> <span data-ttu-id="d1dbd-126">SIP:kmyer@litwareinc.com;GRUU;OPAQUE=App:conf:Focus:ID:drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="d1dbd-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span>  <br/> |
|<span data-ttu-id="d1dbd-127">**FQDN del grupo de servidores**</span><span class="sxs-lookup"><span data-stu-id="d1dbd-127">**Pool FQDN**</span></span> <br/> |<span data-ttu-id="d1dbd-128">Nombre de dominio completo del grupo de registrador o servidor perimetral involucrado en una sesión.</span><span class="sxs-lookup"><span data-stu-id="d1dbd-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span>  <br/> |
|<span data-ttu-id="d1dbd-129">**Hora de inicio**</span><span class="sxs-lookup"><span data-stu-id="d1dbd-129">**Start time**</span></span> <br/> |<span data-ttu-id="d1dbd-130">Fecha y hora en que comenzó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="d1dbd-130">Date and time that the conference started.</span></span>  <br/> |
|<span data-ttu-id="d1dbd-131">**Organizador**</span><span class="sxs-lookup"><span data-stu-id="d1dbd-131">**Organizer**</span></span> <br/> |<span data-ttu-id="d1dbd-132">Dirección SIP del usuario que organizó la conferencia</span><span class="sxs-lookup"><span data-stu-id="d1dbd-132">SIP address of the user who organized the conference.</span></span>  <br/> |
|<span data-ttu-id="d1dbd-133">**Hora de finalización**</span><span class="sxs-lookup"><span data-stu-id="d1dbd-133">**End time**</span></span> <br/> |<span data-ttu-id="d1dbd-134">Fecha y hora en que la conferencia finalizó.</span><span class="sxs-lookup"><span data-stu-id="d1dbd-134">Date and time that the conference ended.</span></span>  <br/> |
   
<span data-ttu-id="d1dbd-135">La siguiente tabla muestra la información brindada en la sección Participación de conferencia del Informe de detalles de conferencia.</span><span class="sxs-lookup"><span data-stu-id="d1dbd-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>
  
<span data-ttu-id="d1dbd-136">**Métricas de Participación de conferencia**</span><span class="sxs-lookup"><span data-stu-id="d1dbd-136">**Conference Participation Metrics**</span></span>

|<span data-ttu-id="d1dbd-137">**Nombre.**</span><span class="sxs-lookup"><span data-stu-id="d1dbd-137">**Name**</span></span>|<span data-ttu-id="d1dbd-138">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d1dbd-138">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d1dbd-139">**Usuario**</span><span class="sxs-lookup"><span data-stu-id="d1dbd-139">**User**</span></span> <br/> |<span data-ttu-id="d1dbd-140">Dirección SIP del usuario que participó en la conferencia.</span><span class="sxs-lookup"><span data-stu-id="d1dbd-140">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="d1dbd-141">**Rol**</span><span class="sxs-lookup"><span data-stu-id="d1dbd-141">**Role**</span></span> <br/> |<span data-ttu-id="d1dbd-142">Rol (por ejemplo, Moderador) que ocupó el participante de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="d1dbd-142">Role (for example, Presenter) played by the conference participant.</span></span>  <br/> |
|<span data-ttu-id="d1dbd-143">**Conectividad**</span><span class="sxs-lookup"><span data-stu-id="d1dbd-143">**Connectivity**</span></span> <br/> |<span data-ttu-id="d1dbd-144">Conectividad de red (normalmente Desde conexión interna o Desde conexión externa) del participante.</span><span class="sxs-lookup"><span data-stu-id="d1dbd-144">Network connectivity (typically From Internal or From External) for the participant.</span></span>  <br/> |
|<span data-ttu-id="d1dbd-145">**Hora de conexión**</span><span class="sxs-lookup"><span data-stu-id="d1dbd-145">**Join time**</span></span> <br/> |<span data-ttu-id="d1dbd-146">Fecha y hora en que el participante se unió a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="d1dbd-146">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="d1dbd-147">**Hora de desconexión**</span><span class="sxs-lookup"><span data-stu-id="d1dbd-147">**Leave time**</span></span> <br/> |<span data-ttu-id="d1dbd-148">Fecha y hora en que el participante abandonó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="d1dbd-148">Date and time that the participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="d1dbd-149">**Agente de usuario**</span><span class="sxs-lookup"><span data-stu-id="d1dbd-149">**User agent**</span></span> <br/> |<span data-ttu-id="d1dbd-150">Identificador del software del extremo del participante.</span><span class="sxs-lookup"><span data-stu-id="d1dbd-150">Identifier for the software used by the participant's endpoint.</span></span>  <br/> |
|<span data-ttu-id="d1dbd-151">**Informes de diagnósticos**</span><span class="sxs-lookup"><span data-stu-id="d1dbd-151">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="d1dbd-p104">Proporciona información de diagnóstico y resolución de problemas. Por ejemplo, códigos de respuesta SIP, encabezados de diagnóstico, horarios de conexión a conferencias e identificadores de diagnóstico para sesiones fallidas.</span><span class="sxs-lookup"><span data-stu-id="d1dbd-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |
   
<span data-ttu-id="d1dbd-154">En la siguiente tabla se enumera la información proporcionada en la sección modalidades de conferencia del informe de detalles de conferencia.</span><span class="sxs-lookup"><span data-stu-id="d1dbd-154">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>
  
<span data-ttu-id="d1dbd-155">**Métricas de Modalidades de conferencia**</span><span class="sxs-lookup"><span data-stu-id="d1dbd-155">**Conference Modalities Metrics**</span></span>

|<span data-ttu-id="d1dbd-156">**Nombre.**</span><span class="sxs-lookup"><span data-stu-id="d1dbd-156">**Name**</span></span>|<span data-ttu-id="d1dbd-157">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d1dbd-157">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d1dbd-158">**Usuario**</span><span class="sxs-lookup"><span data-stu-id="d1dbd-158">**User**</span></span> <br/> |<span data-ttu-id="d1dbd-159">Dirección SIP del usuario que participó en la conferencia.</span><span class="sxs-lookup"><span data-stu-id="d1dbd-159">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="d1dbd-160">**Hora de conexión**</span><span class="sxs-lookup"><span data-stu-id="d1dbd-160">**Join time**</span></span> <br/> |<span data-ttu-id="d1dbd-161">Fecha y hora en que el participante se unió a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="d1dbd-161">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="d1dbd-162">**Hora de desconexión**</span><span class="sxs-lookup"><span data-stu-id="d1dbd-162">**Leave time**</span></span> <br/> |<span data-ttu-id="d1dbd-163">Fecha y hora en que un participante abandonó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="d1dbd-163">Date and time that a participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="d1dbd-164">**URI del servidor de conferencia**</span><span class="sxs-lookup"><span data-stu-id="d1dbd-164">**Conferencing server URI**</span></span> <br/> |<span data-ttu-id="d1dbd-165">URI para el servidor de conferencia utilizado en la conferencia.</span><span class="sxs-lookup"><span data-stu-id="d1dbd-165">URI for the Conferencing server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="d1dbd-166">**Informes de diagnósticos**</span><span class="sxs-lookup"><span data-stu-id="d1dbd-166">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="d1dbd-p105">Proporciona información de diagnóstico y resolución de problemas. Por ejemplo, códigos de respuesta SIP, encabezados de diagnóstico, horarios de conexión a conferencias e identificadores de diagnóstico para sesiones fallidas.</span><span class="sxs-lookup"><span data-stu-id="d1dbd-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |
   

