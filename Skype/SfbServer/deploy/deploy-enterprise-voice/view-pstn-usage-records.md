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
# <a name="view-pstn-usage-records-in-skype-for-business"></a>Ver registros de uso de RTC en Skype Empresarial

**Resumen:** Obtenga información sobre cómo ver los registros de uso de RTC mediante el Panel de control de Skype Empresarial Server o el Shell de administración de Skype Empresarial Server.

Un registro de uso de la red telefónica conmutada (RTC) especifica una clase de llamada (como interna, local o de larga distancia) que pueden realizar varios usuarios o grupos de usuarios de una organización. Para obtener más información, consulte [Registros de uso de RTC](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) en la documentación de planeación.

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>Para ver un registro de uso de RTC mediante el Panel de control de Skype Empresarial Server

1. Abra el Panel de control de Skype Empresarial Server.

2. En la barra de navegación izquierda, haga clic en **Enrutamiento de** voz y, a continuación, haga clic en Uso **de RTC.**

3. En la **página Uso de** RTC, resalte el  registro de uso de RTC que desea ver, haga clic en Editar y, a continuación, haga clic en **Mostrar detalles.**

    > [!NOTE]
    > Una página de solo lectura del registro de uso de RTC seleccionado muestra las rutas asociadas y las directivas de voz asociadas.

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>Para ver la información de uso de RTC mediante cmdlets del Shell de administración de Skype Empresarial Server

- Para ver información sobre todos los usos de RTC, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:

  ```powershell
  Get-CsPstnUsage
  ```

    Este comando devolverá información similar a la siguiente:

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>Vea también

[Crear o modificar una directiva de voz y configurar registros de uso de RTC en Skype Empresarial](voice-policy-and-pstn-usage-records.md)

