---
title: 'Lync Server 2013: configuración del modo de privacidad de presencia mejorada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c16e33197ed28744df126d672385359f5eb8781b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a><span data-ttu-id="cb640-102">Configurar el modo de privacidad de presencia mejorada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb640-102">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb640-103">_**Última modificación del tema:** 2014-12-08_</span><span class="sxs-lookup"><span data-stu-id="cb640-103">_**Topic Last Modified:** 2014-12-08_</span></span>

<span data-ttu-id="cb640-104">Con el modo de privacidad de presencia mejorada, los usuarios pueden restringir la información de presencia para que esté visible solo para los contactos que aparecen en la lista de contactos de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="cb640-104">With enhanced presence privacy mode, users can restrict their presence information so that it is visible only to the contacts listed in their Lync 2013 Contacts list.</span></span> <span data-ttu-id="cb640-105">Los cmdlets **New-CsPrivacyConfiguration** y **set-CsPrivacyConfiguration** tienen un parámetro EnablePrivacyMode controla esta opción.</span><span class="sxs-lookup"><span data-stu-id="cb640-105">The **New-CsPrivacyConfiguration** and **Set-CsPrivacyConfiguration** cmdlets have an EnablePrivacyMode parameter controls this option.</span></span> <span data-ttu-id="cb640-106">Cuando EnablePrivacyMode se establece en true, la opción para restringir la información de presencia a los contactos está disponible en las opciones de estado de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="cb640-106">When EnablePrivacyMode is set to True, the option to restrict presence information to contacts becomes available in the Lync 2013 Status options.</span></span> <span data-ttu-id="cb640-107">Si EnablePrivacyMode está definido en False, los usuarios pueden elegir si quieren permitir que todo el mundo vea siempre su información de presencia o adaptarse a los posibles cambios que el administrador realice en el modo de privacidad.</span><span class="sxs-lookup"><span data-stu-id="cb640-107">When EnablePrivacyMode is set to False, users can choose either to always allow everyone to see their presence information or to adhere to any future changes the administrator makes to the privacy mode.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cb640-108">Las versiones anteriores no respetan la configuración de privacidad de Lync 2013 y Lync 2010 (Microsoft Office Communicator 2007 R2 o Microsoft Office Communicator 2007).</span><span class="sxs-lookup"><span data-stu-id="cb640-108">Lync 2013 and Lync 2010 privacy settings are not honored by previous versions (Microsoft Office Communicator 2007 R2 or Microsoft Office Communicator 2007).</span></span> <span data-ttu-id="cb640-109">Si se permite iniciar sesión en versiones anteriores de Office Communicator, una persona a la que no se le haya autorizado ver el estado, la información de contacto o la imagen del usuario de Lync 2013 puede verla.</span><span class="sxs-lookup"><span data-stu-id="cb640-109">If previous versions of Office Communicator are allowed to sign in, a Lync 2013 user’s status, contact information, or picture could be viewed by someone who has not been authorized to view it.</span></span> <span data-ttu-id="cb640-110">Además, la configuración de privacidad de un usuario de Lync 2013 se restablece si inicia sesión con una versión anterior de Communicator.</span><span class="sxs-lookup"><span data-stu-id="cb640-110">Additionally, a Lync 2013 user’s privacy settings are reset if he or she later signs in with previous version of Communicator.</span></span><BR><span data-ttu-id="cb640-111">Por estas razones, en un escenario de migración, antes de habilitar el modo de privacidad de presencia mejorada:</span><span class="sxs-lookup"><span data-stu-id="cb640-111">For these reasons, in a migration scenario, before you enable enhanced presence privacy mode:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="cb640-112">Asegúrese de que todos los usuarios tienen instalado Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="cb640-112">Ensure that every user has Lync 2013 installed.</span></span></P>
> <LI>
> <P><span data-ttu-id="cb640-113">Defina una regla de directiva de versiones de cliente para impedir que versiones anteriores de Communicator inicien sesión.</span><span class="sxs-lookup"><span data-stu-id="cb640-113">Define a client version policy rule to prevent previous versions of Communicator from signing in.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a><span data-ttu-id="cb640-114">Para habilitar el modo de privacidad de presencia mejorada</span><span class="sxs-lookup"><span data-stu-id="cb640-114">To enable enhanced presence privacy mode</span></span>

1.  <span data-ttu-id="cb640-115">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="cb640-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="cb640-116">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="cb640-116">Run the following command:</span></span>
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    <span data-ttu-id="cb640-117">Este comando habilita el modo de privacidad para todos los parámetros de privacidad que se encuentran actualmente en uso en la organización.</span><span class="sxs-lookup"><span data-stu-id="cb640-117">This command enables privacy mode for all the privacy configuration settings currently in use in the organization.</span></span> <span data-ttu-id="cb640-118">Para obtener más información sobre cómo la Directiva de modo de privacidad de presencia mejorada de Lync Server administra la presencia de contactos para el cliente de Lync 2013, consulte el artículo de Microsoft Knowledge base [que habilita Lync Server Enhanced Presence el modo de privacidad actualiza el estado de presencia de algunos contactos de Lync a "no disponible"](http://support.microsoft.com/kb/3020057).</span><span class="sxs-lookup"><span data-stu-id="cb640-118">For more information about how the Lync Server enhanced presence privacy mode policy configurations manages contact presence for the Lync 2013 client, see the Microsoft KB article [Enabling Lync Server enhanced presence privacy mode updates the presence status of some Lync contacts to "unavailable"](http://support.microsoft.com/kb/3020057).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cb640-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb640-119">See Also</span></span>


[<span data-ttu-id="cb640-120">Get-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="cb640-120">Get-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[<span data-ttu-id="cb640-121">New-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="cb640-121">New-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[<span data-ttu-id="cb640-122">Set-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="cb640-122">Set-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

