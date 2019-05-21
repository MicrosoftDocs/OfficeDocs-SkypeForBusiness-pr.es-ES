---
title: Restablecer el control de admisión de llamadas
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si un grupo de servidores front-end heredado hospeda Call Admission Control (CAC), debe mover el alojamiento CAC a un grupo de servidores de Skype empresarial 2019 antes de poder quitar el grupo de aplicaciones para usuario heredado.
ms.openlocfilehash: 7b4aa42b20bfad5506d47c16038d1765f3ac8571
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307101"
---
# <a name="reset-call-admission-control"></a>Restablecer el control de admisión de llamadas

Si un grupo de servidores front-end heredado hospeda Call Admission Control (CAC), debe mover el alojamiento CAC a un grupo de servidores de Skype empresarial 2019 antes de poder quitar el grupo de aplicaciones para usuario heredado.
  
### <a name="to-reset-cac"></a>Para restablecer CAC

1. Abra el generador de topologías.
    
2. Haga clic con el botón secundario en el nodo del sitio y haga clic en **Editar propiedades**.
    
3. En **configuración de control de admisión de llamadas**, asegúrese de que **Habilitar control de admisión de llamadas** está seleccionado. 
    
4. En **grupo de servidores front-end para ejecutar el controlador de admisión de llamadas (CAC)**, seleccione el grupo de servidores de Skype empresarial 2019 que va a alojar CAC y, a continuación, haga clic en **Aceptar**.
    
5. Publique la topología.
    

