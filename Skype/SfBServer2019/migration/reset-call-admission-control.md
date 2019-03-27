---
title: Restablecer el control de admisión de llamadas
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si un grupo de servidores Front-End heredado hospeda el control de admisión de llamadas (CAC), debe mover CAC que hospeda a un Skype para Business Server 2019 grupo para poder quitar el grupo de servidores Front-End heredado.
ms.openlocfilehash: 3b94322b86feb2c647f88102617ab1dcc9d5f8bc
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895778"
---
# <a name="reset-call-admission-control"></a>Restablecer el control de admisión de llamadas

Si un grupo de servidores Front-End heredado hospeda el control de admisión de llamadas (CAC), debe mover CAC que hospeda a un Skype para Business Server 2019 grupo para poder quitar el grupo de servidores Front-End heredado.
  
### <a name="to-reset-cac"></a>Para restablecer el CAC

1. Abra el generador de topología.
    
2. Haga clic en el nodo del sitio y, a continuación, haga clic en **Editar propiedades**.
    
3. En el cuadro **configuración de Control de admisión de llamadas**, asegúrese de que **Habilitar el Control de admisión de llamadas** está seleccionada. 
    
4. En el **grupo de servidores Front-End para ejecutar el control de admisión de llamadas (CAC)**, seleccione el Skype para Business Server 2019 del grupo que va a alojar el CAC y, a continuación, haga clic en **Aceptar**.
    
5. Publique la topología.
    

