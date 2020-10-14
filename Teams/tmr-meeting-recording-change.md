---
title: Usar OneDrive y SharePoint para grabaciones de reuniones
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo cambiar de flujo a OneDrive para la empresa y el almacenamiento de grabaciones de reuniones de SharePoint en Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83a7a0628d76a96318081ec51a039d458ea1570f
ms.sourcegitcommit: c48a5aca37220ac6a797ac88b09cf80090b1b7df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "48444236"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a><span data-ttu-id="add89-103">Usar OneDrive para la empresa y SharePoint o Stream para grabaciones de reuniones</span><span class="sxs-lookup"><span data-stu-id="add89-103">Use OneDrive for Business and SharePoint or Stream for meeting recordings</span></span>

> [!Note]
> <span data-ttu-id="add89-104">El cambio de usar Microsoft Stream a OneDrive para la empresa y a Microsoft SharePoint para las grabaciones de la reunión será un enfoque por fases.</span><span class="sxs-lookup"><span data-stu-id="add89-104">The change from using Microsoft Stream to OneDrive for Business and Microsoft SharePoint for meeting recordings will be a phased approach.</span></span>

|||
|---|-----------------|
|<span data-ttu-id="add89-105">Fecha</span><span class="sxs-lookup"><span data-stu-id="add89-105">Date</span></span>|<span data-ttu-id="add89-106">Produce</span><span class="sxs-lookup"><span data-stu-id="add89-106">Event</span></span>|
|<span data-ttu-id="add89-107">Principios del cuarto trimestre de CY20</span><span class="sxs-lookup"><span data-stu-id="add89-107">Early Q4 CY20</span></span>|<span data-ttu-id="add89-108">**Los equipos que se registran en OneDrive para la empresa y SharePoint están disponibles para participar o para anular la suscripción.**</span><span class="sxs-lookup"><span data-stu-id="add89-108">**Teams meeting recording on OneDrive for Business and SharePoint available for opt in or opt out.**</span></span><br> <span data-ttu-id="add89-109">Los administradores de inquilinos pueden optar por OneDrive para la empresa o no participar en la configuración de la Directiva de Teams de PowerShell</span><span class="sxs-lookup"><span data-stu-id="add89-109">Tenant admins can opt in  or opt out of OneDrive for Business and SharePoint setting the Teams policy in PowerShell</span></span>|
|<span data-ttu-id="add89-110">CY20 Trim Trim</span><span class="sxs-lookup"><span data-stu-id="add89-110">Mid Q4 CY20</span></span>|<span data-ttu-id="add89-111">**Los equipos graban el registro de OneDrive para la empresa y SharePoint como predeterminado para los inquilinos que no se desactivan**</span><span class="sxs-lookup"><span data-stu-id="add89-111">**Teams meeting recording on OneDrive for Business and SharePoint set as default for tenants who don't opt out**</span></span><br> <span data-ttu-id="add89-112">Esta es la ruta recomendada para la mayoría de los clientes</span><span class="sxs-lookup"><span data-stu-id="add89-112">This is the  recommended path for most customers</span></span>|
<span data-ttu-id="add89-113">T1 CY21</span><span class="sxs-lookup"><span data-stu-id="add89-113">Q1 CY21</span></span>|<span data-ttu-id="add89-114">**Guardar equipos ya no se permite la grabación de reuniones en una secuencia clásica**</span><span class="sxs-lookup"><span data-stu-id="add89-114">**Saving Teams meeting recording to Classic Stream no longer allowed**</span></span><br><span data-ttu-id="add89-115">Todos los inquilinos guardarán los equipos de la grabación de reuniones en OneDrive para la empresa y SharePoint</span><span class="sxs-lookup"><span data-stu-id="add89-115">All tenants will save Teams meeting recording to OneDrive for Business and SharePoint</span></span>|
|||

<span data-ttu-id="add89-116">Microsoft Teams tiene un nuevo método para guardar las grabaciones de la reunión.</span><span class="sxs-lookup"><span data-stu-id="add89-116">Microsoft Teams has a new method for saving meeting recordings.</span></span> <span data-ttu-id="add89-117">Como primera fase de una transición de la secuencia clásica de Microsoft a la [nueva secuencia](https://docs.microsoft.com/stream/streamnew/new-stream), este método almacena las grabaciones en Microsoft OneDrive y SharePoint en Microsoft 365 y ofrece muchas ventajas.</span><span class="sxs-lookup"><span data-stu-id="add89-117">As the first phase of a transition from classic Microsoft Stream to the [new Stream](https://docs.microsoft.com/stream/streamnew/new-stream), this method stores recordings on Microsoft OneDrive and SharePoint in Microsoft 365 and offers many benefits.</span></span>

<span data-ttu-id="add89-118">Entre las ventajas de usar OneDrive para la empresa y SharePoint para almacenar grabaciones, se incluyen:</span><span class="sxs-lookup"><span data-stu-id="add89-118">The benefits of using OneDrive for Business and SharePoint for storing recordings include:</span></span>

- <span data-ttu-id="add89-119">Directivas de retención para la grabación de reuniones de Teams (TMR) (etiquetas de autoretención S + C E5)</span><span class="sxs-lookup"><span data-stu-id="add89-119">Retention policies for Teams meeting recording (TMR) (S+C E5 autoretention labels)</span></span>
- <span data-ttu-id="add89-120">Beneficios de OneDrive para la empresa y SharePoint Information Governance</span><span class="sxs-lookup"><span data-stu-id="add89-120">Benefit from OneDrive for Business and SharePoint information governance</span></span>
- <span data-ttu-id="add89-121">Fácil de establecer permisos y compartir</span><span class="sxs-lookup"><span data-stu-id="add89-121">Easy to set permissions and sharing</span></span>
- <span data-ttu-id="add89-122">Compartir grabaciones con invitados (usuarios externos) solo con recursos compartidos explícitos</span><span class="sxs-lookup"><span data-stu-id="add89-122">Share recordings with guests (external users) with explicit share only</span></span>
- <span data-ttu-id="add89-123">Solicitar el flujo de acceso</span><span class="sxs-lookup"><span data-stu-id="add89-123">Request access flow</span></span>
- <span data-ttu-id="add89-124">Proporcionar vínculos compartidos de OneDrive para la empresa y SharePoint</span><span class="sxs-lookup"><span data-stu-id="add89-124">Provide OneDrive for Business and SharePoint shared links</span></span>
- <span data-ttu-id="add89-125">Mayor cuota</span><span class="sxs-lookup"><span data-stu-id="add89-125">Increased quota</span></span>
- <span data-ttu-id="add89-126">Las grabaciones de reunión están disponibles más rápido</span><span class="sxs-lookup"><span data-stu-id="add89-126">Meeting  recordings are available faster</span></span>
- <span data-ttu-id="add89-127">**Ir** a soporte técnico de inquilino local</span><span class="sxs-lookup"><span data-stu-id="add89-127">**Go local** tenant support</span></span>
- <span data-ttu-id="add89-128">Compatibilidad con múltiples geografías: las grabaciones se almacenan en una región específica para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="add89-128">Multi-geo support – recordings are stored in a region specific to that user</span></span>
- <span data-ttu-id="add89-129">Ofrece tu propia clave (BYOK)</span><span class="sxs-lookup"><span data-stu-id="add89-129">Bring your own key (BYOK) support</span></span>
- <span data-ttu-id="add89-130">Mejora de la calidad de la transcripción y atribución del altavoz</span><span class="sxs-lookup"><span data-stu-id="add89-130">Improved Transcript quality and speaker attribution</span></span>

<span data-ttu-id="add89-131">Hay algunas limitaciones que debe tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="add89-131">There are some limitations to consider:</span></span>

- <span data-ttu-id="add89-132">Habrá subtítulos y transcripciones solo en inglés.</span><span class="sxs-lookup"><span data-stu-id="add89-132">There will be English-only closed captions and transcripts.</span></span>
- <span data-ttu-id="add89-133">No podrás buscar transcripciones ni su contenido.</span><span class="sxs-lookup"><span data-stu-id="add89-133">You won't be able to search transcripts or their content.</span></span>
- <span data-ttu-id="add89-134">No podrá modificar las transcripciones, pero podrá activar o desactivar las leyendas....</span><span class="sxs-lookup"><span data-stu-id="add89-134">You won’t be able to edit the transcripts, but you'll be able to toggle captions off/on.</span></span>
- <span data-ttu-id="add89-135">Puede controlar con quién comparte la grabación, pero no podrá bloquear a los usuarios con acceso compartido para que no descarguen la grabación.</span><span class="sxs-lookup"><span data-stu-id="add89-135">You can control with whom you share the recording, but you won't be able to block people with shared access from downloading the recording.</span></span>
- <span data-ttu-id="add89-136">No recibirá un correo electrónico cuando la grabación termine de guardar, pero la grabación aparecerá en la conversación de la reunión una vez que haya finalizado.</span><span class="sxs-lookup"><span data-stu-id="add89-136">You'll not get an email when the recording finishes saving, but the recording will appear in the meeting chat once it’s finished.</span></span> <span data-ttu-id="add89-137">Esto se hará mucho más rápido de lo que hacía en la secuencia anteriormente</span><span class="sxs-lookup"><span data-stu-id="add89-137">This will happen much quicker than it did in Stream previously</span></span>

<span data-ttu-id="add89-138">Vea "grabación de reuniones" para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="add89-138">Watch "Meeting Recording" for more information.</span></span>

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a><span data-ttu-id="add89-139">Configurar la opción de grabación de la reunión para OneDrive para la empresa y SharePoint</span><span class="sxs-lookup"><span data-stu-id="add89-139">Set up the meeting recording option for OneDrive for Business and SharePoint</span></span>

1. <span data-ttu-id="add89-140">Instale la consola de administración de PowerShell de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="add89-140">Install the Skype For Business Online PowerShell admin console.</span></span>

    <span data-ttu-id="add89-141">a.</span><span class="sxs-lookup"><span data-stu-id="add89-141">a.</span></span> <span data-ttu-id="add89-142">Descargue [Skype empresarial online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="add89-142">Download [Skype for Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span></span>

    <span data-ttu-id="add89-143">b.</span><span class="sxs-lookup"><span data-stu-id="add89-143">b.</span></span> <span data-ttu-id="add89-144">Siga las indicaciones para instalarlo.</span><span class="sxs-lookup"><span data-stu-id="add89-144">Follow the prompts to install it.</span></span>

    <span data-ttu-id="add89-145">c.</span><span class="sxs-lookup"><span data-stu-id="add89-145">c.</span></span> <span data-ttu-id="add89-146">Reinicie el equipo.</span><span class="sxs-lookup"><span data-stu-id="add89-146">Restart your machine.</span></span>

2. <span data-ttu-id="add89-147">Iniciar PowerShell como administrador</span><span class="sxs-lookup"><span data-stu-id="add89-147">Launch PowerShell as an admin</span></span>

3. <span data-ttu-id="add89-148">Importe el conector SkypeOnline e inicie sesión como administrador de equipos.</span><span class="sxs-lookup"><span data-stu-id="add89-148">Import the SkypeOnline Connector and log in as a Teams admin.</span></span>

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. <span data-ttu-id="add89-149">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) para configurar una directiva de reunión de Teams para que pase de la secuencia de almacenamiento a la de ODSP.</span><span class="sxs-lookup"><span data-stu-id="add89-149">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) to set a Teams Meeting Policy to transition from the Stream storage to ODSP.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a><span data-ttu-id="add89-150">No se puede elegir OneDrive para la empresa y SharePoint para seguir usando Stream</span><span class="sxs-lookup"><span data-stu-id="add89-150">Opt out of OneDrive for Business and SharePoint to continue using Stream</span></span>

<span data-ttu-id="add89-151">Incluso si una directiva dice que está configurada para **transmitirse**, es posible que no esté configurada.</span><span class="sxs-lookup"><span data-stu-id="add89-151">Even if a policy says it's set to **Stream**, it might not be set.</span></span> <span data-ttu-id="add89-152">Normalmente, si no se establece la Directiva, la configuración predeterminada es **transmitir**.</span><span class="sxs-lookup"><span data-stu-id="add89-152">Typically, if the policy isn't set, then the default setting is **Stream**.</span></span> <span data-ttu-id="add89-153">Sin embargo, con este nuevo cambio, si desea optar por no usar SharePoint o OneDrive, debe restablecer la Directiva en **Stream** para asegurarse de que es la opción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="add89-153">However, with this new change, if you want to opt-out of using SharePoint or OneDrive, then you must reset the policy to **Stream** to ensure that it's the default.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a><span data-ttu-id="add89-154">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="add89-154">Frequently asked questions</span></span>

<span data-ttu-id="add89-155">**¿Dónde se almacenará la grabación de la reunión?**</span><span class="sxs-lookup"><span data-stu-id="add89-155">**Where will the meeting recording be stored?**</span></span>

- <span data-ttu-id="add89-156">Para las reuniones que no son de canal, la grabación se almacena en una carpeta denominada **grabaciones** que se encuentra en el nivel superior de OneDrive que pertenece a la persona que inició la grabación de la reunión.</span><span class="sxs-lookup"><span data-stu-id="add89-156">For non-Channel meetings, the recording is stored in a folder named **Recordings** that is at the top level of the OneDrive that belongs to the person who started the meeting recording.</span></span> <span data-ttu-id="add89-157">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="add89-157">Example:</span></span>

  <span data-ttu-id="add89-158"><i>OneDrive para la empresa</i> / de la grabadora **Grabaciones**</span><span class="sxs-lookup"><span data-stu-id="add89-158"><i>recorder's OneDrive for Business</i>/**Recordings**</span></span>

- <span data-ttu-id="add89-159">Para las reuniones de canal, la grabación se almacena en la biblioteca de documentación del sitio de Teams en una carpeta denominada **grabaciones**.</span><span class="sxs-lookup"><span data-stu-id="add89-159">For Channel meetings, the recording is stored in the Teams site documentation library in a folder named **Recordings**.</span></span> <span data-ttu-id="add89-160">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="add89-160">Example:</span></span>

  <span data-ttu-id="add89-161"><i>Equipos nombre: nombre</i> / del canal **Documentos** / **Grabaciones**</span><span class="sxs-lookup"><span data-stu-id="add89-161"><i>Teams name - Channel name</i>/**Documents**/**Recordings**</span></span>

<span data-ttu-id="add89-162">**¿Cómo puedo controlar las grabaciones de antiguos empleados?**</span><span class="sxs-lookup"><span data-stu-id="add89-162">**How do I handle recordings from former employees?**</span></span>

<span data-ttu-id="add89-163">Puesto que los vídeos son como cualquier otro archivo de OneDrive y SharePoint, la administración de la propiedad y la retención después de que un empleado salga el proceso normal de [onedrive y SharePoint]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process).</span><span class="sxs-lookup"><span data-stu-id="add89-163">Since videos are just like any other file in OneDrive and SharePoint, handling ownership and retention after an employee leaves will follow the normal [OneDrive and SharePoint process]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process).</span></span>

<span data-ttu-id="add89-164">**¿Quién tiene permisos para ver la grabación de la reunión?**</span><span class="sxs-lookup"><span data-stu-id="add89-164">**Who has the permissions to view the meeting recording?**</span></span>

- <span data-ttu-id="add89-165">Para las reuniones que no son de canal, todas las invitaciones a reuniones, excepto los usuarios externos, obtendrán automáticamente un vínculo compartido personalmente.</span><span class="sxs-lookup"><span data-stu-id="add89-165">For non-Channel meetings, all meeting invitees, except for external users, will automatically get a personally shared link.</span></span> <span data-ttu-id="add89-166">Los usuarios externos tendrán que agregarlos explícitamente a la lista compartida por el organizador de la reunión o la persona que inició la grabación de la reunión.</span><span class="sxs-lookup"><span data-stu-id="add89-166">External users will need to be explicitly added to the shared list by the meeting organizer or the person who started the meeting recording.</span></span>

- <span data-ttu-id="add89-167">Para las reuniones de canal, los permisos se heredan de la lista de propietarios y miembros en el canal.</span><span class="sxs-lookup"><span data-stu-id="add89-167">For Channel meetings, permissions are inherited from the owners and members list in the channel.</span></span>

<span data-ttu-id="add89-168">**¿Cómo puedo administrar transcripciones?**</span><span class="sxs-lookup"><span data-stu-id="add89-168">**How can I manage transcripts?**</span></span>

<span data-ttu-id="add89-169">Los clientes que opten por esta versión preliminar no tendrán subtítulos disponibles en las grabaciones de reuniones de sus equipos que se migren a OneDrive y SharePoint.</span><span class="sxs-lookup"><span data-stu-id="add89-169">Customers opting in to this preview will not have closed captions available on their Teams Meeting Recordings that are migrated to OneDrive and SharePoint.</span></span><span data-ttu-id="add89-170">Estamos trabajando para agregar subtítulos, empezando con los subtítulos en inglés, para hacer una reunión de las grabaciones en octubre de 2020.</span><span class="sxs-lookup"><span data-stu-id="add89-170">  We're working to add captioning, beginning with closed captions in English, to meeting recordings in October 2020.</span></span>

<span data-ttu-id="add89-171">Los subtítulos cerrados estarán disponibles en las grabaciones de reuniones de Teams para los clientes que hayan optado por permitir transcripciones según se describe en las [grabaciones en la nube de Teams](cloud-recording.md) .</span><span class="sxs-lookup"><span data-stu-id="add89-171">Closed captions will be available on Teams Meeting Recordings for customers who have opted in to allow transcripts as described in [Teams cloud recordings](cloud-recording.md)</span></span>

<span data-ttu-id="add89-172">Los subtítulos ayudan a crear contenido inclusivo para los visores de todas las capacidades.</span><span class="sxs-lookup"><span data-stu-id="add89-172">Captions help create inclusive content for viewers of all abilities.</span></span> <span data-ttu-id="add89-173">Como propietario, puede ocultar los subtítulos, aunque la transcripción seguirá estando disponible en Teams, a menos que elimine los subtítulos de Teams.</span><span class="sxs-lookup"><span data-stu-id="add89-173">As an owner, you can hide captions, although the transcript will still be available on Teams unless you delete the captions from Teams.</span></span> <span data-ttu-id="add89-174">Ver [Cómo activar o desactivar las grabaciones de reuniones](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="add89-174">See [how to turn on or off meeting recordings](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span></span>

<span data-ttu-id="add89-175">Los subtítulos se admiten para las grabaciones de reuniones de equipos por 60 días desde que se grabó la reunión.</span><span class="sxs-lookup"><span data-stu-id="add89-175">Closed captions are supported for Teams meeting recordings for 60 days from when the meeting is recorded.</span></span>

<span data-ttu-id="add89-176">**¿Cómo se verá afectada mi cuota de almacenamiento**</span><span class="sxs-lookup"><span data-stu-id="add89-176">**How will my storage quota be impacted**</span></span>

<span data-ttu-id="add89-177">Los equipos que reunión graban archivos en OneDrive para la empresa y SharePoint se incluyen en su cuota para esos servicios.</span><span class="sxs-lookup"><span data-stu-id="add89-177">Teams meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services.</span></span> <span data-ttu-id="add89-178">Consulte [cuota de SharePoint](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) y [cuota de OneDrive para la empresa] ( https://docs.microsoft.com/onedrive/set-default-storage-space) .</span><span class="sxs-lookup"><span data-stu-id="add89-178">See [SharePoint quota](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) and [OneDrive for Business quota] (https://docs.microsoft.com/onedrive/set-default-storage-space).</span></span>

<span data-ttu-id="add89-179">**¿Cómo puedo reproducir una grabación de reuniones de Teams?**</span><span class="sxs-lookup"><span data-stu-id="add89-179">**How can I play a Teams meeting recording?**</span></span>

<span data-ttu-id="add89-180">El vídeo se reproducirá en el reproductor de vídeo de OneDrive para la empresa o SharePoint según dónde se obtenga acceso al archivo.</span><span class="sxs-lookup"><span data-stu-id="add89-180">Your video will play on the video player of OneDrive for Business or SharePoint depending on where you access the file.</span></span>

<span data-ttu-id="add89-181">**Si tiene previsto agregar a la transmisión, ¿los vídeos existentes se mantendrán como están y durante cuánto tiempo?**</span><span class="sxs-lookup"><span data-stu-id="add89-181">**If you plan on deprecating adding to Stream, will existing videos stay as is and for how long?**</span></span>

<span data-ttu-id="add89-182">La secuencia como plataforma no quedará obsoleta en un futuro próximo.</span><span class="sxs-lookup"><span data-stu-id="add89-182">Stream as a platform won't be deprecated in the near future.</span></span> <span data-ttu-id="add89-183">Los vídeos que actualmente viven en la secuencia permanecerán allí hasta que empiece la migración.</span><span class="sxs-lookup"><span data-stu-id="add89-183">The videos that currently live in Stream will stay there until we start migrating.</span></span> <span data-ttu-id="add89-184">Después de la migración, esos vídeos también se migrarán a ODSP.</span><span class="sxs-lookup"><span data-stu-id="add89-184">Upon migration, those videos will be migrated to ODSP as well.</span></span> <span data-ttu-id="add89-185">Para obtener más información, consulta [aquí](https://docs.microsoft.com/stream/streamnew/classic-migration) .</span><span class="sxs-lookup"><span data-stu-id="add89-185">Check [here](https://docs.microsoft.com/stream/streamnew/classic-migration) for more information.</span></span>
