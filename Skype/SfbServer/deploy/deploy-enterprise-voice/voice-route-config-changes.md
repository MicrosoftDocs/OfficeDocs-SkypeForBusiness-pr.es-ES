---
title: Publicar cambios pendientes en la configuración de enrutamiento de voz en Skype Empresarial
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
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 'Resumen: obtenga información sobre cómo revisar, publicar o cancelar los cambios de configuración de enrutamiento de voz en Skype Empresarial Server mediante el Panel de control Skype Empresarial Server voz.'
ms.openlocfilehash: 9c9cfd1cfdf1cf58f58cfcbf77abb54f9068609414a3b141b4fb643abcf4ac83
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54338698"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a>Publicar cambios pendientes en la configuración de enrutamiento de voz en Skype Empresarial
 
**Resumen:** Obtenga información sobre cómo revisar, publicar o cancelar los cambios de configuración de enrutamiento de voz en Skype Empresarial Server mediante el Panel de control Skype Empresarial Server voz.
  
Después de realizar algún cambio en cualquiera de las opciones de configuración de las páginas del grupo **Enrutamiento de voz**, siga este procedimiento para revisar, publicar o cancelar los cambios pendientes.
  
> [!IMPORTANT]
> Compruebe que solo modifica las opciones de configuración de Enrutamiento de voz un usuario cada vez. 
  
> [!NOTE]
> Todos los cambios pendientes deben publicarse al mismo tiempo, ejecutando el comando **Confirmar todo**. No se pueden publicar los cambios pendientes de forma selectiva. Antes de publicar los cambios pendientes, ejecute el comando **Revisar cambios sin confirmar** y cancele los cambios de configuración que no desee publicar.
  
> [!NOTE]
> Si sale de las páginas del grupo **Enrutamiento de voz** antes de confirmar los cambios pendientes, se perderán todos los cambios pendientes. Sin embargo, puede exportar la configuración actual (incluidos los cambios pendientes) a un archivo de configuración de voz y, a continuación, importar y publicar la configuración actualizada. Para obtener más información, [vea Exportar o importar un archivo de configuración](voice-route-configuration-import-export.md)de ruta de voz en Skype Empresarial . 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>Para revisar, publicar o cancelar cambios de configuración de enrutamiento de voz

1. Inicie sesión en el equipo como un miembro del grupo RTCUniversalServerAdmins o bien, como un miembro de la función administrativa **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.
    
2. Abra Skype Empresarial Server Panel de control.
    
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.
    
4. Realice los cambios de configuración que desee en las opciones de cada página del grupo **Enrutamiento de voz**.
    
5. Para revisar los cambios pendientes sin publicarlos, seleccione **Revisar cambios sin confirmar** en el menú **Confirmar**.
    
6. Si desea cancelar alguno de los cambios pendientes, realice una de las siguientes acciones:
    
   - Seleccione **Cancelar todos los cambios sin confirmar** en el menú **Confirmar**.
    
   - Navegue hasta la pestaña de la página de **Enrutamiento de voz** que tiene los cambios pendientes que desea cancelar, seleccione el elemento con cambios pendientes, haga clic en **Confirmar** y, a continuación, haga clic en **Cancelar cambios seleccionados**.
    
7. Después de revisar todos los cambios pendientes y cancelar los que no desee publicar, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    
8. En el cuadro de diálogo **Configuración de voz no confirmada**, que muestra una lista de todos los cambios pendientes, haga clic en **Aceptar**. 
    
    Cuando Skype Empresarial Server panel de control ha confirmado los cambios, aparece el **mensaje de** configuración de enrutamiento de voz publicado correctamente.
    

