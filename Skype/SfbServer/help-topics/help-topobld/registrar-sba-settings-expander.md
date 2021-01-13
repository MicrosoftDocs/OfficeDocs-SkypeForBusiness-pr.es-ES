---
title: Expansor de configuración SBA de registrador
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 'Modifique la configuración de la Resistencia y configure las siguientes propiedades:'
ms.openlocfilehash: e85bc8fd1ff3beb745fa494db6e77b5ca6d407a5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823580"
---
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="e69bd-103">Expansor de configuración SBA de registrador</span><span class="sxs-lookup"><span data-stu-id="e69bd-103">Registrar SBA Settings Expander</span></span>

<span data-ttu-id="e69bd-104">Modifique la configuración de la **Resistencia** y configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="e69bd-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>

- <span data-ttu-id="e69bd-105">Seleccione **Servicio de usuario asociado y grupo de registrador de reserva** en la lista.</span><span class="sxs-lookup"><span data-stu-id="e69bd-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>

    <span data-ttu-id="e69bd-106">Opcionalmente, puede activar la casilla **Conmutación por error y conmutación por recuperación automática para voz**.</span><span class="sxs-lookup"><span data-stu-id="e69bd-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>

    <span data-ttu-id="e69bd-p101">Configure el **Intervalo de detección de errores de voz (s)** y el **Intervalo de conmutación por recuperación de voz (s)**. De forma predeterminada, los intervalos son de 120 segundos para la detección de errores de voz y de 240 segundos para la conmutación por recuperación de voz.</span><span class="sxs-lookup"><span data-stu-id="e69bd-p101">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**. By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="e69bd-p102">El número de segundos que se definen para los intervalos de conmutación por error y de conmutación por recuperación deben probarse detenidamente para garantizar que la resistencia funciona según lo previsto. Si se define el intervalo como bajo (es decir, inferior a 120 segundos) o la conmutación por error y la conmutación por recuperación se definen demasiado próximas, puede resultar en que la conmutación por error y la conmutación por recuperación reales no funcionen correctamente.</span><span class="sxs-lookup"><span data-stu-id="e69bd-p102">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected. Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span>

  <span data-ttu-id="e69bd-111">**Aceptar** Acepta y confirma los cambios realizados en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e69bd-111">**OK** Accepts and commits changes to the dialog.</span></span>

  <span data-ttu-id="e69bd-112">**Cancelar** Descarta los cambios y cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e69bd-112">**Cancel** Discards changes and closes the dialog.</span></span>

  <span data-ttu-id="e69bd-113">**Ayuda** Muestra la ayuda de esta pantalla.</span><span class="sxs-lookup"><span data-stu-id="e69bd-113">**Help** Displays this help screen.</span></span>

## <a name="see-also"></a><span data-ttu-id="e69bd-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e69bd-114">See also</span></span>

[<span data-ttu-id="e69bd-115">Planeación de la resistencia de Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="e69bd-115">Planning for Enterprise Voice Resiliency</span></span>](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
