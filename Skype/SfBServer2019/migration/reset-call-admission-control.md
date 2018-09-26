---
title: Restablecer el control de admisión de llamadas
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si un grupo de servidores Front-End heredado hospeda el control de admisión de llamadas (CAC), debe mover CAC que hospeda a un Skype para Business Server 2019 grupo para poder quitar el grupo de servidores Front-End heredado.
ms.openlocfilehash: 65d56d000c5bcec5f7aae73413c287dee8ab29ca
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027322"
---
# <a name="reset-call-admission-control"></a>Restablecer el control de admisión de llamadas

Si un grupo de servidores Front-End heredado hospeda el control de admisión de llamadas (CAC), debe mover CAC que hospeda a un Skype para Business Server 2019 grupo para poder quitar el grupo de servidores Front-End heredado.
  
### <a name="to-reset-cac"></a>Para restablecer el CAC

1. Abra el generador de topología.
    
2. Haga clic en el nodo del sitio y, a continuación, haga clic en **Editar propiedades**.
    
3. En el cuadro **configuración de Control de admisión de llamadas**, asegúrese de que **Habilitar el Control de admisión de llamadas** está seleccionada. 
    
4. En el **grupo de servidores Front-End para ejecutar el control de admisión de llamadas (CAC)**, seleccione el Skype para Business Server 2019 del grupo que va a alojar el CAC y, a continuación, haga clic en **Aceptar**.
    
5. Publique la topología.
    

