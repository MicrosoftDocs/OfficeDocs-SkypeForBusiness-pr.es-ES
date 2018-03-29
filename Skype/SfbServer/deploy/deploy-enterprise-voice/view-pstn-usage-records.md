---
title: Ver registros de uso de la RTC en Skype Empresarial 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Resumen: Conozca cómo ver los registros de uso PSTN mediante el Skype para Business Server Control Panel o el Skype para el Shell de administración de servidor empresarial.'
ms.openlocfilehash: 63e35879f9530d56ef770584de45a169c20ea057
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="view-pstn-usage-records-in-skype-for-business-2015"></a>Ver registros de uso de la RTC en Skype Empresarial 2015
 
**Resumen:** Obtenga información sobre cómo ver los registros de uso PSTN mediante el Skype para Business Server Control Panel o el Skype para el Shell de administración de servidor empresarial.
  
Un registro de uso de una red de telefonía conmutada (RTC) especifica la clase de llamada (por ejemplo, interna, local o de larga distancia) que pueden realizar los diversos usuarios o grupos de usuarios en una organización. Para obtener más información, vea [Registros de uso de RTC](http://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) en la documentación de planificación.
  
### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>Para ver un registro de uso PSTN mediante Skype para Panel de Control de servidor empresarial

1. Abre Skype para Panel de Control del servidor de empresa.
    
2. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Uso de RTC**.
    
3. En la página **Uso de RTC**, resalte el registro de uso de RTC que desee ver, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**. 
    
    > [!NOTE]
    > Una página de solo lectura del registro de uso de RTC seleccionado muestra las rutas y las directivas de voz asociadas. 
  
### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>Para ver la información de uso PSTN mediante Skype para los cmdlets del Shell de administración de servidor de Business

- Para ver información acerca de todos los usos del PSTN, escriba el comando siguiente en el Skype para el Shell de administración de servidor de Business y, a continuación, presione ENTRAR:
    
  ```
  Get-CsPstnUsage
  ```

    Este comando devolverá información similar a la siguiente:
    
  ```
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
  ```

## <a name="see-also"></a>Vea también

#### 

[Crear o modificar una directiva de voz y configurar registros de uso PSTN en Skype para negocios 2015](voice-policy-and-pstn-usage-records.md)

