---
title: Administrar la asignación de teclas para comandos DTMF en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 'Resumen: Conozca cómo administrar la asignación de teclas de comandos de multifrecuencia de tono dual (DTMF) en Skype para Business Server 2015.'
ms.openlocfilehash: 0dca7143b59b7cf4ded0302f763053e71be3bb2b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server-2015"></a><span data-ttu-id="25c6f-103">Administrar la asignación de teclas para comandos DTMF en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="25c6f-103">Manage key mapping for DTMF commands in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="25c6f-104">**Resumen:** Aprenda a administrar la asignación de teclas de comandos de multifrecuencia de tono dual (DTMF) en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="25c6f-104">**Summary:** Learn how to manage key mapping of dual-tone multi-frequency (DTMF) commands in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="25c6f-p101">Los usuarios de conferencia de acceso telefónico local pueden presionar las teclas en el teclado numérico del teléfono para usar los comandos de tono de marcado de frecuencia múltiple (DTMF). Los comandos DTMF permiten a los usuarios que obtengan acceso telefónico local a una conferencia controlar la configuración de la conferencia (como activar o desactivar el audio propio o bloquear y desbloquear la conferencia) con el teclado numérico de su teléfono.</span><span class="sxs-lookup"><span data-stu-id="25c6f-p101">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands. DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone.</span></span> 
  
<span data-ttu-id="25c6f-107">Para administrar las claves utilizadas para los comandos DTMF, use el Skype para el Shell de administración de servidor empresariales con **Get-CsDialinConferencingDtmfConfiguration**, **Conjunto de CsDialinConferencingDtmfConfiguration**y ** CsDialinConferencingDtmfConfiguration nuevo** cmdlets.</span><span class="sxs-lookup"><span data-stu-id="25c6f-107">To manage the keys used for the DTMF commands, use the Skype for Business Server Management Shell with the **Get-CsDialinConferencingDtmfConfiguration**, **Set-CsDialinConferencingDtmfConfiguration**, and **New-CsDialinConferencingDtmfConfiguration** cmdlets.</span></span>
  
<span data-ttu-id="25c6f-108">Cuando se crea una configuración de DTMF para sitios, la configuración de sitio prevalece por encima de la configuración global.</span><span class="sxs-lookup"><span data-stu-id="25c6f-108">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="25c6f-109">Administrar la asignación de teclas de comandos DTMF</span><span class="sxs-lookup"><span data-stu-id="25c6f-109">Manage the key mapping of DTMF commands</span></span>

1. <span data-ttu-id="25c6f-110">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o bien como miembro del rol Cs-ServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="25c6f-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="25c6f-111">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="25c6f-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="25c6f-112">Para ver la configuración de DTMF usada para conferencias de acceso telefónico local, ejecute el siguiente comando en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="25c6f-112">To view the DTMF settings used for dial-in conferencing, run the following command at the command prompt :</span></span>
    
  ```
  Get-CsDialinConferencingDtmfConfiguration
  ```

4. <span data-ttu-id="25c6f-113">Para modificar la configuración de DTMF usada para conferencias de acceso telefónico local, ejecute el cmdlet siguiente y especifique la tecla que se necesita presionar para cada una de las opciones que desea cambiar:</span><span class="sxs-lookup"><span data-stu-id="25c6f-113">To modify the DTMF settings used for dial-in conferencing, run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
  ```
  Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
[-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
[-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
[-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
[-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
  ```

5. <span data-ttu-id="25c6f-114">(Opcional) Para crear conjuntos de comandos DTMF adicionales para sitios específicos, use el cmdlet **New-CsDialinConferencingDtmfConfiguration** con una identidad de sitio.</span><span class="sxs-lookup"><span data-stu-id="25c6f-114">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span>
    
<span data-ttu-id="25c6f-p102">En este ejemplo se cambia la tecla que se presiona para habilitar o deshabilitar anuncios y la tecla que se presiona para activar o desactivar el audio de todos los participantes. Como no se ha especificado el parámetro Identity, estos cambios se aplican a la configuración de DTMF global:</span><span class="sxs-lookup"><span data-stu-id="25c6f-p102">The following example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants. Because no Identity is specified, these changes apply to the global DTMF settings:</span></span>
  
```
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

<span data-ttu-id="25c6f-117">Para obtener más información, consulte [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Conjunto de CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)y [CsDialInConferencingDtmfConfiguration de nuevo](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="25c6f-117">For more information, see [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps), and [New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).</span></span>
  

