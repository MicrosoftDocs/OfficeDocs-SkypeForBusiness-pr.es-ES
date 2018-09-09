---
title: Exportar o importar un archivo de configuración de ruta de voz de Skype para la empresa
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Resumen: Obtenga información sobre cómo exportar o importar un archivo de configuración de enrutamiento de voz de Skype para Business Server mediante el uso de la Skype para el Panel de Control de servidor empresarial.'
ms.openlocfilehash: 5cf9021a1cc18daf90fc719723962959142ad92e
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886792"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>Exportar o importar un archivo de configuración de ruta de voz de Skype para la empresa
 
**Resumen:** Obtenga información sobre cómo exportar o importar un archivo de configuración de enrutamiento de voz de Skype para Business Server mediante el uso de la Skype para el Panel de Control de servidor empresarial.
  
Si desea guardar la configuración del enrutamiento de voz sin publicarla, siga los pasos de este tema para guardar y recuperar una instantánea de la configuración del enrutamiento de voz. 
  
Al importar un archivo de configuración enrutamiento de voz (.vcfg), pero los cambios se han realizado la voz configuración de enrutamiento en el servidor mientras tanto, las páginas en el grupo de **Enrutamiento de voz** de Skype para el Panel de Control de servidor empresarial que le indicará no existe son los cambios no confirmados en enrutamiento de voz. Estos cambios no confirmados son las diferencias entre las dos configuraciones que requieren reconciliación.
  
Si ha realizado los cambios no confirmados en la configuración de cualquier página dentro del grupo, los cambios se guardan en el archivo de configuración de voz exportado (.vcfg). Esto le permite realizar cambios en la configuración de enrutamiento durante varias sesiones antes de publicar los cambios de voz. 
  
### <a name="to-export-a-voice-routing-configuration"></a>Para exportar una configuración de enrutamiento de voz

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.
    
2. Abra Skype para el Panel de Control de servidor empresarial.
    
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.
    
4. En el menú **Acciones**, haga clic en **Exportar configuración**.
    
5. Especifique una ubicación y un nombre de archivo y, a continuación, haga clic en **Guardar**.
    
### <a name="to-import-a-voice-routing-configuration"></a>Para importar una configuración de enrutamiento de voz

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.
    
2. Abra Skype para el Panel de Control de servidor empresarial.
    
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.
    
4. En el menú **Acciones**, haga clic en **Importar configuración**.
    
5. Busque el archivo de configuración que desee importar y, a continuación, haga clic en **Abrir**.
    
6. Haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    
    > [!NOTE]
    > Siempre que importe un archivo de configuración de voz, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, consulte [Publicar cambios pendientes en la configuración de enrutamiento de voz de Skype para la empresa](voice-route-config-changes.md) en la documentación sobre operaciones.
  

