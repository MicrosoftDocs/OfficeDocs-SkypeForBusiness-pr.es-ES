---
title: Ver los registros de uso de RTC en Skype empresarial
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
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Resumen: Aprenda a ver los registros de uso de RTC con el panel de control de Skype empresarial Server o el shell de administración de Skype empresarial Server.'
ms.openlocfilehash: 96a96898bf728b4f05ba473bc750635e41be19fa
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002730"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="d3f11-103">Ver los registros de uso de RTC en Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="d3f11-103">View PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="d3f11-104">**Resumen:** Obtenga información sobre cómo ver los registros de uso de RTC con el panel de control de Skype empresarial Server o el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d3f11-104">**Summary:** Learn how to view PSTN usage records by using the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="d3f11-p101">Un registro de uso de una red de telefonía conmutada (RTC) especifica la clase de llamada (por ejemplo, interna, local o de larga distancia) que pueden realizar los diversos usuarios o grupos de usuarios en una organización. Para obtener más información, consulte [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="d3f11-p101">A Public Switched Telephone Network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization. For details, see [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in the Planning documentation.</span></span>

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d3f11-107">Para ver un registro de uso de RTC con el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d3f11-107">To view a PSTN usage record by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d3f11-108">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d3f11-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="d3f11-109">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Uso de RTC**.</span><span class="sxs-lookup"><span data-stu-id="d3f11-109">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

3. <span data-ttu-id="d3f11-110">En la página **Uso de RTC**, resalte el registro de uso de RTC que desee ver, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="d3f11-110">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d3f11-111">Una página de solo lectura del registro de uso de RTC seleccionado muestra las rutas y las directivas de voz asociadas.</span><span class="sxs-lookup"><span data-stu-id="d3f11-111">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="d3f11-112">Para ver la información de uso de RTC con los cmdlets del shell de administración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d3f11-112">To view PSTN usage information by using Skype for Business Server Management Shell cmdlets</span></span>

- <span data-ttu-id="d3f11-113">Para ver información sobre todos los usos de RTC, escriba el siguiente comando en el shell de administración de Skype empresarial Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="d3f11-113">To view information about all of your PSTN usages, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

  ```powershell
  Get-CsPstnUsage
  ```

    <span data-ttu-id="d3f11-114">Este comando devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="d3f11-114">This command returns information similar to the following:</span></span>

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a><span data-ttu-id="d3f11-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3f11-115">See also</span></span>

[<span data-ttu-id="d3f11-116">Crear o modificar una directiva de voz y configurar los registros de uso de RTC en Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="d3f11-116">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

