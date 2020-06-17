---
title: Restablecer el control de admisión de llamadas
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Si un grupo de servidores front-end heredado hospeda el control de admisión de llamadas (CAC), debe mover el hospedaje de CAC a un grupo de servidores de Skype empresarial Server 2019 antes de poder quitar el grupo de servidores front-end heredado.
ms.openlocfilehash: 850ab5c13483d024d52c483c63ef09468f8374b3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753302"
---
# <a name="reset-call-admission-control"></a>Restablecer el control de admisión de llamadas

Si un grupo de servidores front-end heredado hospeda el control de admisión de llamadas (CAC), debe mover el hospedaje de CAC a un grupo de servidores de Skype empresarial Server 2019 antes de poder quitar el grupo de servidores front-end heredado.
  
### <a name="to-reset-cac"></a>Para restablecer el CAC

1. Abra el Generador de topologías.
    
2. Haga clic con el botón secundario en el nodo del sitio y luego haga clic en **Editar propiedades**.
    
3. En el parámetro **Control de admisión de llamadas**, asegúrese de que **Habilitar control de admisión de llamadas** esté activado. 
    
4. En **grupo de servidores front-end para ejecutar el control de admisión de llamadas (CAC)**, seleccione el grupo de servidores de Skype empresarial Server 2019 que va a hospedar el CAC y, a continuación, haga clic en **Aceptar**.
    
5. Publique la topología.
    

