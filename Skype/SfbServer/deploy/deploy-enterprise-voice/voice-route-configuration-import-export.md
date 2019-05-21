---
title: Exportar o importar un archivo de configuración de la ruta de voz en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Resumen: Aprenda a exportar o importar un archivo de configuración de enrutamiento de voz en Skype empresarial Server mediante el panel de control de Skype empresarial Server.'
ms.openlocfilehash: 14637694e5604419fcd344b43af98263588f117a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300883"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>Exportar o importar un archivo de configuración de la ruta de voz en Skype empresarial
 
**Resumen:** Obtenga información sobre cómo exportar o importar un archivo de configuración de enrutamiento de voz en Skype empresarial Server mediante el panel de control de Skype empresarial Server.
  
Si desea guardar la configuración del enrutamiento de voz sin publicarla, siga los pasos de este tema para guardar y recuperar una instantánea de la configuración del enrutamiento de voz. 
  
Al importar un archivo de configuración de enrutamiento de voz (. vcfg), pero se han realizado cambios en la configuración de enrutamiento de voz en el servidor mientras tanto, las páginas del grupo de **enrutamiento de voz** en el panel de control de Skype empresarial Server indicarán que son cambios no confirmados en el enrutamiento de voz. Estos cambios no confirmados son las diferencias entre las dos configuraciones que requieren reconciliación.
  
Si ha realizado cambios no confirmados en la configuración de cualquier página del grupo, los cambios se guardan en el archivo de configuración de voz exportado (. vcfg). Esto le permite realizar cambios en la configuración del enrutamiento de voz durante varias sesiones antes de publicar los cambios. 
  
### <a name="to-export-a-voice-routing-configuration"></a>Para exportar una configuración de enrutamiento de voz

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.
    
2. Abra el panel de control de Skype empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.
    
4. En el menú **Acciones**, haga clic en **Exportar configuración**.
    
5. Especifique una ubicación y un nombre de archivo y, a continuación, haga clic en **Guardar**.
    
### <a name="to-import-a-voice-routing-configuration"></a>Para importar una configuración de enrutamiento de voz

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.
    
2. Abra el panel de control de Skype empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.
    
4. En el menú **Acciones**, haga clic en **Importar configuración**.
    
5. Busque el archivo de configuración que desee importar y, a continuación, haga clic en **Abrir**.
    
6. Haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    
    > [!NOTE]
    > Siempre que importe un archivo de configuración de voz, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, vea [publicar cambios pendientes en la configuración de enrutamiento de voz en Skype empresarial](voice-route-config-changes.md) en la documentación de operaciones.
  

