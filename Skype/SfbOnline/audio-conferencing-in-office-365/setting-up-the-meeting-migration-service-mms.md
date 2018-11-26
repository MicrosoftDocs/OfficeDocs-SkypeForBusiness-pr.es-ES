---
title: Configuración del servicio de migración de reuniones (MMS)
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Servicio de migración (MMS) de la reunión es un Skype para servicio empresarial que se ejecuta en segundo plano y Skype se actualiza automáticamente para las reuniones de negocios y Microsoft Teams para los usuarios. MMS está diseñado para eliminar la necesidad de los usuarios ejecutar la herramienta de migración de la reunión para actualizar su Skype para las reuniones de negocios y Microsoft Teams.
ms.openlocfilehash: b5484459fc01337bd9eb2dad38e9f0e3349abd07
ms.sourcegitcommit: fbcd150e724456ea4521d68cf3acb351e3525e2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2018
ms.locfileid: "26674589"
---
# <a name="setting-up-the-meeting-migration-service-mms"></a><span data-ttu-id="43e3e-104">Configuración del servicio de migración de reuniones (MMS)</span><span class="sxs-lookup"><span data-stu-id="43e3e-104">Setting up the Meeting Migration Service (MMS)</span></span>

<span data-ttu-id="43e3e-105">Servicio de migración (MMS) de la reunión es un Skype para servicio empresarial que se ejecuta en segundo plano y Skype se actualiza automáticamente para las reuniones de negocios y Microsoft Teams para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="43e3e-105">Meeting Migration Service (MMS) is a Skype for Business service that runs in the background and automatically updates Skype for Business and Microsoft Teams meetings for users.</span></span> <span data-ttu-id="43e3e-106">MMS está diseñado para eliminar la necesidad de los usuarios ejecutar la herramienta de migración de la reunión para actualizar su Skype para las reuniones de negocios y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="43e3e-106">MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.</span></span>  <span data-ttu-id="43e3e-107">Esta herramienta no migra reuniones de Skype for Business a reuniones de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="43e3e-107">This tool does not migrate Skype for Business meetings into Microsoft Teams meetings.</span></span>  
  
 <span data-ttu-id="43e3e-108">**Requisitos**</span><span class="sxs-lookup"><span data-stu-id="43e3e-108">**Requirements**</span></span>
  
<span data-ttu-id="43e3e-109">MMS requiere que los buzones de los organizadores de las reuniones estén en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="43e3e-109">MMS requires the mailboxes of meeting organizers to be on Exchange Online.</span></span>
  
 <span data-ttu-id="43e3e-110">**Escenarios principales**</span><span class="sxs-lookup"><span data-stu-id="43e3e-110">**Primary scenarios**</span></span>
  
<span data-ttu-id="43e3e-111">MMS actualiza las reuniones de Skype de un usuario en los siguientes dos escenarios principales:</span><span class="sxs-lookup"><span data-stu-id="43e3e-111">MMS updates Skype meetings for a user in the following two primary scenarios:</span></span>
  
- <span data-ttu-id="43e3e-112">Cuando el usuario se migra de Skype local para Business Server a Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="43e3e-112">When the user is migrated from on-premises Skype for Business Server to Skype for Business Online.</span></span>
    
- <span data-ttu-id="43e3e-113">Cuando un administrador realiza un cambio en la configuración del usuario conferencias de audio que sería necesario actualizar la información de conferencia de audio en las reuniones de dicho usuario.</span><span class="sxs-lookup"><span data-stu-id="43e3e-113">When an admin makes a change to the user's audio conferencing settings that would require updating the audio conferencing information in that user's meetings.</span></span>
    
  <span data-ttu-id="43e3e-114">**Escenarios comunes en los que no puede usar MMS**</span><span class="sxs-lookup"><span data-stu-id="43e3e-114">**Common scenarios where you can't use MMS**</span></span>
  
<span data-ttu-id="43e3e-p103">Estos son algunos de los escenarios comunes con los que puede encontrarse. Todos son escenarios admitidos para la migración, aunque en ellos no se puede ejecutar MMS y tendrá que usar en su lugar la [Herramienta de migración de reuniones](https://go.microsoft.com/fwlink/p/?linkid=626047).</span><span class="sxs-lookup"><span data-stu-id="43e3e-p103">Here are some common scenarios that may apply to you. These are all supported scenarios for migration. However, MMS won't run in these scenarios and you'll need to use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) instead.</span></span>
  
- <span data-ttu-id="43e3e-118">Los buzones de los usuarios están en un servidor de Exchange local.</span><span class="sxs-lookup"><span data-stu-id="43e3e-118">User mailboxes are on Exchange Server on-premises</span></span>
    
- <span data-ttu-id="43e3e-119">Uso de un proveedor de conferencia de audio de terceros</span><span class="sxs-lookup"><span data-stu-id="43e3e-119">Using a third-party audio conferencing provider</span></span>
    
- <span data-ttu-id="43e3e-120">Migración de usuarios de Skype para empresarial en línea para el servidor local Skype</span><span class="sxs-lookup"><span data-stu-id="43e3e-120">Migrating users from Skype for Business Online to on-premises Skype Server</span></span>
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a><span data-ttu-id="43e3e-121">Actualización de reuniones cuando se migra un usuario local a Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="43e3e-121">Updating meetings when an on-premises user is migrated to Skype for Business Online</span></span>

<span data-ttu-id="43e3e-122">Este es el escenario más común en el que MMS puede simplificar la transición a sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="43e3e-122">This is the most common scenario where MMS can help create a smoother transition for your users.</span></span> <span data-ttu-id="43e3e-123">Cuando un usuario se migra desde una Skype local para Business Server a Skype para profesionales en línea, MMS detectará el nuevo usuario y calendario de dicho usuario se analizará en busca de Skype para las reuniones de negocios y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="43e3e-123">When a user is migrated from an on-premises Skype for Business Server to Skype for Business Online, MMS will detect the new user and will scan that user's calendar for Skype for Business and Microsoft Teams meetings.</span></span> <span data-ttu-id="43e3e-124">Las reuniones futuras se actualizará con la nueva información de dicho usuario.</span><span class="sxs-lookup"><span data-stu-id="43e3e-124">Any future meetings will be updated with the new information for that user.</span></span>
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a><span data-ttu-id="43e3e-125">Si está utilizando actualmente el servidor 2015 de Skype para conferencias de audio</span><span class="sxs-lookup"><span data-stu-id="43e3e-125">If you're currently using Skype Server 2015 for audio conferencing</span></span>

<span data-ttu-id="43e3e-126">Le invitamos a seguir los procedimientos recomendados indicados a continuación para obtener la mejor experiencia con MMS en este escenario:</span><span class="sxs-lookup"><span data-stu-id="43e3e-126">We recommend that you follow the best practices below for the best experience with MMS in this scenario:</span></span>
  
- <span data-ttu-id="43e3e-127">Dado que MMS requiere que el buzón del usuario se encuentre en Exchange Online, si también va a realizar la migración desde un servidor de Exchange local, mueva el buzón del usuario a Exchange Online en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="43e3e-127">Because MMS requires the user's mailbox to be on Exchange Online, if you are also migrating from on-premises Exchange Server as well, move the user's mailbox to Exchange Online first.</span></span>
    
- <span data-ttu-id="43e3e-128">Asignar la licencia de **Conferencias de Audio** al usuario antes de ejecutar el `Move-CSUser` cmdlet para migrar el usuario.</span><span class="sxs-lookup"><span data-stu-id="43e3e-128">Assign the **Audio Conferencing** license to the user before you run the `Move-CSUser` cmdlet to migrate the user.</span></span> <span data-ttu-id="43e3e-129">Esto es debido a que MMS también actualiza las reuniones cuando se cambia la configuración de conferencia de audio para un usuario.</span><span class="sxs-lookup"><span data-stu-id="43e3e-129">This is because MMS also updates meetings when audio conferencing settings are changed for a user.</span></span> <span data-ttu-id="43e3e-130">Si no asigna la licencia en primer lugar, MMS actualizará todas las reuniones de nuevo cuando la asigne.</span><span class="sxs-lookup"><span data-stu-id="43e3e-130">If you don't assign the license first, MMS will update all meetings again when you assign the license.</span></span>
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a><span data-ttu-id="43e3e-131">Si utiliza un proveedor de servicios de audioconferencia (ACP) de terceros</span><span class="sxs-lookup"><span data-stu-id="43e3e-131">If you're currently using a third-party audio conferencing provider (ACP)</span></span>

<span data-ttu-id="43e3e-132">Con un ACP de terceros, o si no se ejecuta MMS depende de configuración de conferencia de audio de la organización.</span><span class="sxs-lookup"><span data-stu-id="43e3e-132">With a third-party ACP, whether or not MMS runs depends on your organization's audio conferencing settings.</span></span> <span data-ttu-id="43e3e-133">Puede elegir reemplazar automáticamente los números de acceso telefónico desde su ACP cuando se asigna a un usuario una licencia de **Conferencias de Audio** .</span><span class="sxs-lookup"><span data-stu-id="43e3e-133">You can choose to automatically replace the dial-in numbers from your ACP when you assign a user a **Audio Conferencing** license.</span></span> <span data-ttu-id="43e3e-134">También es posible que deba evitar que esto suceda y que necesite conservar los números de acceso telefónico local de su ACP.</span><span class="sxs-lookup"><span data-stu-id="43e3e-134">On the other hand, you may need to prevent that from happening and retain the dial-in numbers from your ACP.</span></span> <span data-ttu-id="43e3e-135">Para ver la configuración de la organización, ejecute el siguiente comando de Windows PowerShell y comprobar el valor del parámetro `AutomaticallyReplaceAcpProvider`.</span><span class="sxs-lookup"><span data-stu-id="43e3e-135">To see your organization's setting, run the following Windows PowerShell command and check the value of the parameter `AutomaticallyReplaceAcpProvider`.</span></span> <span data-ttu-id="43e3e-136">Si necesita ayuda con PowerShell, consulte la sección [Usar PowerShell para administrar su organización de Skype Empresarial](setting-up-the-meeting-migration-service-mms.md#WPSInfo) al final de este artículo.</span><span class="sxs-lookup"><span data-stu-id="43e3e-136">If you need help with PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- <span data-ttu-id="43e3e-137">Si el valor de este parámetro es $true, MMS va a ejecutar cuando un usuario se le asigna una licencia de **Conferencias de Audio** y actualizar sus reuniones.</span><span class="sxs-lookup"><span data-stu-id="43e3e-137">If the value of this parameter is $true, then MMS will run when a user is assigned a **Audio Conferencing** license and update their meetings.</span></span> <span data-ttu-id="43e3e-138">Los números de acceso telefónico desde su ACP se conservan hasta que se asigna la licencia de **Conferencias de Audio** .</span><span class="sxs-lookup"><span data-stu-id="43e3e-138">The dial-in numbers from your ACP are retained until the **Audio Conferencing** license is assigned.</span></span>
    
- <span data-ttu-id="43e3e-139">Si el valor de este parámetro es $false, a continuación, MMS no actualizarán las reuniones incluso si un usuario se le asigna una licencia de **Conferencias de Audio** .</span><span class="sxs-lookup"><span data-stu-id="43e3e-139">If the value of this parameter is $false, then MMS won't update the meetings even if a user is assigned a **Audio Conferencing** licence.</span></span> <span data-ttu-id="43e3e-140">Los números de acceso telefónico desde su ACP se conservan hasta que el usuario está configurado manualmente para conferencias de audio en Skype para el centro de administración de negocio o con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43e3e-140">The dial-in numbers from your ACP are retained until the user is manually provisioned for audio conferencing in Skype for Business admin center or using Windows PowerShell.</span></span>
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a><span data-ttu-id="43e3e-141">Actualización de reuniones cuando cambie la configuración de conferencia de audio de un usuario</span><span class="sxs-lookup"><span data-stu-id="43e3e-141">Updating meetings when a user's audio conferencing settings change</span></span>

<span data-ttu-id="43e3e-142">MMS actualizará un Skype existente para las reuniones de negocios y Microsoft Teams en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="43e3e-142">MMS will update an existing Skype for Business and Microsoft Teams meetings in the following cases:</span></span>
  
- <span data-ttu-id="43e3e-143">Al asignar o quitar la licencia de **Conferencias de Audio** .</span><span class="sxs-lookup"><span data-stu-id="43e3e-143">When you assign or remove **Audio Conferencing** license.</span></span>
    
- <span data-ttu-id="43e3e-144">Al habilitar o deshabilitar conferencias de audio.</span><span class="sxs-lookup"><span data-stu-id="43e3e-144">When you enable or disable audio conferencing.</span></span>
    
- <span data-ttu-id="43e3e-145">Al cambiar o restablecer el identificador de conferencia para un usuario configurado para usar reuniones públicas.</span><span class="sxs-lookup"><span data-stu-id="43e3e-145">When you change or reset the Conference ID for a user configured to use public meetings.</span></span>
    
- <span data-ttu-id="43e3e-146">Cuando el usuario se mueve a un nuevo puente de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="43e3e-146">When you move the user to a new audio conferencing bridge.</span></span>
    
- <span data-ttu-id="43e3e-147">Cuando un número de teléfono es sin asignar de un puente de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="43e3e-147">When a phone number is unassigned from a audio conferencing bridge.</span></span> <span data-ttu-id="43e3e-148">Este es un escenario complejo que requiere pasos adicionales.</span><span class="sxs-lookup"><span data-stu-id="43e3e-148">This is a complex scenario which requires additional steps.</span></span> <span data-ttu-id="43e3e-149">Para obtener más información, vea [cambiar el teléfono de pago o gratuito números de teléfono de pago en el puente de conferencia de Audio](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="43e3e-149">For more information, see [Change the toll or toll free numbers on your Audio Conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="43e3e-150">MMS solo actualiza las reuniones si se utiliza el puente de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="43e3e-150">MMS only updates meetings when you're using the Microsoft bridge.</span></span> <span data-ttu-id="43e3e-151">Si usa un proveedor de conferencia de audio de terceros, los usuarios será necesario actualizar sus reuniones manualmente.</span><span class="sxs-lookup"><span data-stu-id="43e3e-151">If you are using a third-party audio conferencing provider, the users will need to update their meetings manually.</span></span> <span data-ttu-id="43e3e-152">En este caso, puede usar la [Herramienta de migración de reuniones](https://go.microsoft.com/fwlink/p/?linkid=626047).</span><span class="sxs-lookup"><span data-stu-id="43e3e-152">In this case, you can use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047).</span></span> 
  
<span data-ttu-id="43e3e-153">No todos los cambios a la configuración de conferencia de audio de un usuario desencadenan MMS.</span><span class="sxs-lookup"><span data-stu-id="43e3e-153">Not all changes to a user's audio conferencing settings trigger MMS.</span></span> <span data-ttu-id="43e3e-154">Concretamente, los siguientes cambios no provocan que MMS actualice las reuniones:</span><span class="sxs-lookup"><span data-stu-id="43e3e-154">Specifically, the following two changes won't result in MMS updating meetings:</span></span>
  
- <span data-ttu-id="43e3e-155">Cuando cambia la dirección SIP del organizador de la reunión (tanto el nombre de usuario SIP como el dominio SIP).</span><span class="sxs-lookup"><span data-stu-id="43e3e-155">When you change the SIP address for the meeting organizer (either their SIP user name or their SIP domain)</span></span>
    
- <span data-ttu-id="43e3e-156">Cuando cambia la URL de una reunión de su organización mediante el comando [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).</span><span class="sxs-lookup"><span data-stu-id="43e3e-156">When you change your organization's meeting URL using the [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442) command.</span></span>
    
## <a name="what-happens-when-mms-updates-meetings"></a><span data-ttu-id="43e3e-157">¿Qué sucede cuando MMS actualiza las reuniones?</span><span class="sxs-lookup"><span data-stu-id="43e3e-157">What happens when MMS updates meetings?</span></span>

<span data-ttu-id="43e3e-158">Cuando MMS detecta que es necesario actualizar las reuniones de un usuario, realiza lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="43e3e-158">When MMS detects that a user's meetings need to be updated, it will do the following:</span></span>
  
1. <span data-ttu-id="43e3e-159">Identificar todos los Skype para profesionales y Microsoft Teams las reuniones que el usuario ha programado en el futuro</span><span class="sxs-lookup"><span data-stu-id="43e3e-159">Identify all Skype for Business and Microsoft Teams meetings the user has scheduled in the future</span></span>
    
   - <span data-ttu-id="43e3e-160">Se pasan por alto cualquier Skype para las reuniones de negocios o Teams de Microsoft que se produjo antes de cuando se ejecuta MMS</span><span class="sxs-lookup"><span data-stu-id="43e3e-160">Any Skype for Business or Microsoft Teams meetings that occurred prior to when MMS runs are skipped</span></span>
    
   - <span data-ttu-id="43e3e-161">Solo se actualizan las reuniones en las que el usuario es el organizador.</span><span class="sxs-lookup"><span data-stu-id="43e3e-161">Only the meetings where the user is the organizer are updated</span></span>
    
2. <span data-ttu-id="43e3e-162">Sustituye el bloque de información de la reunión en línea en los detalles de la reunión.</span><span class="sxs-lookup"><span data-stu-id="43e3e-162">Replace the online meeting information block in the meeting details</span></span>
    
3. <span data-ttu-id="43e3e-163">Envía actualizaciones a todos los destinatarios de la reunión en nombre del organizador.</span><span class="sxs-lookup"><span data-stu-id="43e3e-163">Send updates to all meeting recipients on behalf of the meeting organizer</span></span>
    
   <span data-ttu-id="43e3e-164">**¿Cuánto tardará MMS en completar la operación?**</span><span class="sxs-lookup"><span data-stu-id="43e3e-164">**How long will it take for MMS to run?**</span></span>
  
<span data-ttu-id="43e3e-165">La cantidad de tiempo que tarda para que MMS migrar las reuniones varía en función de cuántos usuarios se ven afectados y el número total de Skype para reuniones profesionales o Teams de Microsoft, que cada usuario tiene en su calendario.</span><span class="sxs-lookup"><span data-stu-id="43e3e-165">The amount of time it take for MMS to migrate meetings varies depending on how many users are impacted, and the total number of Skype for Business or Microsoft Teams meetings each user has on their calendar.</span></span> <span data-ttu-id="43e3e-166">Como mínimo, requerirá diez minutos.</span><span class="sxs-lookup"><span data-stu-id="43e3e-166">At a minimum, it will take 10 minutes to run.</span></span> <span data-ttu-id="43e3e-167">Aunque algunas migraciones de gran tamaño pueden llevar hasta 12 horas, la mayoría se completan en una hora.</span><span class="sxs-lookup"><span data-stu-id="43e3e-167">While some large migrations can take up to 12 hours, most migrations should complete within 1 hour.</span></span>
  
 <span data-ttu-id="43e3e-168">**Limitaciones y problemas potenciales**</span><span class="sxs-lookup"><span data-stu-id="43e3e-168">**Limitations and potential issues**</span></span>
  
- <span data-ttu-id="43e3e-169">Se migran sólo el Skype para las reuniones de negocios o Teams de Microsoft que se han programado haciendo clic en el botón **Agregar Skype reunión** en Outlook en el Web o mediante el complemento de reunión de Skype para Outlook.</span><span class="sxs-lookup"><span data-stu-id="43e3e-169">Only the Skype for Business or Microsoft Teams meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated.</span></span> <span data-ttu-id="43e3e-170">En otras palabras, si un usuario copia y pega la información de una reunión en línea de Skype en otra nueva, la nueva reunión no se actualizará.</span><span class="sxs-lookup"><span data-stu-id="43e3e-170">In other words, if a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated.</span></span>
    
- <span data-ttu-id="43e3e-p114">Cuando migra una reunión, MMS sustituye todo el contenido del bloque de información de la reunión en línea. Por lo tanto, si el usuario ha editado ese bloque, los cambios se sobrescriben. No se verá afectado por esta acción ningún contenido que el usuario tenga en los detalles de la reunión, fuera del bloque de información de la reunión en línea.</span><span class="sxs-lookup"><span data-stu-id="43e3e-p114">MMS replaces everything in the online meeting information block when a meeting is migrated. Therefore, if a user has edited that block, their changes will be overwritten. Any content they have in the meeting details outside of the online meeting information block won't be affected.</span></span>
    
     ![El bloque de reunión que MMS actualiza](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- <span data-ttu-id="43e3e-p115">El contenido que se haya creado o adjuntado a la reunión (pizarras, sondeos, etc.) no se conservará tras la ejecución de MMS. Si sus organizadores de reuniones adjuntaron contenido a las reuniones antes de la ejecución de MMS, será necesario volver a crear el contenido una vez finalizada la operación.</span><span class="sxs-lookup"><span data-stu-id="43e3e-p115">Meeting content that was created or attached to the meeting (whiteboards, polls and so on) won't be retained after MMS runs. If your meeting organizers have attached content to the meetings in advance, the content will need to be recreated after MMS runs.</span></span>
    
- <span data-ttu-id="43e3e-p116">También se sobrescribirá el vínculo a las notas de la reunión compartidas en el elemento de calendario y en la reunión de Skype. Tenga en cuenta que las notas de la reunión almacenadas en OneNote no se perderán, solo se sobrescribe el vínculo que conduce a las notas compartidas.</span><span class="sxs-lookup"><span data-stu-id="43e3e-p116">The link to the shared meeting notes in the calendar item and also from within the Skype meeting also will be overwritten. Note that the actual meeting notes stored in OneNote will still be there, it is only the link to the shared notes that gets overwritten.</span></span>
    
- <span data-ttu-id="43e3e-179">Las reuniones que tengan más de 250 participantes (incluido el organizador) no se migrarán.</span><span class="sxs-lookup"><span data-stu-id="43e3e-179">Meetings with more than 250 attendees (including the organizer) won't be migrated.</span></span>
    
- <span data-ttu-id="43e3e-180">Algunos caracteres UNICODE del cuerpo de la invitación se pueden actualizar de forma incorrecta y mostrar uno de los siguientes caracteres especiales: ï, ¿, ½, �.</span><span class="sxs-lookup"><span data-stu-id="43e3e-180">Some UNICODE characters in the body of the invite may be incorrectly updated to one of the following special characters: ï, ¿, ½, �.</span></span>
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a><span data-ttu-id="43e3e-181">¿Qué verán los usuarios cuando MMS actualice sus reuniones?</span><span class="sxs-lookup"><span data-stu-id="43e3e-181">What will the users see when MMS updates their meetings?</span></span>

<span data-ttu-id="43e3e-182">Al igual que la Herramienta de migración de reuniones, MMS envía las actualizaciones de reuniones en nombre de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="43e3e-182">Just like the Meeting Migration Tool, MMS sends meeting updates on behalf of users.</span></span> <span data-ttu-id="43e3e-183">Por lo tanto, lo único que verán los usuarios es otra ronda de notificaciones de aceptación de reunión para sus reuniones.</span><span class="sxs-lookup"><span data-stu-id="43e3e-183">Therefore, the only thing your users will see is another round of meeting acceptance notifications for their meetings.</span></span> <span data-ttu-id="43e3e-184">Esto puede resultar confusa para los usuarios, por lo que recomendamos que notifique a los usuarios por adelantado no sólo cuando se migran ellos de local a Skype para profesionales en línea, pero también cuando se realizan cambios de conferencias de audio que activará MMS.</span><span class="sxs-lookup"><span data-stu-id="43e3e-184">This might be confusing for users, so we recommend that you notify your users in advance not only when you migrate them from on-premises to Skype for Business Online, but also when you make audio conferencing changes that will trigger MMS.</span></span>
  
## <a name="managing-mms"></a><span data-ttu-id="43e3e-185">Administrar MMS</span><span class="sxs-lookup"><span data-stu-id="43e3e-185">Managing MMS</span></span>

<span data-ttu-id="43e3e-186">Debe usar Windows PowerShell para administrar MMS y compruebe el estado de las migraciones continuadas.</span><span class="sxs-lookup"><span data-stu-id="43e3e-186">You need to use Windows PowerShell to manage MMS and check the status of ongoing migrations.</span></span> <span data-ttu-id="43e3e-187">La información de esta sección asume que está familiarizado con el uso de PowerShell para administrar su organización de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="43e3e-187">The information in this section assumes that you're familiar with using PowerShell to manage your Skype for Business organization.</span></span> <span data-ttu-id="43e3e-188">Si está familiarizado con PowerShell, vea la sección [Uso de PowerShell para administrar su Skype para organización empresarial](setting-up-the-meeting-migration-service-mms.md#WPSInfo) al final de este artículo.</span><span class="sxs-lookup"><span data-stu-id="43e3e-188">If you are new to PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a><span data-ttu-id="43e3e-189">¿Cómo compruebo el estado de las migraciones de las reuniones?</span><span class="sxs-lookup"><span data-stu-id="43e3e-189">How do I check the status of meeting migrations?</span></span>

<span data-ttu-id="43e3e-p119">Debe usar el cmdlet  `Get-CsMeetingMigrationStatus` para comprobar el estado de las migraciones de las reuniones. A continuación puede ver algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="43e3e-p119">You use the  `Get-CsMeetingMigrationStatus` cmdlet to check the status of meeting migrations. Below are some examples.</span></span>
  
<span data-ttu-id="43e3e-192">Para obtener un resumen del estado de todas las migraciones de MMS, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="43e3e-192">To get a summary status of all MMS migrations, run the following command:</span></span>
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="43e3e-193">De este modo obtendrá una vista en forma de tabla de todos los estados de migración similar a esta:</span><span class="sxs-lookup"><span data-stu-id="43e3e-193">This will give you a tabular view of all migration states like this:</span></span>
  
<span data-ttu-id="43e3e-194">Estado UserCount---------------</span><span class="sxs-lookup"><span data-stu-id="43e3e-194">State UserCount---------------</span></span><br/> <span data-ttu-id="43e3e-195">21 pendientes</span><span class="sxs-lookup"><span data-stu-id="43e3e-195">Pending 21</span></span><br/><span data-ttu-id="43e3e-196">6 en curso</span><span class="sxs-lookup"><span data-stu-id="43e3e-196">InProgress 6</span></span><br/> <span data-ttu-id="43e3e-197">2 con errores</span><span class="sxs-lookup"><span data-stu-id="43e3e-197">Failed 2</span></span> <br/> <span data-ttu-id="43e3e-198">131 correctas</span><span class="sxs-lookup"><span data-stu-id="43e3e-198">Succeeded 131</span></span>
> [!IMPORTANT]
> <span data-ttu-id="43e3e-p120">Si ve alguna migración que haya dado error, solucione los problemas cuanto antes. Nadie podrá acceder mediante acceso telefónico local a las reuniones organizadas por estos usuarios hasta que lo haga. Consulte la sección [¿Qué debo hacer si hay un error?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="43e3e-p120">If you see any migrations that have failed, take action to resolve these issues as soon as possible. People won't be able to dial-in to the meetings organized by those users until you address these. See the [What do I do if there is an error?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) section for more information.</span></span>
  
<span data-ttu-id="43e3e-p121">Para obtener información detallada de todas las migraciones realizadas en un período de tiempo específico puede usar los parámetros  `StartTime` y `EndTime`. Por ejemplo, el siguiente comando devolverá información detallada sobre todas las migraciones realizadas entre el 1 de octubre de 2016 y el 8 de octubre de 2016.</span><span class="sxs-lookup"><span data-stu-id="43e3e-p121">To get full details of all migrations within a specific time period, you can use the  `StartTime` and `EndTime` parameters. For example, the following command will return full details on all migrations that occurred from October 1, 2016 to October 8, 2016.</span></span>
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

<span data-ttu-id="43e3e-p122">También puede interesarle comprobar el estado de la migración de un usuario concreto, para lo que puede usar el parámetro  `UserId`. Por ejemplo, el siguiente comando devolverá el estado del usuario ashaw@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="43e3e-p122">You also may want to check the status of the migration for a specific user, and you can use the  `UserId` parameter for that. For example, the following command will return the status for the user ashaw@contoso.com:</span></span>
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### <a name="what-do-i-do-if-there-is-an-error"></a><span data-ttu-id="43e3e-206">¿Qué debo hacer si hay un error?</span><span class="sxs-lookup"><span data-stu-id="43e3e-206">What do I do if there is an error?</span></span>
<span data-ttu-id="43e3e-207"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="43e3e-207"></span></span>

<span data-ttu-id="43e3e-208">Si ejecuta el cmdlet  `Get-CsMeetingMigrationStatus` para obtener una vista de resumen y advierte que hay migraciones con el estado Con erroresesto es lo que tiene que hacer:</span><span class="sxs-lookup"><span data-stu-id="43e3e-208">When you run the  `Get-CsMeetingMigrationStatus` cmdlet to get a summary view and notice that there are migrations in Failed state, here's what you need to do:</span></span>
  
1. <span data-ttu-id="43e3e-p123">Determine a qué usuarios afecta. Ejecute el siguiente comando para obtener la lista de usuarios afectados y el error concreto registrado:</span><span class="sxs-lookup"><span data-stu-id="43e3e-p123">Determine which users are affected. Run the following command to get the list of affected users, and the specific error that was reported:</span></span>
    
   ```
   Get-CsMeetingMigrationStatus | Where {$_.State -eq "Failed"} | Format-Table UserId,LastMessage
   ```

2. <span data-ttu-id="43e3e-211">Ejecute la [Herramienta de migración de reuniones](https://go.microsoft.com/fwlink/p/?linkid=626047) para cada uno de estos usuarios, para migrar sus reuniones manualmente.</span><span class="sxs-lookup"><span data-stu-id="43e3e-211">For each of those user, run the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) to manually migrate their meetings.</span></span>
    
3. <span data-ttu-id="43e3e-212">Si la migración sigue sin funcionar con la Herramienta de migración de reuniones, tiene dos opciones:</span><span class="sxs-lookup"><span data-stu-id="43e3e-212">If migration still doesn't work with the Meeting Migration Tool, you have two options:</span></span>
    
   - <span data-ttu-id="43e3e-213">Hacer que los usuarios creen reuniones de Skype nuevas.</span><span class="sxs-lookup"><span data-stu-id="43e3e-213">Have the users create new Skype meetings.</span></span>
    
   - <span data-ttu-id="43e3e-214">[Ponerse en contacto con el equipo de soporte técnico](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span><span class="sxs-lookup"><span data-stu-id="43e3e-214">[Contact support](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span></span>
    
### <a name="enabling-and-disabling-mms"></a><span data-ttu-id="43e3e-215">Habilitar y deshabilitar MMS</span><span class="sxs-lookup"><span data-stu-id="43e3e-215">Enabling and disabling MMS</span></span>
<span data-ttu-id="43e3e-216"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="43e3e-216"></span></span>

<span data-ttu-id="43e3e-217">MMS está habilitado de forma predeterminada para todas las organizaciones, pero se puede deshabilitar si es necesario.</span><span class="sxs-lookup"><span data-stu-id="43e3e-217">MMS is enabled by default for all organizations, but it can be disabled as needed.</span></span> <span data-ttu-id="43e3e-218">Por ejemplo, si desea migrar manualmente todas las reuniones o si usa un proveedor de conferencia de audio de terceros, es posible que no necesita MMS ejecuta.</span><span class="sxs-lookup"><span data-stu-id="43e3e-218">For example, if you want to manually migrate all meetings or if you use a third-party audio conferencing provider, you may not need MMS running.</span></span> <span data-ttu-id="43e3e-219">También tiene la opción de deshabilitar temporalmente MMS.</span><span class="sxs-lookup"><span data-stu-id="43e3e-219">You may also choose to temporarily disable MMS.</span></span> <span data-ttu-id="43e3e-220">Por ejemplo, se pueden realizar cambios importantes en la configuración de conferencia de audio para su organización y no desea MMS se ejecuta hasta que se hayan completado todos los cambios.</span><span class="sxs-lookup"><span data-stu-id="43e3e-220">For example, you may be doing substantial changes to the audio conferencing settings for your organization and you don't want MMS to run until all changes are completed.</span></span>
  
<span data-ttu-id="43e3e-p125">Para ver si MMS está habilitado en su organización, ejecute el siguiente comando y observe el valor del parámetro  `MeetingMigrationEnabled`. Si este parámetro está ajustado en $true, MMS está habilitado.</span><span class="sxs-lookup"><span data-stu-id="43e3e-p125">To see if MMS is enabled for your organization, run the following command and check the value for the  `MeetingMigrationEnabled` parameter. If this parameter is set to$true, MMS is enabled.</span></span>
  
```
Get-CsTenantMigrationConfiguration
```

<span data-ttu-id="43e3e-223">Para deshabilitar MMS, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="43e3e-223">To disable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```

<span data-ttu-id="43e3e-224">Para habilitar MMS, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="43e3e-224">To enable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $true
```

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a><span data-ttu-id="43e3e-225">Habilitación y deshabilitación de MMS únicamente para los cambios de conferencias de audio</span><span class="sxs-lookup"><span data-stu-id="43e3e-225">Enabling and disabling MMS only for audio conferencing changes</span></span>
<span data-ttu-id="43e3e-226"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="43e3e-226"></span></span>

<span data-ttu-id="43e3e-227">También puede deshabilitar MMS únicamente para los cambios de conferencias de audio.</span><span class="sxs-lookup"><span data-stu-id="43e3e-227">You can also disable MMS only for audio conferencing changes.</span></span> <span data-ttu-id="43e3e-228">Aún se ejecutará cuando un usuario se migra de Skype para empresarial local a Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="43e3e-228">It will still run when a user is migrated from Skype for Business on-premises to Skype for Business Online.</span></span> <span data-ttu-id="43e3e-229">Para comprobar el estado actual de MMS para actualizaciones en las conferencias de audio, ejecute el siguiente comando y compruebe el valor de la `AutomaticallyMigrateUserMeetings` parámetro.</span><span class="sxs-lookup"><span data-stu-id="43e3e-229">To check the current MMS status for audio conferencing updates, run the following command and check the value for the  `AutomaticallyMigrateUserMeetings` parameter.</span></span> <span data-ttu-id="43e3e-230">Si este parámetro se establece en true de $, MMS se establece para actualizar las reuniones del usuario cuando se cambia la configuración de conferencias de audio.</span><span class="sxs-lookup"><span data-stu-id="43e3e-230">If this parameter is set to$true, MMS is set to update user meetings when audio conferencing settings are changed.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

<span data-ttu-id="43e3e-231">Para deshabilitar MMS para conferencias de audio, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="43e3e-231">To disable MMS for audio conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

<span data-ttu-id="43e3e-232">Para habilitar MMS para conferencias de audio, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="43e3e-232">To enable MMS for audio conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a><span data-ttu-id="43e3e-233">¿Cómo ejecuto la migración de reuniones manualmente para un usuario?</span><span class="sxs-lookup"><span data-stu-id="43e3e-233">How do I run Meeting Migration manually for a user?</span></span>
<span data-ttu-id="43e3e-234"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="43e3e-234"></span></span>

<span data-ttu-id="43e3e-235">Además de las migraciones de reuniones automáticas, puede ejecutar la migración de reuniones de forma manual para un usuario a través del cmdlet **Start-CsExMeetingMigration**.</span><span class="sxs-lookup"><span data-stu-id="43e3e-235">In addition to the automatic meeting migrations, you can also run the meeting migration manually for a user by running the cmdlet **Start-CsExMeetingMigration**.</span></span> <span data-ttu-id="43e3e-236">Este cmdlet agrega el usuario en la cola de migración de la reunión.</span><span class="sxs-lookup"><span data-stu-id="43e3e-236">This cmdlet adds the user in meeting migration queue.</span></span> <span data-ttu-id="43e3e-237">El servicio de migración de reuniones leerá la solicitud del usuario y migrará sus reuniones.</span><span class="sxs-lookup"><span data-stu-id="43e3e-237">Meeting Migration Service will read the user request and migrate their meetings.</span></span> <span data-ttu-id="43e3e-238">Puede comprobar el estado de la migración de reuniones con el cmdlet **Get-CsMeetingMigrationStatus**.</span><span class="sxs-lookup"><span data-stu-id="43e3e-238">You can check the status of meeting migration by cmdlet **Get-CsMeetingMigrationStatus**.</span></span>
  
<span data-ttu-id="43e3e-239">Aquí puede ver un ejemplo que inicia la migración de reuniones para el usuario ashaw@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="43e3e-239">Here is an example that kicks off meeting migration for the user ashaw@contoso.com:</span></span>
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## <a name="using-powershell-to-manage-your-skype-for-business-organization"></a><span data-ttu-id="43e3e-240">Usar PowerShell para administrar su organización de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="43e3e-240">Using PowerShell to manage your Skype for Business organization</span></span>
<span data-ttu-id="43e3e-241"><a name="WPSInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="43e3e-241"></span></span>

 <span data-ttu-id="43e3e-242">**Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**</span><span class="sxs-lookup"><span data-stu-id="43e3e-242">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="43e3e-243">Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="43e3e-243">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="43e3e-244">Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="43e3e-244">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="43e3e-p128">Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="43e3e-p128">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="43e3e-p129">También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="43e3e-p129">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="43e3e-251">Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="43e3e-251">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
 <span data-ttu-id="43e3e-252">**Iniciar una sesión de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="43e3e-252">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="43e3e-253">En el **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="43e3e-253">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="43e3e-254">En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="43e3e-254">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="43e3e-255">Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="43e3e-255">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
>   ```
>   Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
>   $credential = Get-Credential
>   $session = New-CsOnlineSession -Credential $credential
>   Import-PSSession $session
>   ```
> <span data-ttu-id="43e3e-256">Si desea obtener más información acerca de cómo iniciar Windows PowerShell, vea [Conectar a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [Configurar el equipo de Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="43e3e-256">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
- <span data-ttu-id="43e3e-p130">En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="43e3e-p130">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="43e3e-260">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="43e3e-260">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="43e3e-261">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="43e3e-261">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="43e3e-p131">Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="43e3e-p131">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="43e3e-264">Mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="43e3e-264">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="43e3e-265">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="43e3e-265">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="43e3e-266">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="43e3e-266">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="43e3e-267">See also</span><span class="sxs-lookup"><span data-stu-id="43e3e-267">Related topics</span></span>

[<span data-ttu-id="43e3e-268">Probar o comprar Audioconferencia en Office 365</span><span class="sxs-lookup"><span data-stu-id="43e3e-268">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
