---
title: 'Lync Server 2013: configurar las opciones del estacionamiento de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Call Park settings
ms:assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425886(v=OCS.15)
ms:contentKeyID: 48183922
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72d3f60747f9b3456a6999358b0cf318b5e6d91d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521167"
---
# <a name="configure-call-park-settings-in-lync-server-2013"></a><span data-ttu-id="f77cb-102">Configurar las opciones del estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f77cb-102">Configure Call Park settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f77cb-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f77cb-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f77cb-104">Si no quiere usar la configuración predeterminada del estacionamiento de llamadas, puede personalizarla.</span><span class="sxs-lookup"><span data-stu-id="f77cb-104">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="f77cb-105">Al instalar la aplicación estacionamiento de llamadas, la configuración global se configura de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f77cb-105">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="f77cb-106">Puede modificar esta configuración global y, además, puede especificar opciones de configuración específicas del sitio.</span><span class="sxs-lookup"><span data-stu-id="f77cb-106">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="f77cb-107">Use el cmdlet **New-CsCpsConfiguration** para crear una nueva configuración específica del sitio.</span><span class="sxs-lookup"><span data-stu-id="f77cb-107">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="f77cb-108">Use cmdlet **Set-CsCpsConfiguration** para modificar la configuración existente.</span><span class="sxs-lookup"><span data-stu-id="f77cb-108">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f77cb-109">Como mínimo, se recomienda configurar la opción <STRONG>OnTimeoutURI</STRONG> para el destino de reserva que se usará cuando el tiempo de espera de una llamada estacionada se agote y deje de sonar.</span><span class="sxs-lookup"><span data-stu-id="f77cb-109">At a minimum, we recommend that you configure the <STRONG>OnTimeoutURI</STRONG> option for the fallback destination to use when a parked call times out and ringback fails.</span></span>



</div>

<span data-ttu-id="f77cb-110">Use el cmdlet **New-CsCpsConfiguration** o el cmdlet **Set-CsCpsConfiguration** para configurar las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f77cb-110">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f77cb-111">Esta opción:</span><span class="sxs-lookup"><span data-stu-id="f77cb-111">This option:</span></span></th>
<th><span data-ttu-id="f77cb-112">Especifica:</span><span class="sxs-lookup"><span data-stu-id="f77cb-112">Specifies this:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f77cb-113"><strong>CallPickupTimeoutThreshold</strong></span><span class="sxs-lookup"><span data-stu-id="f77cb-113"><strong>CallPickupTimeoutThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="f77cb-114">El tiempo que transcurre después de estacionar la llamada hasta que vuelve a sonar en el teléfono en el que se respondió.</span><span class="sxs-lookup"><span data-stu-id="f77cb-114">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p>
<p><span data-ttu-id="f77cb-p102">El valor debe introducirse con el formato hh:mm:ss para especificar las horas, los minutos y los segundos. El valor mínimo es 10 segundos y el máximo, 10 minutos. El valor predeterminado es 00:01:30.</span><span class="sxs-lookup"><span data-stu-id="f77cb-p102">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds. The minimum value is 10 seconds, and the maximum value is 10 minutes. The default is 00:01:30.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f77cb-118"><strong>EnableMusicOnHold</strong></span><span class="sxs-lookup"><span data-stu-id="f77cb-118"><strong>EnableMusicOnHold</strong></span></span></p></td>
<td><p><span data-ttu-id="f77cb-119">Si la persona que llama escuchará música mientras la llamada está estacionada.</span><span class="sxs-lookup"><span data-stu-id="f77cb-119">Whether music plays for a caller while a call is parked.</span></span></p>
<p><span data-ttu-id="f77cb-p103">Los valores son True o False. El valor predeterminado es True.</span><span class="sxs-lookup"><span data-stu-id="f77cb-p103">Values are True or False. The default is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f77cb-122"><strong>MaxCallPickupAttempts</strong></span><span class="sxs-lookup"><span data-stu-id="f77cb-122"><strong>MaxCallPickupAttempts</strong></span></span></p></td>
<td><p><span data-ttu-id="f77cb-p104">El número de veces que una llamada estacionada vuelve a sonar en el teléfono en que se respondió antes de transferirla al identificador uniforme de recursos (URI) de reserva que se especifique para <strong>OnTimeoutURI</strong>. El valor predeterminado es 1.</span><span class="sxs-lookup"><span data-stu-id="f77cb-p104">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for <strong>OnTimeoutURI</strong>. The default is 1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f77cb-125"><strong>OnTimeoutURI</strong></span><span class="sxs-lookup"><span data-stu-id="f77cb-125"><strong>OnTimeoutURI</strong></span></span></p></td>
<td><p><span data-ttu-id="f77cb-126">La dirección SIP del usuario o grupo de respuesta al que se enruta una llamada estacionada que no se responda cuando se supera el valor de <strong>MaxCallPickupAttempts</strong>.</span><span class="sxs-lookup"><span data-stu-id="f77cb-126">The SIP address of the user or response group to which an unanswered parked call is routed when <strong>MaxCallPickupAttempts</strong> is exceeded.</span></span></p>
<p><span data-ttu-id="f77cb-p105">El valor debe ser un URI de SIP que comience por sip:. Por ejemplo, sip:bob@contoso.com. El valor predeterminado corresponde a sin dirección de transferencia.</span><span class="sxs-lookup"><span data-stu-id="f77cb-p105">Value must be a SIP URI beginning with the string sip:. For example, sip:bob@contoso.com. The default is no forwarding address.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-call-park-settings"></a><span data-ttu-id="f77cb-130">Para configurar las opciones del estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="f77cb-130">To configure Call Park settings</span></span>

1.  <span data-ttu-id="f77cb-131">Inicie sesión en el equipo donde esté instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f77cb-131">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f77cb-132">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f77cb-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f77cb-133">Realizar</span><span class="sxs-lookup"><span data-stu-id="f77cb-133">Run:</span></span>
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="f77cb-134">Use el cmdlet <STRONG>Get-CsSite</STRONG> para identificar el sitio.</span><span class="sxs-lookup"><span data-stu-id="f77cb-134">Use the <STRONG>Get-CsSite</STRONG> cmdlet to identify the site.</span></span> <span data-ttu-id="f77cb-135">Para obtener información detallada, consulte Lync Server Management Shell Documentation.</span><span class="sxs-lookup"><span data-stu-id="f77cb-135">For details, see Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="f77cb-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f77cb-136">For example:</span></span>
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f77cb-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="f77cb-137">See Also</span></span>


[<span data-ttu-id="f77cb-138">Personalizar la música de estacionamiento de llamadas en espera en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f77cb-138">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)  


[<span data-ttu-id="f77cb-139">New-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="f77cb-139">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCpsConfiguration)  
[<span data-ttu-id="f77cb-140">Set-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="f77cb-140">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCpsConfiguration)  
[<span data-ttu-id="f77cb-141">Get-CsSite</span><span class="sxs-lookup"><span data-stu-id="f77cb-141">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

