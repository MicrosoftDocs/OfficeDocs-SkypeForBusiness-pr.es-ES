---
title: 'Lync Server 2013: (Opcional) Modificar la asignación de teclas para comandos DTMF'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Modify key mapping for DTMF commands
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398943(v=OCS.15)
ms:contentKeyID: 48185563
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd1a9fbe17a07403fbf0195026d44b490680973e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a><span data-ttu-id="1e9bc-102">(Opcional) Modificar la asignación de teclas para comandos DTMF en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e9bc-102">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e9bc-103">_**Última modificación del tema:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="1e9bc-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="1e9bc-104">Los usuarios de conferencia de acceso telefónico local pueden presionar las teclas en el teclado numérico del teléfono para usar los comandos de tono de marcado de frecuencia múltiple (DTMF).</span><span class="sxs-lookup"><span data-stu-id="1e9bc-104">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands.</span></span> <span data-ttu-id="1e9bc-105">Los comandos DTMF permiten a los usuarios que obtengan acceso telefónico local a una conferencia controlar la configuración de la conferencia (como activar o desactivar el audio propio o bloquear y desbloquear la conferencia) con el teclado numérico de su teléfono.</span><span class="sxs-lookup"><span data-stu-id="1e9bc-105">DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone.</span></span> <span data-ttu-id="1e9bc-106">Puede usar cmdlets para modificar las claves que se usan para los comandos de DTMF.</span><span class="sxs-lookup"><span data-stu-id="1e9bc-106">You can use cmdlets to modify the keys used for the DTMF commands.</span></span> <span data-ttu-id="1e9bc-107">Este paso es opcional.</span><span class="sxs-lookup"><span data-stu-id="1e9bc-107">This step is optional.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1e9bc-108">Para obtener más información sobre estos cmdlets y las posibles opciones de DTMF, consulte la documentación del shell de administración de Lync Server o la ayuda de la línea de comandos del shell de administración de Lync Server Management.</span><span class="sxs-lookup"><span data-stu-id="1e9bc-108">For details about these cmdlets and the possible DTMF options, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="1e9bc-109">Para modificar la asignación de teclas de los comandos DTMF</span><span class="sxs-lookup"><span data-stu-id="1e9bc-109">To modify the key mapping of DTMF commands</span></span>

1.  <span data-ttu-id="1e9bc-110">Inicie sesión en el equipo como miembro del grupo **RTCUniversalServerAdmins** o como miembro del rol **CS-ServerAdministrator** o **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="1e9bc-110">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="1e9bc-111">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1e9bc-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1e9bc-112">Ejecute los siguientes comandos en símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="1e9bc-112">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingDtmfConfiguration
    
    <span data-ttu-id="1e9bc-113">Este cmdlet devuelve la configuración de DTMF usada para las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="1e9bc-113">This cmdlet returns the DTMF settings used for dial-in conferencing.</span></span>

4.  <span data-ttu-id="1e9bc-114">Ejecute el cmdlet siguiente y especifique la tecla que se va a presionar para cada opción que quiera cambiar:</span><span class="sxs-lookup"><span data-stu-id="1e9bc-114">Run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    <span data-ttu-id="1e9bc-115">Este cmdlet modifica la configuración de DTMF que se usa para las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="1e9bc-115">This cmdlet modifies the DTMF settings used for dial-in conferencing.</span></span>
    
    <span data-ttu-id="1e9bc-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1e9bc-116">For example:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    <span data-ttu-id="1e9bc-117">Este ejemplo intercambia la tecla que se presiona para habilitar o deshabilitar anuncios, y la tecla que se presiona para silenciar y reactivar el audio de todos los participantes.</span><span class="sxs-lookup"><span data-stu-id="1e9bc-117">This example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants.</span></span> <span data-ttu-id="1e9bc-118">Dado que no se especifica ninguna identidad, estos cambios se aplican a la configuración de DTMF global.</span><span class="sxs-lookup"><span data-stu-id="1e9bc-118">Because no Identity is specified, these changes apply to the global DTMF settings.</span></span>

5.  <span data-ttu-id="1e9bc-119">(Opcional) Para crear conjuntos de comandos DTMF adicionales para sitios específicos, use el cmdlet **New-CsDialinConferencingDtmfConfiguration** con una identidad de sitio.</span><span class="sxs-lookup"><span data-stu-id="1e9bc-119">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span> <span data-ttu-id="1e9bc-120">Cuando se crea una configuración de DTMF para sitios, la configuración de sitio prevalece por encima de la configuración global.</span><span class="sxs-lookup"><span data-stu-id="1e9bc-120">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="1e9bc-121">Para obtener más información, consulte documentación del shell de administración de Lync Server o la ayuda de la línea de comandos del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1e9bc-121">For details, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

