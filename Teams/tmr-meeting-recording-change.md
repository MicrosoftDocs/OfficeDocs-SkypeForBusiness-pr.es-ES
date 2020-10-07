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
ms.openlocfilehash: e8616bae083f8ec043c1092e4d391866a8b957d6
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369176"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a><span data-ttu-id="a98b3-103">Usar OneDrive para la empresa y SharePoint o Stream para grabaciones de reuniones</span><span class="sxs-lookup"><span data-stu-id="a98b3-103">Use OneDrive for Business and SharePoint or Stream for meeting recordings</span></span>

> [!Note]
> <span data-ttu-id="a98b3-104">El cambio del uso de Microsoft Stream a OneDrive para la Empresa y SharePoint para grabaciones de reuniones estará basado en fases.</span><span class="sxs-lookup"><span data-stu-id="a98b3-104">The change from using Microsoft Stream to OneDrive for Business and SharePoint for meeting recordings will be a phased approach.</span></span> <span data-ttu-id="a98b3-105">En el inicio, los administradores de inquilinos pueden elegir esta nueva opción de flujo de trabajo hoy y empezar a ver la carga automática de grabaciones para OneDrive para la empresa y SharePoint en el 2020 de octubre.</span><span class="sxs-lookup"><span data-stu-id="a98b3-105">At launch, tenant admins can choose this new workflow option today and will start seeing recordings auto-upload to OneDrive for Business and SharePoint in October 2020.</span></span> <span data-ttu-id="a98b3-106">En noviembre, tendrá que optar por no poder seguir usando Stream, y durante principios de 2021 requerimos que todos los clientes usen OneDrive para la empresa y SharePoint para nuevas grabaciones de reunión.</span><span class="sxs-lookup"><span data-stu-id="a98b3-106">In November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

<span data-ttu-id="a98b3-107">Microsoft Teams tiene un nuevo método para guardar las grabaciones de la reunión.</span><span class="sxs-lookup"><span data-stu-id="a98b3-107">Microsoft Teams has a new method for saving meeting recordings.</span></span> <span data-ttu-id="a98b3-108">Como salida de Stream, el método usa Microsoft OneDrive y SharePoint en Microsoft 365 y ofrece muchas ventajas.</span><span class="sxs-lookup"><span data-stu-id="a98b3-108">As a departure from Stream, the method uses Microsoft OneDrive and SharePoint in Microsoft 365 and offers many benefits.</span></span>

<span data-ttu-id="a98b3-109">Entre las ventajas de usar OneDrive para la empresa y SharePoint para almacenar grabaciones, se incluyen:</span><span class="sxs-lookup"><span data-stu-id="a98b3-109">The benefits of using OneDrive for Business and SharePoint for storing recordings include:</span></span>

- <span data-ttu-id="a98b3-110">Directivas de retención para la grabación de reuniones de Teams (TMR) (etiquetas de autoretención S + C E5)</span><span class="sxs-lookup"><span data-stu-id="a98b3-110">Retention policies for Teams meeting recording (TMR) (S+C E5 autoretention labels)</span></span>
- <span data-ttu-id="a98b3-111">Beneficios de OneDrive para la empresa y SharePoint Information Governance</span><span class="sxs-lookup"><span data-stu-id="a98b3-111">Benefit from OneDrive for Business and SharePoint information governance</span></span>
- <span data-ttu-id="a98b3-112">Fácil de establecer permisos y compartir</span><span class="sxs-lookup"><span data-stu-id="a98b3-112">Easy to set permissions and sharing</span></span>
- <span data-ttu-id="a98b3-113">Compartir grabaciones con invitados (usuarios externos) solo con recursos compartidos explícitos</span><span class="sxs-lookup"><span data-stu-id="a98b3-113">Share recordings with guests (external users) with explicit share only</span></span>
- <span data-ttu-id="a98b3-114">Solicitar el flujo de acceso</span><span class="sxs-lookup"><span data-stu-id="a98b3-114">Request access flow</span></span>
- <span data-ttu-id="a98b3-115">Proporcionar vínculos compartidos de OneDrive para la empresa y SharePoint</span><span class="sxs-lookup"><span data-stu-id="a98b3-115">Provide OneDrive for Business and SharePoint shared links</span></span>
- <span data-ttu-id="a98b3-116">Mayor cuota</span><span class="sxs-lookup"><span data-stu-id="a98b3-116">Increased quota</span></span>
- <span data-ttu-id="a98b3-117">Las grabaciones de reunión están disponibles más rápido</span><span class="sxs-lookup"><span data-stu-id="a98b3-117">Meeting  recordings are available faster</span></span>
- <span data-ttu-id="a98b3-118">**Ir** a soporte técnico de inquilino local</span><span class="sxs-lookup"><span data-stu-id="a98b3-118">**Go local** tenant support</span></span>
- <span data-ttu-id="a98b3-119">Compatibilidad con múltiples geografías: las grabaciones se almacenan en una región específica para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="a98b3-119">Multi-geo support – recordings are stored in a region specific to that user</span></span>
- <span data-ttu-id="a98b3-120">Ofrece tu propia clave (BYOK)</span><span class="sxs-lookup"><span data-stu-id="a98b3-120">Bring your own key (BYOK) support</span></span>
- <span data-ttu-id="a98b3-121">Mejora de la calidad de la transcripción y atribución del altavoz</span><span class="sxs-lookup"><span data-stu-id="a98b3-121">Improved Transcript quality and speaker attribution</span></span>

<span data-ttu-id="a98b3-122">Hay algunas limitaciones que debe tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="a98b3-122">There are some limitations to consider:</span></span>

- <span data-ttu-id="a98b3-123">Habrá subtítulos y transcripciones solo en inglés.</span><span class="sxs-lookup"><span data-stu-id="a98b3-123">There will be English-only closed captions and transcripts.</span></span>
- <span data-ttu-id="a98b3-124">No podrás buscar transcripciones ni su contenido.</span><span class="sxs-lookup"><span data-stu-id="a98b3-124">You won't be able to search transcripts or their content.</span></span>
- <span data-ttu-id="a98b3-125">No podrá modificar las transcripciones, pero podrá activar o desactivar las leyendas....</span><span class="sxs-lookup"><span data-stu-id="a98b3-125">You won’t be able to edit the transcripts, but you'll be able to toggle captions off/on.</span></span>
- <span data-ttu-id="a98b3-126">Puede controlar con quién comparte la grabación, pero no podrá bloquear a los usuarios con acceso compartido para que no descarguen la grabación.</span><span class="sxs-lookup"><span data-stu-id="a98b3-126">You can control with whom you share the recording, but you won't be able to block people with shared access from downloading the recording.</span></span>
- <span data-ttu-id="a98b3-127">No recibirá un correo electrónico cuando la grabación termine de guardar, pero la grabación aparecerá en la conversación de la reunión una vez que haya finalizado.</span><span class="sxs-lookup"><span data-stu-id="a98b3-127">You'll not get an email when the recording finishes saving, but the recording will appear in the meeting chat once it’s finished.</span></span> <span data-ttu-id="a98b3-128">Esto se hará mucho más rápido de lo que hacía en la secuencia anteriormente</span><span class="sxs-lookup"><span data-stu-id="a98b3-128">This will happen much quicker than it did in Stream previously</span></span>

<span data-ttu-id="a98b3-129">Vea "grabación de reuniones" para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a98b3-129">Watch "Meeting Recording" for more information.</span></span>

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a><span data-ttu-id="a98b3-130">Configurar la opción de grabación de la reunión para OneDrive para la empresa y SharePoint</span><span class="sxs-lookup"><span data-stu-id="a98b3-130">Set up the meeting recording option for OneDrive for Business and SharePoint</span></span>

1. <span data-ttu-id="a98b3-131">Instale la consola de administración de PowerShell de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="a98b3-131">Install the Skype For Business Online PowerShell admin console.</span></span>

    <span data-ttu-id="a98b3-132">a.</span><span class="sxs-lookup"><span data-stu-id="a98b3-132">a.</span></span> <span data-ttu-id="a98b3-133">Descargue [Skype empresarial online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="a98b3-133">Download [Skype for Business Online Powershell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span></span>

    <span data-ttu-id="a98b3-134">b.</span><span class="sxs-lookup"><span data-stu-id="a98b3-134">b.</span></span> <span data-ttu-id="a98b3-135">Siga las indicaciones para instalarlo.</span><span class="sxs-lookup"><span data-stu-id="a98b3-135">Follow the prompts to install it.</span></span>

    <span data-ttu-id="a98b3-136">c.</span><span class="sxs-lookup"><span data-stu-id="a98b3-136">c.</span></span> <span data-ttu-id="a98b3-137">Reinicie el equipo.</span><span class="sxs-lookup"><span data-stu-id="a98b3-137">Restart your machine.</span></span>

2. <span data-ttu-id="a98b3-138">Iniciar PowerShell como administrador</span><span class="sxs-lookup"><span data-stu-id="a98b3-138">Launch PowerShell as an admin</span></span>

3. <span data-ttu-id="a98b3-139">Importe el conector SkypeOnline e inicie sesión como administrador de equipos.</span><span class="sxs-lookup"><span data-stu-id="a98b3-139">Import the SkypeOnline Connector and log in as a Teams admin.</span></span>

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. <span data-ttu-id="a98b3-140">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) para configurar una directiva de reunión de Teams para que pase de la secuencia de almacenamiento a la de ODSP.</span><span class="sxs-lookup"><span data-stu-id="a98b3-140">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) to set a Teams Meeting Policy to transition from the Stream storage to ODSP.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a><span data-ttu-id="a98b3-141">No se puede elegir OneDrive para la empresa y SharePoint para seguir usando Stream</span><span class="sxs-lookup"><span data-stu-id="a98b3-141">Opt out of OneDrive for Business and SharePoint to continue using Stream</span></span>

<span data-ttu-id="a98b3-142">Incluso si una directiva dice que está configurada para **transmitirse**, es posible que no esté configurada.</span><span class="sxs-lookup"><span data-stu-id="a98b3-142">Even if a policy says it's set to **Stream**, it might not be set.</span></span> <span data-ttu-id="a98b3-143">Normalmente, si no se establece la Directiva, la configuración predeterminada es **transmitir**.</span><span class="sxs-lookup"><span data-stu-id="a98b3-143">Typically, if the policy isn't set, then the default setting is **Stream**.</span></span> <span data-ttu-id="a98b3-144">Sin embargo, con este nuevo cambio, si desea optar por no usar SharePoint o OneDrive, debe restablecer la Directiva en **Stream** para asegurarse de que es la opción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a98b3-144">However, with this new change, if you want to opt-out of using SharePoint or OneDrive, then you must reset the policy to **Stream** to ensure that it's the default.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a><span data-ttu-id="a98b3-145">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="a98b3-145">Frequently asked questions</span></span>

<span data-ttu-id="a98b3-146">**¿Dónde se almacenará la grabación de la reunión?**</span><span class="sxs-lookup"><span data-stu-id="a98b3-146">**Where will the meeting recording be stored?**</span></span>

- <span data-ttu-id="a98b3-147">Para las reuniones que no son de canal, la grabación se almacena en una carpeta denominada **grabaciones** que se encuentra en el nivel superior de OneDrive que pertenece a la persona que inició la grabación de la reunión.</span><span class="sxs-lookup"><span data-stu-id="a98b3-147">For non-Channel meetings, the recording is stored in a folder named **Recordings** that is at the top level of the OneDrive that belongs to the person who started the meeting recording.</span></span> <span data-ttu-id="a98b3-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a98b3-148">Example:</span></span>

  <span data-ttu-id="a98b3-149"><i>OneDrive para la empresa</i> / de la grabadora **Grabaciones**</span><span class="sxs-lookup"><span data-stu-id="a98b3-149"><i>recorder's OneDrive for Business</i>/**Recordings**</span></span>

- <span data-ttu-id="a98b3-150">Para las reuniones de canal, la grabación se almacena en la biblioteca de documentación del sitio de Teams en una carpeta denominada **grabaciones**.</span><span class="sxs-lookup"><span data-stu-id="a98b3-150">For Channel meetings, the recording is stored in the Teams site documentation library in a folder named **Recordings**.</span></span> <span data-ttu-id="a98b3-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a98b3-151">Example:</span></span>

  <span data-ttu-id="a98b3-152"><i>Equipos nombre: nombre</i> / del canal **Documentos** / **Grabaciones**</span><span class="sxs-lookup"><span data-stu-id="a98b3-152"><i>Teams name - Channel name</i>/**Documents**/**Recordings**</span></span>

<span data-ttu-id="a98b3-153">**¿Quién tiene permisos para ver la grabación de la reunión?**</span><span class="sxs-lookup"><span data-stu-id="a98b3-153">**Who has the permissions to view the meeting recording?**</span></span>

- <span data-ttu-id="a98b3-154">Para las reuniones que no son de canal, todas las invitaciones a reuniones, excepto los usuarios externos, obtendrán automáticamente un vínculo compartido personalmente.</span><span class="sxs-lookup"><span data-stu-id="a98b3-154">For non-Channel meetings, all meeting invitees, except for external users, will automatically get a personally shared link.</span></span> <span data-ttu-id="a98b3-155">Los usuarios externos tendrán que agregarlos explícitamente a la lista compartida por el organizador de la reunión o la persona que inició la grabación de la reunión.</span><span class="sxs-lookup"><span data-stu-id="a98b3-155">External users will need to be explicitly added to the shared list by the meeting organizer or the person who started the meeting recording.</span></span>

- <span data-ttu-id="a98b3-156">Para las reuniones de canal, los permisos se heredan de la lista de propietarios y miembros en el canal.</span><span class="sxs-lookup"><span data-stu-id="a98b3-156">For Channel meetings, permissions are inherited from the owners and members list in the channel.</span></span>

<span data-ttu-id="a98b3-157">**¿Cómo puedo administrar transcripciones?**</span><span class="sxs-lookup"><span data-stu-id="a98b3-157">**How can I manage transcripts?**</span></span>

<span data-ttu-id="a98b3-158">Los clientes que opten por esta versión preliminar no tendrán subtítulos disponibles en las grabaciones de reuniones de sus equipos que se migren a OneDrive y SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a98b3-158">Customers opting in to this preview will not have closed captions available on their Teams Meeting Recordings that are migrated to OneDrive and SharePoint.</span></span><span data-ttu-id="a98b3-159">Estamos trabajando para agregar subtítulos, empezando con los subtítulos en inglés, para hacer una reunión de las grabaciones en octubre de 2020.</span><span class="sxs-lookup"><span data-stu-id="a98b3-159">  We're working to add captioning, beginning with closed captions in English, to meeting recordings in October 2020.</span></span>

<span data-ttu-id="a98b3-160">Los subtítulos cerrados estarán disponibles en las grabaciones de reuniones de Teams para los clientes que hayan optado por permitir transcripciones según se describe en las [grabaciones en la nube de Teams](cloud-recording.md) .</span><span class="sxs-lookup"><span data-stu-id="a98b3-160">Closed captions will be available on Teams Meeting Recordings for customers who have opted in to allow transcripts as described in [Teams cloud recordings](cloud-recording.md)</span></span>

<span data-ttu-id="a98b3-161">Los subtítulos ayudan a crear contenido inclusivo para los visores de todas las capacidades.</span><span class="sxs-lookup"><span data-stu-id="a98b3-161">Captions help create inclusive content for viewers of all abilities.</span></span> <span data-ttu-id="a98b3-162">Como propietario, puede ocultar los subtítulos, aunque la transcripción seguirá estando disponible en Teams, a menos que elimine los subtítulos de Teams.</span><span class="sxs-lookup"><span data-stu-id="a98b3-162">As an owner, you can hide captions, although the transcript will still be available on Teams unless you delete the captions from Teams.</span></span> <span data-ttu-id="a98b3-163">Ver [Cómo activar o desactivar las grabaciones de reuniones](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="a98b3-163">See [how to turn on or off meeting recordings](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span></span>

<span data-ttu-id="a98b3-164">Los subtítulos se admiten para las grabaciones de reuniones de equipos por 60 días desde que se grabó la reunión.</span><span class="sxs-lookup"><span data-stu-id="a98b3-164">Closed captions are supported for Teams meeting recordings for 60 days from when the meeting is recorded.</span></span>

<span data-ttu-id="a98b3-165">**¿Cómo se verá afectada mi cuota de almacenamiento**</span><span class="sxs-lookup"><span data-stu-id="a98b3-165">**How will my storage quota be impacted**</span></span>

<span data-ttu-id="a98b3-166">Los equipos que reunión graban archivos en OneDrive para la empresa y SharePoint se incluyen en su cuota para esos servicios.</span><span class="sxs-lookup"><span data-stu-id="a98b3-166">Teams meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services.</span></span> <span data-ttu-id="a98b3-167">Consulte [cuota de SharePoint](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) y [cuota de OneDrive para la empresa] ( https://docs.microsoft.com/onedrive/set-default-storage-space) .</span><span class="sxs-lookup"><span data-stu-id="a98b3-167">See [SharePoint quota](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) and [OneDrive for Business quota] (https://docs.microsoft.com/onedrive/set-default-storage-space).</span></span>

<span data-ttu-id="a98b3-168">**¿Cómo puedo reproducir una grabación de reuniones de Teams?**</span><span class="sxs-lookup"><span data-stu-id="a98b3-168">**How can I play a Teams meeting recording?**</span></span>

<span data-ttu-id="a98b3-169">El vídeo se reproducirá en el reproductor de vídeo de OneDrive para la empresa o SharePoint según dónde se obtenga acceso al archivo.</span><span class="sxs-lookup"><span data-stu-id="a98b3-169">Your video will play on the video player of OneDrive for Business or SharePoint depending on where you access the file.</span></span>

<span data-ttu-id="a98b3-170">**Si tiene previsto agregar a la transmisión, ¿los vídeos existentes se mantendrán como están y durante cuánto tiempo?**</span><span class="sxs-lookup"><span data-stu-id="a98b3-170">**If you plan on deprecating adding to Stream, will existing videos stay as is and for how long?**</span></span>

<span data-ttu-id="a98b3-171">La secuencia como plataforma no quedará obsoleta en un futuro próximo.</span><span class="sxs-lookup"><span data-stu-id="a98b3-171">Stream as a platform won't be deprecated in the near future.</span></span> <span data-ttu-id="a98b3-172">Los vídeos que actualmente viven en la secuencia permanecerán allí hasta que empiece la migración.</span><span class="sxs-lookup"><span data-stu-id="a98b3-172">The videos that currently live in Stream will stay there until we start migrating.</span></span> <span data-ttu-id="a98b3-173">Después de la migración, esos vídeos también se migrarán a ODSP.</span><span class="sxs-lookup"><span data-stu-id="a98b3-173">Upon migration, those videos will be migrated to ODSP as well.</span></span> <span data-ttu-id="a98b3-174">Para obtener más información, consulta [aquí](https://docs.microsoft.com/stream/streamnew/classic-migration) .</span><span class="sxs-lookup"><span data-stu-id="a98b3-174">Check [here](https://docs.microsoft.com/stream/streamnew/classic-migration) for more information.</span></span>
