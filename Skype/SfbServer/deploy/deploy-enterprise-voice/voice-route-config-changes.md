---
title: Publicar los cambios pendientes en la configuración del enrutamiento de voz en Skype Empresarial 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 'Resumen: Conozca cómo revisar, publicar o cancelar los cambios de configuración enrutamiento de voz de Skype para Business Server 2015 utilizando el Skype para el Panel de Control de servidor empresarial.'
ms.openlocfilehash: 4ad92cce54da403674e5da25052fd55681fd0627
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business-2015"></a>Publicar los cambios pendientes en la configuración del enrutamiento de voz en Skype Empresarial 2015
 
**Resumen:** Aprenda a revisar, publicar o cancelar los cambios de configuración enrutamiento de voz de Skype para Business Server 2015 utilizando el Skype para el Panel de Control de servidor empresarial.
  
Después de realizar cambios en cualquiera de las opciones de configuración de las páginas del grupo **Enrutamiento de voz**, siga este procedimiento para revisar, publicar o cancelar los cambios pendientes.
  
> [!IMPORTANT]
> Compruebe que solo modifica las opciones de configuración de Enrutamiento de voz un usuario cada vez. 
  
> [!NOTE]
> Todos los cambios pendientes deben publicarse al mismo tiempo, ejecutando el comando **Confirmar todo**. No se pueden publicar los cambios pendientes de forma selectiva. Antes de publicar los cambios pendientes, ejecute el comando **Revisar cambios sin confirmar** y cancele los cambios de configuración que no desee publicar.
  
> [!NOTE]
> Si sale de las páginas del grupo **Enrutamiento de voz** de confirmar los cambios pendientes, se perderán todos los cambios pendientes. No obstante, puede exportar la configuración actual (incluidos los cambios pendientes) a un archivo de configuración de voz y, a continuación, importar y publicar la configuración actualizada. Para obtener más información, vea [exportar o importar un archivo de configuración de ruta de voz de Skype para negocios 2015](voice-route-configuration-import-export.md). 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>Para revisar, publicar o cancelar cambios de configuración de enrutamiento de voz

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.
    
2. Abre Skype para Panel de Control del servidor de empresa.
    
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.
    
4. Realice los cambios de configuración que desee en las opciones de cada página del grupo **Enrutamiento de voz**.
    
5. Para revisar los cambios pendientes sin publicarlos, seleccione **Revisar cambios sin confirmar** en el menú **Confirmar**.
    
6. Si desea cancelar alguno de los cambios pendientes, realice una de las siguientes acciones:
    
   - Seleccione **Cancelar todos los cambios sin confirmar** en el menú **Confirmar**.
    
   - Navegue hasta la pestaña de la página de **Enrutamiento de voz** que tiene los cambios pendientes que desea cancelar, seleccione el elemento con cambios pendientes, haga clic en **Confirmar** y, a continuación, haga clic en **Cancelar cambios seleccionados**.
    
7. Después de revisar todos los cambios pendientes y cancelar los que no desee publicar, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    
8. En el cuadro de diálogo **Configuración de voz no confirmada**, que muestra una lista de todos los cambios pendientes, haga clic en **Aceptar**. 
    
    Cuando Skype para Panel de Control de servidor de empresa ha comprometido los cambios, aparecerá el mensaje **publicado correctamente la configuración de enrutamiento de voz** .
    

