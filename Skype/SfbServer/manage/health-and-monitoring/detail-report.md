---
title: Informe detallado de la Conferencia en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 'Resumen: Obtenga información sobre el informe de detalles de conferencia usado en Skype empresarial Server.'
ms.openlocfilehash: 17337624c955dfa174f7b98772fdd836e82891d0
ms.sourcegitcommit: 6cbdcb8606044ad7ab49a4e3c828c2dc3d50fcc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/09/2019
ms.locfileid: "36271406"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a><span data-ttu-id="cffa5-103">Informe detallado de la Conferencia en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="cffa5-103">Conference Detail Report in Skype for Business Server</span></span>

<span data-ttu-id="cffa5-104">**Resumen:** Obtenga más información sobre el informe de detalles de la Conferencia usado en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="cffa5-104">**Summary:** Learn about the Conference Detail Report used in Skype for Business Server.</span></span>

<span data-ttu-id="cffa5-p101">El Informe de detalles de conferencia proporciona información detallada sobre todos los usuarios que participaron en una conferencia. Por ejemplo, puede ver información como la fecha y hora en que un usuario se conectó a la conferencia, la fecha y hora en la que el usuario se desconectó de la conferencia y el agente del usuario del extremo que se utilizó para conectar a ese usuario a la conferencia. También puede ver información sobre el rol del usuario en cada conferencia (por ejemplo, moderador o asistente). Quizás lo más importante, puede ver rápidamente qué usuarios se conectan satisfactoriamente y finalizan la conferencia y qué usuarios no pudieron conectarse satisfactoriamente ni finalizar la conferencia.</span><span class="sxs-lookup"><span data-stu-id="cffa5-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="cffa5-109">Acceso al Informe de detalles de conferencia</span><span class="sxs-lookup"><span data-stu-id="cffa5-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="cffa5-110">Es posible obtener acceso al Informe de detalles de conferencia a partir de los siguientes informes:</span><span class="sxs-lookup"><span data-stu-id="cffa5-110">The Conference Detail Report can be accessed from the following reports:</span></span>

- <span data-ttu-id="cffa5-111">El [Call Admission Control Report](call-admission-control-report.md) (haciendo clic en la métrica Detalle de una conferencia)</span><span class="sxs-lookup"><span data-stu-id="cffa5-111">The [Call Admission Control Report](call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

- <span data-ttu-id="cffa5-112">El [Failure List Report](failure-list-report.md) (haciendo clic en la métrica Conferencia)</span><span class="sxs-lookup"><span data-stu-id="cffa5-112">The [Failure List Report](failure-list-report.md) (by clicking the Conference metric)</span></span>

- <span data-ttu-id="cffa5-113">El [User Activity Report](call-diagnostic-reports-per-user.md) (haciendo clic en la métrica URI de conferencia)</span><span class="sxs-lookup"><span data-stu-id="cffa5-113">The [User Activity Report](call-diagnostic-reports-per-user.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="cffa5-114">Desde el Informe de detalles de conferencia, puede obtener acceso al [Diagnostic Report](diagnostic-report.md) haciendo clic en la métrica Informe de diagnósticos (Detalle).</span><span class="sxs-lookup"><span data-stu-id="cffa5-114">From the Conference Detail Report you can access the [Diagnostic Report](diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

## <a name="filters"></a><span data-ttu-id="cffa5-115">Filtros</span><span class="sxs-lookup"><span data-stu-id="cffa5-115">Filters</span></span>

<span data-ttu-id="cffa5-p102">Ninguno. No se puede filtrar el Informe de detalles de conferencia.</span><span class="sxs-lookup"><span data-stu-id="cffa5-p102">None. You cannot filter on the Conference Detail Report.</span></span>

## <a name="metrics"></a><span data-ttu-id="cffa5-118">Métricas</span><span class="sxs-lookup"><span data-stu-id="cffa5-118">Metrics</span></span>

<span data-ttu-id="cffa5-119">La siguiente tabla muestra la información brindada en la sección Información de conferencia del Informe de detalles de conferencia.</span><span class="sxs-lookup"><span data-stu-id="cffa5-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

<span data-ttu-id="cffa5-120">**Métricas de Información de conferencia**</span><span class="sxs-lookup"><span data-stu-id="cffa5-120">**Conference Information Metrics**</span></span>


| <span data-ttu-id="cffa5-121">**Nombre.**</span><span class="sxs-lookup"><span data-stu-id="cffa5-121">**Name**</span></span>                 | <span data-ttu-id="cffa5-122">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="cffa5-122">**Description**</span></span>                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="cffa5-123">**URI de conferencia**</span><span class="sxs-lookup"><span data-stu-id="cffa5-123">**Conference URI**</span></span> <br/> | <span data-ttu-id="cffa5-p103">URI asignado a la conferencia. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cffa5-p103">URI assigned to the conference. For example:</span></span>  <br/> <span data-ttu-id="cffa5-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="cffa5-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span>  <br/> |
| <span data-ttu-id="cffa5-127">**FQDN del grupo de servidores**</span><span class="sxs-lookup"><span data-stu-id="cffa5-127">**Pool FQDN**</span></span> <br/>      | <span data-ttu-id="cffa5-128">Nombre de dominio completo del grupo de registrador o servidor perimetral involucrado en una sesión.</span><span class="sxs-lookup"><span data-stu-id="cffa5-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span>  <br/>                             |
| <span data-ttu-id="cffa5-129">**Hora de inicio**</span><span class="sxs-lookup"><span data-stu-id="cffa5-129">**Start time**</span></span> <br/>     | <span data-ttu-id="cffa5-130">Fecha y hora en que comenzó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="cffa5-130">Date and time that the conference started.</span></span>  <br/>                                                                          |
| <span data-ttu-id="cffa5-131">**Organizador**</span><span class="sxs-lookup"><span data-stu-id="cffa5-131">**Organizer**</span></span> <br/>      | <span data-ttu-id="cffa5-132">Dirección SIP del usuario que organizó la conferencia</span><span class="sxs-lookup"><span data-stu-id="cffa5-132">SIP address of the user who organized the conference.</span></span>  <br/>                                                               |
| <span data-ttu-id="cffa5-133">**Hora de finalización**</span><span class="sxs-lookup"><span data-stu-id="cffa5-133">**End time**</span></span> <br/>       | <span data-ttu-id="cffa5-134">Fecha y hora en que la conferencia finalizó.</span><span class="sxs-lookup"><span data-stu-id="cffa5-134">Date and time that the conference ended.</span></span>  <br/>                                                                            |

<span data-ttu-id="cffa5-135">La siguiente tabla muestra la información brindada en la sección Participación de conferencia del Informe de detalles de conferencia.</span><span class="sxs-lookup"><span data-stu-id="cffa5-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

<span data-ttu-id="cffa5-136">**Métricas de Participación de conferencia**</span><span class="sxs-lookup"><span data-stu-id="cffa5-136">**Conference Participation Metrics**</span></span>

|<span data-ttu-id="cffa5-137">**Nombre.**</span><span class="sxs-lookup"><span data-stu-id="cffa5-137">**Name**</span></span>|<span data-ttu-id="cffa5-138">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="cffa5-138">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cffa5-139">**Usuario**</span><span class="sxs-lookup"><span data-stu-id="cffa5-139">**User**</span></span> <br/> |<span data-ttu-id="cffa5-140">Dirección SIP del usuario que participó en la conferencia.</span><span class="sxs-lookup"><span data-stu-id="cffa5-140">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="cffa5-141">**Rol**</span><span class="sxs-lookup"><span data-stu-id="cffa5-141">**Role**</span></span> <br/> |<span data-ttu-id="cffa5-142">Rol (por ejemplo, Moderador) que ocupó el participante de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="cffa5-142">Role (for example, Presenter) played by the conference participant.</span></span>  <br/> |
|<span data-ttu-id="cffa5-143">**Conectividad**</span><span class="sxs-lookup"><span data-stu-id="cffa5-143">**Connectivity**</span></span> <br/> |<span data-ttu-id="cffa5-144">Conectividad de red (normalmente Desde conexión interna o Desde conexión externa) del participante.</span><span class="sxs-lookup"><span data-stu-id="cffa5-144">Network connectivity (typically From Internal or From External) for the participant.</span></span>  <br/> |
|<span data-ttu-id="cffa5-145">**Hora de conexión**</span><span class="sxs-lookup"><span data-stu-id="cffa5-145">**Join time**</span></span> <br/> |<span data-ttu-id="cffa5-146">Fecha y hora en que el participante se unió a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="cffa5-146">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="cffa5-147">**Hora de desconexión**</span><span class="sxs-lookup"><span data-stu-id="cffa5-147">**Leave time**</span></span> <br/> |<span data-ttu-id="cffa5-148">Fecha y hora en que el participante abandonó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="cffa5-148">Date and time that the participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="cffa5-149">**Agente de usuario**</span><span class="sxs-lookup"><span data-stu-id="cffa5-149">**User agent**</span></span> <br/> |<span data-ttu-id="cffa5-150">Identificador del software usado por el punto final del participante.</span><span class="sxs-lookup"><span data-stu-id="cffa5-150">Identifier for the software used by the participant's endpoint.</span></span>  <br/> |
|<span data-ttu-id="cffa5-151">**Informes de diagnósticos**</span><span class="sxs-lookup"><span data-stu-id="cffa5-151">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="cffa5-p104">Proporciona información de diagnóstico y resolución de problemas. Por ejemplo, códigos de respuesta SIP, encabezados de diagnóstico, horarios de conexión a conferencias e identificadores de diagnóstico para sesiones fallidas.</span><span class="sxs-lookup"><span data-stu-id="cffa5-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |

<span data-ttu-id="cffa5-154">En la tabla siguiente se enumera la información proporcionada en la sección modalidades de conferencia del informe detalles de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="cffa5-154">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

<span data-ttu-id="cffa5-155">**Métricas de Modalidades de conferencia**</span><span class="sxs-lookup"><span data-stu-id="cffa5-155">**Conference Modalities Metrics**</span></span>

|<span data-ttu-id="cffa5-156">**Nombre.**</span><span class="sxs-lookup"><span data-stu-id="cffa5-156">**Name**</span></span>|<span data-ttu-id="cffa5-157">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="cffa5-157">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cffa5-158">**Usuario**</span><span class="sxs-lookup"><span data-stu-id="cffa5-158">**User**</span></span> <br/> |<span data-ttu-id="cffa5-159">Dirección SIP del usuario que participó en la conferencia.</span><span class="sxs-lookup"><span data-stu-id="cffa5-159">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="cffa5-160">**Hora de conexión**</span><span class="sxs-lookup"><span data-stu-id="cffa5-160">**Join time**</span></span> <br/> |<span data-ttu-id="cffa5-161">Fecha y hora en que el participante se unió a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="cffa5-161">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="cffa5-162">**Hora de desconexión**</span><span class="sxs-lookup"><span data-stu-id="cffa5-162">**Leave time**</span></span> <br/> |<span data-ttu-id="cffa5-163">Fecha y hora en que un participante abandonó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="cffa5-163">Date and time that a participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="cffa5-164">**URI del servidor de conferencia**</span><span class="sxs-lookup"><span data-stu-id="cffa5-164">**Conferencing server URI**</span></span> <br/> |<span data-ttu-id="cffa5-165">URI para el servidor de conferencia utilizado en la conferencia.</span><span class="sxs-lookup"><span data-stu-id="cffa5-165">URI for the Conferencing server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="cffa5-166">**Informes de diagnósticos**</span><span class="sxs-lookup"><span data-stu-id="cffa5-166">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="cffa5-p105">Proporciona información de diagnóstico y resolución de problemas. Por ejemplo, códigos de respuesta SIP, encabezados de diagnóstico, horarios de conexión a conferencias e identificadores de diagnóstico para sesiones fallidas.</span><span class="sxs-lookup"><span data-stu-id="cffa5-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |


