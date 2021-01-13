---
title: Ver registros de uso de RTC en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Resumen: obtenga información sobre cómo ver los registros de uso de RTC mediante el Panel de control de Skype Empresarial Server o el Shell de administración de Skype Empresarial Server.'
ms.openlocfilehash: abf9f3ec9ce1e2801de2c6017d12fd64df0c8954
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830540"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="81226-103">Ver registros de uso de RTC en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="81226-103">View PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="81226-104">**Resumen:** Obtenga información sobre cómo ver los registros de uso de RTC mediante el Panel de control de Skype Empresarial Server o el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="81226-104">**Summary:** Learn how to view PSTN usage records by using the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="81226-105">Un registro de uso de la red telefónica conmutada (RTC) especifica una clase de llamada (como interna, local o de larga distancia) que pueden realizar varios usuarios o grupos de usuarios de una organización.</span><span class="sxs-lookup"><span data-stu-id="81226-105">A Public Switched Telephone Network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="81226-106">Para obtener más información, consulte [Registros de uso de RTC](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="81226-106">For details, see [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in the Planning documentation.</span></span>

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="81226-107">Para ver un registro de uso de RTC mediante el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="81226-107">To view a PSTN usage record by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="81226-108">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="81226-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="81226-109">En la barra de navegación izquierda, haga clic en **Enrutamiento de** voz y, a continuación, haga clic en Uso **de RTC.**</span><span class="sxs-lookup"><span data-stu-id="81226-109">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

3. <span data-ttu-id="81226-110">En la **página Uso de** RTC, resalte el  registro de uso de RTC que desea ver, haga clic en Editar y, a continuación, haga clic en **Mostrar detalles.**</span><span class="sxs-lookup"><span data-stu-id="81226-110">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="81226-111">Una página de solo lectura del registro de uso de RTC seleccionado muestra las rutas asociadas y las directivas de voz asociadas.</span><span class="sxs-lookup"><span data-stu-id="81226-111">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="81226-112">Para ver la información de uso de RTC mediante cmdlets del Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="81226-112">To view PSTN usage information by using Skype for Business Server Management Shell cmdlets</span></span>

- <span data-ttu-id="81226-113">Para ver información sobre todos los usos de RTC, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="81226-113">To view information about all of your PSTN usages, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

  ```powershell
  Get-CsPstnUsage
  ```

    <span data-ttu-id="81226-114">Este comando devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="81226-114">This command returns information similar to the following:</span></span>

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a><span data-ttu-id="81226-115">Ver también</span><span class="sxs-lookup"><span data-stu-id="81226-115">See also</span></span>

[<span data-ttu-id="81226-116">Crear o modificar una directiva de voz y configurar registros de uso de RTC en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="81226-116">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

