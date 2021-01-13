---
title: Administrar la asignación de claves para comandos DTMF en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 'Resumen: obtenga información sobre cómo administrar la asignación de teclas de comandos de tono de marcado de frecuencia múltiple (DTMF) en Skype Empresarial Server.'
ms.openlocfilehash: b804c9a0923630f6de3d1b5af2acdda123cc6331
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828100"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a><span data-ttu-id="57bb0-103">Administrar la asignación de claves para comandos DTMF en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="57bb0-103">Manage key mapping for DTMF commands in Skype for Business Server</span></span>
 
<span data-ttu-id="57bb0-104">**Resumen:** Obtenga información sobre cómo administrar la asignación de claves de comandos de tono de marcado de frecuencia múltiple (DTMF) en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="57bb0-104">**Summary:** Learn how to manage key mapping of dual-tone multi-frequency (DTMF) commands in Skype for Business Server.</span></span>
  
<span data-ttu-id="57bb0-105">Los usuarios de conferencia de acceso telefónico local pueden presionar las teclas del teléfono para usar los comandos de tono de marcado de frecuencia múltiple (DTMF).</span><span class="sxs-lookup"><span data-stu-id="57bb0-105">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands.</span></span> <span data-ttu-id="57bb0-106">Los comandos DTMF permiten a los usuarios que obtengan acceso telefónico a una conferencia controlar la configuración de la conferencia (como activar o desactivar el audio propio o bloquear y desbloquear la conferencia) mediante el teclado de su teléfono.</span><span class="sxs-lookup"><span data-stu-id="57bb0-106">DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone.</span></span> 
  
<span data-ttu-id="57bb0-107">Para administrar las claves usadas para los comandos DTMF, use el Shell de administración de Skype Empresarial Server con los cmdlets **Get-CsDialinConferencingDtmfConfiguration**, **Set-CsDialinConferencingDtmfConfiguration** y **New-CsDialinConferencingDtmfConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="57bb0-107">To manage the keys used for the DTMF commands, use the Skype for Business Server Management Shell with the **Get-CsDialinConferencingDtmfConfiguration**, **Set-CsDialinConferencingDtmfConfiguration**, and **New-CsDialinConferencingDtmfConfiguration** cmdlets.</span></span>
  
<span data-ttu-id="57bb0-108">Cuando se crea una configuración de DTMF para sitios, la configuración de sitio prevalece por encima de la configuración global.</span><span class="sxs-lookup"><span data-stu-id="57bb0-108">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="57bb0-109">Administrar la asignación de claves de comandos DTMF</span><span class="sxs-lookup"><span data-stu-id="57bb0-109">Manage the key mapping of DTMF commands</span></span>

1. <span data-ttu-id="57bb0-110">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol Cs-ServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="57bb0-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="57bb0-111">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="57bb0-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="57bb0-112">Para ver la configuración de DTMF usada para conferencias de acceso telefónico local, ejecute el siguiente comando en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="57bb0-112">To view the DTMF settings used for dial-in conferencing, run the following command at the command prompt :</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. <span data-ttu-id="57bb0-113">Para modificar la configuración de DTMF usada para las conferencias de acceso telefónico local, ejecute el siguiente cmdlet y especifique la tecla que se debe presionar para cada opción que desee cambiar:</span><span class="sxs-lookup"><span data-stu-id="57bb0-113">To modify the DTMF settings used for dial-in conferencing, run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. <span data-ttu-id="57bb0-114">(Opcional) Para crear conjuntos de comandos DTMF adicionales para sitios específicos, use el cmdlet **New-CsDialinConferencingDtmfConfiguration** con una identidad de sitio.</span><span class="sxs-lookup"><span data-stu-id="57bb0-114">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span>
    
<span data-ttu-id="57bb0-115">En el siguiente ejemplo se intercambia la tecla que se presiona para habilitar o deshabilitar anuncios y la tecla que se presiona para silenciar y desactivar el audio de todos los participantes.</span><span class="sxs-lookup"><span data-stu-id="57bb0-115">The following example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants.</span></span> <span data-ttu-id="57bb0-116">Dado que no se especifica ninguna identidad, estos cambios se aplican a la configuración global de DTMF:</span><span class="sxs-lookup"><span data-stu-id="57bb0-116">Because no Identity is specified, these changes apply to the global DTMF settings:</span></span>
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

<span data-ttu-id="57bb0-117">Para obtener más información, vea [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)y [New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="57bb0-117">For more information, see [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps), and [New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).</span></span>
  

