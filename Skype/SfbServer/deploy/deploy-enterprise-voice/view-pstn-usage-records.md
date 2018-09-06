---
title: Ver registros de uso de RTC de Skype para la empresa
ms.author: crowe
author: CarolynRowe
manager: serdars
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
ms.openlocfilehash: 7e0cf091c1fd6afbfde6fc4a35ba049e75deaf4f
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23250269"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>Ver registros de uso de RTC de Skype para la empresa

**Resumen:** Obtenga información sobre cómo ver registros de uso de RTC mediante la Skype para el Panel de Control de servidor empresarial o el Skype para Shell de administración de servidor empresarial.

Un registro de uso de una red de telefonía conmutada (RTC) especifica la clase de llamada (por ejemplo, interna, local o de larga distancia) que pueden realizar los diversos usuarios o grupos de usuarios en una organización. Para obtener información detallada, vea [Registros de uso de RTC](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) en la documentación de planeación.

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>Para ver un registro de uso de RTC mediante Skype para el Panel de Control de servidor empresarial

1. Abra Skype para el Panel de Control de servidor empresarial.

2. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Uso de RTC**.

3. En la página **Uso de RTC**, resalte el registro de uso de RTC que desee ver, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.

    > [!NOTE]
    > Una página de solo lectura del registro de uso de RTC seleccionado muestra las rutas y las directivas de voz asociadas.

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>Para ver la información de uso de RTC mediante el uso de Skype para los cmdlets del Shell de administración de servidor empresarial

- Para ver información acerca de todos los usos de RTC, escriba el siguiente comando en el Skype para Shell de administración de servidor empresarial y, a continuación, presione ENTRAR:

  ```
  Get-CsPstnUsage
  ```

    Este comando devolverá información similar a la siguiente:

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>Vea también

[Crear o modificar una directiva de voz y configurar registros de uso de RTC en Skype para la empresa](voice-policy-and-pstn-usage-records.md)

