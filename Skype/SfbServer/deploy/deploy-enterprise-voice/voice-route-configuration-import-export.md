---
title: Exportar o importar un archivo de configuración de ruta de voz en Skype Empresarial
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Resumen: obtenga información sobre cómo exportar o importar un archivo de configuración de enrutamiento de voz en Skype Empresarial Server mediante el Panel de control Skype Empresarial Server voz.'
ms.openlocfilehash: 7b3b0ae7e7fe49b645fd5a6ee6b6b4d9fcc1affd
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773230"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>Exportar o importar un archivo de configuración de ruta de voz en Skype Empresarial
 
**Resumen:** Obtenga información sobre cómo exportar o importar un archivo de configuración de enrutamiento de voz en Skype Empresarial Server mediante el Panel de control Skype Empresarial Server voz.
  
Si desea guardar la configuración de enrutamiento de voz sin publicarla, siga estos pasos para guardar y recuperar una instantánea de la configuración de enrutamiento de voz. 
  
Al importar un archivo de configuración de enrutamiento de voz (.vcfg), pero se han realizado cambios  en la configuración de enrutamiento de voz en el servidor mientras tanto, las páginas del grupo Enrutamiento de voz en el Panel de control de Skype Empresarial Server indicarán que hay cambios no confirmados en el enrutamiento de voz. Estos cambios sin confirmar son distintos entre dos configuraciones que requieren reconciliación.
  
Si ha realizado cambios no confirmados en la configuración de cualquier página del grupo, los cambios se guardan en el archivo de configuración de voz exportado (.vcfg). Esto le permite realizar cambios de configuración de enrutamiento de voz durante varias sesiones antes de publicar los cambios. 
  
### <a name="to-export-a-voice-routing-configuration"></a>Para exportar una configuración de enrutamiento de voz

1. Inicie sesión en el equipo como un miembro del grupo RTCUniversalServerAdmins o bien, como un miembro de la función administrativa **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.
    
2. Abra Skype Empresarial Server Panel de control.
    
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.
    
4. En el menú **Acciones**, haga clic en **Exportar configuración**.
    
5. Especifique una ubicación y un nombre de archivo y, a continuación, haga clic en **Guardar**.
    
### <a name="to-import-a-voice-routing-configuration"></a>Para importar una configuración de enrutamiento de voz

1. Inicie sesión en el equipo como un miembro del grupo RTCUniversalServerAdmins o bien, como un miembro de la función administrativa **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.
    
2. Abra Skype Empresarial Server Panel de control.
    
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.
    
4. En el **menú Acciones,** haga clic **en Importar configuración**.
    
5. Busque el archivo de configuración que desea importar y, a continuación, haga clic **en Abrir**.
    
6. Haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    
    > [!NOTE]
    > Siempre que importe un archivo de configuración de voz, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, [vea Publicar cambios pendientes](voice-route-config-changes.md) en la configuración de enrutamiento de voz en Skype Empresarial en la documentación de operaciones.
  

