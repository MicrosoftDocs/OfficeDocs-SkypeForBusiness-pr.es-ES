---
title: Ver registros de uso de la RTC en Skype Empresarial 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Resumen: Obtenga información sobre cómo ver registros de uso de RTC mediante la Skype para el Panel de Control de servidor empresarial o el Skype para Shell de administración de servidor empresarial.'
ms.openlocfilehash: e4e58326fade20a48b032cf6cdc575894152fac0
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="view-pstn-usage-records-in-skype-for-business-2015"></a><span data-ttu-id="cf5c2-103">Ver registros de uso de la RTC en Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="cf5c2-103">View PSTN usage records in Skype for Business 2015</span></span>
 
<span data-ttu-id="cf5c2-104">**Resumen:** Obtenga información sobre cómo ver registros de uso de RTC mediante la Skype para el Panel de Control de servidor empresarial o el Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="cf5c2-104">**Summary:** Learn how to view PSTN usage records by using the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="cf5c2-105">Un registro de uso de una red de telefonía conmutada (RTC) especifica la clase de llamada (por ejemplo, interna, local o de larga distancia) que pueden realizar los diversos usuarios o grupos de usuarios en una organización.</span><span class="sxs-lookup"><span data-stu-id="cf5c2-105">A Public Switched Telephone Network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="cf5c2-106">Para obtener información detallada, vea [Registros de uso de RTC](http://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="cf5c2-106">For details, see [PSTN Usage Records](http://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in the Planning documentation.</span></span>
  
### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="cf5c2-107">Para ver un registro de uso de RTC mediante Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="cf5c2-107">To view a PSTN usage record by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="cf5c2-108">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="cf5c2-108">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="cf5c2-109">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Uso de RTC**.</span><span class="sxs-lookup"><span data-stu-id="cf5c2-109">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>
    
3. <span data-ttu-id="cf5c2-110">En la página **Uso de RTC**, resalte el registro de uso de RTC que desee ver, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="cf5c2-110">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="cf5c2-111">Una página de solo lectura del registro de uso de RTC seleccionado muestra las rutas y las directivas de voz asociadas.</span><span class="sxs-lookup"><span data-stu-id="cf5c2-111">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span> 
  
### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="cf5c2-112">Para ver la información de uso de RTC mediante el uso de Skype para los cmdlets del Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="cf5c2-112">To view PSTN usage information by using Skype for Business Server Management Shell cmdlets</span></span>

- <span data-ttu-id="cf5c2-113">Para ver información acerca de todos los usos de RTC, escriba el siguiente comando en el Skype para Shell de administración de servidor empresarial y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="cf5c2-113">To view information about all of your PSTN usages, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
  ```
  Get-CsPstnUsage
  ```

    <span data-ttu-id="cf5c2-114">Este comando devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="cf5c2-114">This command returns information similar to the following:</span></span>
    
  ```
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
  ```

## <a name="see-also"></a><span data-ttu-id="cf5c2-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf5c2-115">See also</span></span>

#### 

[<span data-ttu-id="cf5c2-116">Crear o modificar una directiva de voz y configurar registros de uso de RTC en Skype para profesionales de 2015</span><span class="sxs-lookup"><span data-stu-id="cf5c2-116">Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015</span></span>](voice-policy-and-pstn-usage-records.md)

