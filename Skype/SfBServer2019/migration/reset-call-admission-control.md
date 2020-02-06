---
title: Restablecer el control de admisión de llamadas
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Si un grupo de servidores front-end heredado hospeda Call Admission Control (CAC), debe mover el alojamiento CAC a un grupo de servidores de Skype empresarial 2019 antes de poder quitar el grupo de aplicaciones para usuario heredado.
ms.openlocfilehash: cbc481e55d044ef196bd91dbfa8f7ebc796f28b5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812808"
---
# <a name="reset-call-admission-control"></a>Restablecer el control de admisión de llamadas

Si un grupo de servidores front-end heredado hospeda Call Admission Control (CAC), debe mover el alojamiento CAC a un grupo de servidores de Skype empresarial 2019 antes de poder quitar el grupo de aplicaciones para usuario heredado.
  
### <a name="to-reset-cac"></a>Para restablecer CAC

1. Abra el generador de topologías.
    
2. Haga clic con el botón secundario en el nodo del sitio y haga clic en **Editar propiedades**.
    
3. En **configuración de control de admisión de llamadas**, asegúrese de que **Habilitar control de admisión de llamadas** está seleccionado. 
    
4. En **grupo de servidores front-end para ejecutar el controlador de admisión de llamadas (CAC)**, seleccione el grupo de servidores de Skype empresarial 2019 que va a alojar CAC y, a continuación, haga clic en **Aceptar**.
    
5. Publique la topología.
    

