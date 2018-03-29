---
title: Exportar o importar un archivo de configuración de enrutamiento de voz en Skype Empresarial 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Resumen: Conozca cómo exportar o importar un archivo de configuración de enrutamiento de voz de Skype para Business Server 2015 mediante el Skype para el Panel de Control de servidor empresarial.'
ms.openlocfilehash: 8b676ac6417c172402c231401ea9284fccbb8d97
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business-2015"></a>Exportar o importar un archivo de configuración de enrutamiento de voz en Skype Empresarial 2015
 
**Resumen:** Aprenda a exportar o importar un archivo de configuración de enrutamiento de voz de Skype para Business Server 2015 mediante el Skype para el Panel de Control de servidor empresarial.
  
Si desea guardar la configuración del enrutamiento de voz sin publicarla, siga los pasos de este tema para guardar y recuperar una instantánea de la configuración del enrutamiento de voz. 
  
Cuando importa un archivo de configuración de enrutamiento voz (.vcfg), pero los cambios realizados a la voz configuración de enrutamiento en el servidor mientras tanto, las páginas en el grupo de **Enrutamiento de voz** de Skype para el Panel de Control de servidor de negocios indicará existe son cambios no confirmados para el enrutamiento de voz. Estos cambios no confirmados son las diferencias entre las dos configuraciones que requieren reconciliación.
  
Si los cambios no confirmados realizados en la configuración de cualquier página dentro del grupo, los cambios se guardan en el archivo de configuración exportado voz (.vcfg). Esto permite realizar cambios en la configuración de enrutamiento durante varias sesiones antes de publicar los cambios de voz. 
  
### <a name="to-export-a-voice-routing-configuration"></a>Para exportar una configuración de enrutamiento de voz

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.
    
2. Abre Skype para Panel de Control del servidor de empresa.
    
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.
    
4. En el menú **Acciones**, haga clic en **Exportar configuración**.
    
5. Especifique una ubicación y un nombre de archivo y, a continuación, haga clic en **Guardar**.
    
### <a name="to-import-a-voice-routing-configuration"></a>Para importar una configuración de enrutamiento de voz

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.
    
2. Abre Skype para Panel de Control del servidor de empresa.
    
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.
    
4. En el menú **Acciones**, haga clic en **Importar configuración**.
    
5. Busque el archivo de configuración que desee importar y, a continuación, haga clic en **Abrir**.
    
6. Haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    
    > [!NOTE]
    > Siempre que importe un archivo de configuración de voz, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, consulte [publicación de cambios a la configuración de enrutamiento de voz de Skype para el año 2015 de negocios pendientes](voice-route-config-changes.md) en la documentación de las operaciones.
  

