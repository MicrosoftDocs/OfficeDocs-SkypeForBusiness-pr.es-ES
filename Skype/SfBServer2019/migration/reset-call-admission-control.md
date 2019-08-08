---
title: Restablecer el control de admisión de llamadas
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si un grupo de servidores front-end heredado hospeda Call Admission Control (CAC), debe mover el alojamiento CAC a un grupo de servidores de Skype empresarial 2019 antes de poder quitar el grupo de aplicaciones para usuario heredado.
ms.openlocfilehash: 812391eda436906020c41b14a53c8ea18c4b1aee
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241328"
---
# <a name="reset-call-admission-control"></a>Restablecer el control de admisión de llamadas

Si un grupo de servidores front-end heredado hospeda Call Admission Control (CAC), debe mover el alojamiento CAC a un grupo de servidores de Skype empresarial 2019 antes de poder quitar el grupo de aplicaciones para usuario heredado.
  
### <a name="to-reset-cac"></a>Para restablecer CAC

1. Abra el generador de topologías.
    
2. Haga clic con el botón secundario en el nodo del sitio y haga clic en **Editar propiedades**.
    
3. En **configuración de control de admisión de llamadas**, asegúrese de que **Habilitar control de admisión de llamadas** está seleccionado. 
    
4. En **grupo de servidores front-end para ejecutar el controlador de admisión de llamadas (CAC)**, seleccione el grupo de servidores de Skype empresarial 2019 que va a alojar CAC y, a continuación, haga clic en **Aceptar**.
    
5. Publique la topología.
    

