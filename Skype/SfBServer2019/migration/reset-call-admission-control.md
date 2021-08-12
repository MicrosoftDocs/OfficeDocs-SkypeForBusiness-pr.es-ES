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
description: Si un grupo de servidores front-end heredado hospeda el control de admisión de llamadas (CAC), debe mover el hospedaje de CAC a un grupo de servidores de Skype Empresarial Server 2019 antes de poder quitar el grupo de servidores front-end heredado.
ms.openlocfilehash: c3ebb748d877e88060b699b1599c39038124565df361c5032533260e4c5643e2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54334572"
---
# <a name="reset-call-admission-control"></a>Restablecer el control de admisión de llamadas

Si un grupo de servidores front-end heredado hospeda el control de admisión de llamadas (CAC), debe mover el hospedaje de CAC a un grupo de servidores de Skype Empresarial Server 2019 antes de poder quitar el grupo de servidores front-end heredado.
  
### <a name="to-reset-cac"></a>Para restablecer el CAC

1. Abra el Generador de topologías.
    
2. Haga clic con el botón secundario en el nodo del sitio y luego haga clic en **Editar propiedades**.
    
3. En el parámetro **Control de admisión de llamadas**, asegúrese de que **Habilitar control de admisión de llamadas** esté activado. 
    
4. En **Grupo de servidores front-end** para ejecutar el control de admisión de llamadas (CAC), seleccione el grupo de servidores de Skype Empresarial Server 2019 que va a hospedar cac y, a continuación, haga clic en **Aceptar**.
    
5. Publique la topología.
    

