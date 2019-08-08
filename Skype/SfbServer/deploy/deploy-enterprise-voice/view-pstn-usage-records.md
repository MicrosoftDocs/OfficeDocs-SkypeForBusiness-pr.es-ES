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
ms.openlocfilehash: bbc9b7f174ff4b6710009af47dbdcd20e12334d4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240003"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>Ver los registros de uso de RTC en Skype empresarial

**Resumen:** Obtenga información sobre cómo ver los registros de uso de RTC con el panel de control de Skype empresarial Server o el shell de administración de Skype empresarial Server.

Un registro de uso de una red de telefonía conmutada (RTC) especifica la clase de llamada (por ejemplo, interna, local o de larga distancia) que pueden realizar los diversos usuarios o grupos de usuarios en una organización. Para obtener más información, consulte [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) en la documentación de planeación.

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>Para ver un registro de uso de RTC con el panel de control de Skype empresarial Server

1. Abra el panel de control de Skype empresarial Server.

2. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Uso de RTC**.

3. En la página **Uso de RTC**, resalte el registro de uso de RTC que desee ver, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.

    > [!NOTE]
    > Una página de solo lectura del registro de uso de RTC seleccionado muestra las rutas y las directivas de voz asociadas.

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>Para ver la información de uso de RTC con los cmdlets del shell de administración de Skype empresarial Server

- Para ver información sobre todos los usos de RTC, escriba el siguiente comando en el shell de administración de Skype empresarial Server y, a continuación, presione ENTRAR:

  ```
  Get-CsPstnUsage
  ```

    Este comando devolverá información similar a la siguiente:

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>Vea también

[Crear o modificar una directiva de voz y configurar los registros de uso de RTC en Skype empresarial](voice-policy-and-pstn-usage-records.md)

