---
title: Configurar la configuración de estacionamiento de llamadas en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Modificar la configuración de la llamada en el parque en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: 5ce9d15c4d233e620c5eb12c18688b5df958defb
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001370"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a><span data-ttu-id="d9aa6-103">Configurar la configuración de estacionamiento de llamadas en Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="d9aa6-103">Configure Call Park settings in Skype for Business</span></span>

<span data-ttu-id="d9aa6-104">Modificar la configuración de la llamada en el parque en Skype empresarial Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="d9aa6-104">Modify Call Park settings in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="d9aa6-105">Si no desea usar la configuración de Parque de llamadas predeterminada, puede personalizarla.</span><span class="sxs-lookup"><span data-stu-id="d9aa6-105">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="d9aa6-106">Al instalar la aplicación de estacionamiento de llamadas, la configuración global se configura de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d9aa6-106">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="d9aa6-107">Puede modificar esta configuración global y, además, puede especificar opciones de configuración específicas del sitio.</span><span class="sxs-lookup"><span data-stu-id="d9aa6-107">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="d9aa6-108">Use el cmdlet **New-CsCpsConfiguration** para crear una nueva configuración específica del sitio.</span><span class="sxs-lookup"><span data-stu-id="d9aa6-108">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="d9aa6-109">Use cmdlet **Set-CsCpsConfiguration** para modificar la configuración existente.</span><span class="sxs-lookup"><span data-stu-id="d9aa6-109">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>

> [!NOTE]
> <span data-ttu-id="d9aa6-110">Como mínimo, se recomienda configurar la opción **OnTimeoutURI** para el destino de reserva que se usará cuando el tiempo de espera de una llamada estacionada se agote y deje de sonar.</span><span class="sxs-lookup"><span data-stu-id="d9aa6-110">At a minimum, we recommend that you configure the **OnTimeoutURI** option for the fallback destination to use when a parked call times out and ringback fails.</span></span>

<span data-ttu-id="d9aa6-111">Use el cmdlet **New-CsCpsConfiguration** o el cmdlet **Set-CsCpsConfiguration** para configurar cualquiera de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="d9aa6-111">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>


| <span data-ttu-id="d9aa6-112">**Esta opción:**</span><span class="sxs-lookup"><span data-stu-id="d9aa6-112">**This option:**</span></span>                     | <span data-ttu-id="d9aa6-113">**Especifica:**</span><span class="sxs-lookup"><span data-stu-id="d9aa6-113">**Specifies this:**</span></span>                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="d9aa6-114">**CallPickupTimeoutThreshold**</span><span class="sxs-lookup"><span data-stu-id="d9aa6-114">**CallPickupTimeoutThreshold**</span></span> <br/> | <span data-ttu-id="d9aa6-115">El tiempo que transcurre después de estacionar la llamada hasta que vuelve a sonar en el teléfono en el que se respondió.</span><span class="sxs-lookup"><span data-stu-id="d9aa6-115">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span>  <br/> <span data-ttu-id="d9aa6-p102">El valor debe introducirse con el formato hh:mm:ss para especificar las horas, los minutos y los segundos. El valor mínimo es 10 segundos y el máximo, 10 minutos. El valor predeterminado es 00:01:30.</span><span class="sxs-lookup"><span data-stu-id="d9aa6-p102">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds. The minimum value is 10 seconds, and the maximum value is 10 minutes. The default is 00:01:30.</span></span>  <br/> |
| <span data-ttu-id="d9aa6-119">**EnableMusicOnHold**</span><span class="sxs-lookup"><span data-stu-id="d9aa6-119">**EnableMusicOnHold**</span></span> <br/>          | <span data-ttu-id="d9aa6-120">Si la persona que llama escuchará música mientras la llamada está estacionada.</span><span class="sxs-lookup"><span data-stu-id="d9aa6-120">Whether music plays for a caller while a call is parked.</span></span>  <br/> <span data-ttu-id="d9aa6-p103">Los valores son True o False. El valor predeterminado es True.</span><span class="sxs-lookup"><span data-stu-id="d9aa6-p103">Values are True or False. The default is True.</span></span>  <br/>                                                                                                                                                                                                                 |
| <span data-ttu-id="d9aa6-123">**MaxCallPickupAttempts**</span><span class="sxs-lookup"><span data-stu-id="d9aa6-123">**MaxCallPickupAttempts**</span></span> <br/>      | <span data-ttu-id="d9aa6-p104">El número de veces que una llamada estacionada vuelve a sonar en el teléfono en que se respondió antes de transferirla al identificador uniforme de recursos (URI) de reserva que se especifique para **OnTimeoutURI**. El valor predeterminado es 1.</span><span class="sxs-lookup"><span data-stu-id="d9aa6-p104">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for **OnTimeoutURI**. The default is 1.  </span></span><br/>                                                                                                                         |
| <span data-ttu-id="d9aa6-126">**OnTimeoutURI**</span><span class="sxs-lookup"><span data-stu-id="d9aa6-126">**OnTimeoutURI**</span></span> <br/>               | <span data-ttu-id="d9aa6-127">La dirección SIP del usuario o grupo de respuesta al que se enruta una llamada estacionada que no se responda cuando se supera el valor de **MaxCallPickupAttempts**.</span><span class="sxs-lookup"><span data-stu-id="d9aa6-127">The SIP address of the user or response group to which an unanswered parked call is routed when **MaxCallPickupAttempts** is exceeded.</span></span> <br/> <span data-ttu-id="d9aa6-p105">El valor debe ser un URI de SIP que comience por sip:. Por ejemplo, sip:bob@contoso.com. El valor predeterminado corresponde a sin dirección de transferencia.</span><span class="sxs-lookup"><span data-stu-id="d9aa6-p105">Value must be a SIP URI beginning with the string sip:. For example, sip:bob@contoso.com. The default is no forwarding address.  </span></span><br/>                                                   |

### <a name="to-configure-call-park-settings"></a><span data-ttu-id="d9aa6-131">Para configurar la configuración del parque de llamadas</span><span class="sxs-lookup"><span data-stu-id="d9aa6-131">To configure Call Park settings</span></span>

1. <span data-ttu-id="d9aa6-132">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="d9aa6-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="d9aa6-133">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="d9aa6-133">Run:</span></span>

   ```powershell
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > <span data-ttu-id="d9aa6-134">Use el cmdlet **Get-CsSite** para identificar el sitio.</span><span class="sxs-lookup"><span data-stu-id="d9aa6-134">Use the **Get-CsSite** cmdlet to identify the site.</span></span> <span data-ttu-id="d9aa6-135">Para obtener más información, consulte la documentación del shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d9aa6-135">For details, see Skype for Business Server Management Shell documentation.</span></span>

    <span data-ttu-id="d9aa6-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d9aa6-136">For example:</span></span>

   ```powershell
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a><span data-ttu-id="d9aa6-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9aa6-137">See also</span></span>

[<span data-ttu-id="d9aa6-138">Personalizar la música de espera para el estacionamiento de llamadas en Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="d9aa6-138">Customize Call Park music on hold inSkype for Business 2015</span></span>](customize-call-park-music-on-hold.md)

[<span data-ttu-id="d9aa6-139">Nuevo: CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="d9aa6-139">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[<span data-ttu-id="d9aa6-140">Set-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="d9aa6-140">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[<span data-ttu-id="d9aa6-141">Get-CsSite</span><span class="sxs-lookup"><span data-stu-id="d9aa6-141">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)
