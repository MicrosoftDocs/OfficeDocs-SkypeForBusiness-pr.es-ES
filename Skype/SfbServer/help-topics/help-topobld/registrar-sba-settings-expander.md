---
title: Expansor de configuración SBA de registrador
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 'Edite la configuración de resistencia y configure las siguientes propiedades:'
ms.openlocfilehash: 3fd2ea5a1ea2f0621a4df840a6e2af7581d39e9f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41696745"
---
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="40a38-103">Expansor de configuración SBA de registrador</span><span class="sxs-lookup"><span data-stu-id="40a38-103">Registrar SBA Settings Expander</span></span>

<span data-ttu-id="40a38-104">Edite la configuración de **resistencia** y configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="40a38-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>

- <span data-ttu-id="40a38-105">Seleccione **servicio de usuario asociado y grupo de registro** de la copia de seguridad en la lista.</span><span class="sxs-lookup"><span data-stu-id="40a38-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>

    <span data-ttu-id="40a38-106">De manera opcional, active la casilla **conmutación automática por error para voz** .</span><span class="sxs-lookup"><span data-stu-id="40a38-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>

    <span data-ttu-id="40a38-107">Configure el **intervalo de detección de errores de voz (s)** y el intervalo de conmutación por recuperación de **voz (s)**.</span><span class="sxs-lookup"><span data-stu-id="40a38-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="40a38-108">De forma predeterminada, los intervalos son de 120 segundos para la detección de errores de voz y de 240 segundos para la conmutación por voz.</span><span class="sxs-lookup"><span data-stu-id="40a38-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="40a38-109">El número de segundos que defina para los intervalos de conmutación por error y failback debe probarse detenidamente para asegurarse de que la resistencia funciona de la manera esperada.</span><span class="sxs-lookup"><span data-stu-id="40a38-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="40a38-110">Configurar el intervalo en Low (es decir, menos de 120 segundos) o el conjunto de conmutación por error y conmutación por recuperación demasiado estrecho puede dar lugar a que la conmutación por error y la conmutación de conmutación reales no funcionen de la manera esperada.</span><span class="sxs-lookup"><span data-stu-id="40a38-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span>

  <span data-ttu-id="40a38-111">**Aceptar.** Se aceptan y confirman los cambios en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="40a38-111">**OK** Accepts and commits changes to the dialog.</span></span>

  <span data-ttu-id="40a38-112">**Cancelar.** Se descartan los cambios y se cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="40a38-112">**Cancel** Discards changes and closes the dialog.</span></span>

  <span data-ttu-id="40a38-113">**Ayuda.** Abre esta pantalla de ayuda.</span><span class="sxs-lookup"><span data-stu-id="40a38-113">**Help** Displays this help screen.</span></span>

## <a name="see-also"></a><span data-ttu-id="40a38-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="40a38-114">See also</span></span>

[<span data-ttu-id="40a38-115">Planificación de resistencia de telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="40a38-115">Planning for Enterprise Voice Resiliency</span></span>](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
