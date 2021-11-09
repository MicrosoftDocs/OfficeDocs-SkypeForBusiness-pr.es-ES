---
title: Instalar almacén de configuración local (invocar) (configurar)
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
ROBOTS: NOINDEX, NOFOLLOW
description: Para iniciar la instalación de la base de datos que va a contener la copia de solo lectura local del almacén de administración central, seleccione entre recuperar la configuración definida publicada mediante el Generador de topologías del almacén de administración central ya instalado y configurado, o leer la configuración definida desde otros medios. Para un equipo que se encuentra en la red interna de su organización, seleccione Recuperar configuración automáticamente desde el Almacén de administración central.
ms.openlocfilehash: 6c60656161998e0a99af33d3ddf9e2c3120d82cf
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60853594"
---
# <a name="install-local-configuration-store-invoke-configure"></a>Instalar almacén de configuración local (invocar) (configurar)
 
Para iniciar la instalación de la base de datos que va a contener la copia de solo lectura local del almacén de administración central, seleccione entre recuperar la configuración definida publicada mediante el Generador de topologías del almacén de administración central ya instalado y configurado, o leer la configuración definida desde otros medios. Para un equipo que se encuentra en la red interna de la organización, seleccione Recuperar la configuración **automáticamente desde el Almacén de administración central**.
  
Si va a instalar una réplica del almacén de administración central en un servidor perimetral, necesita seleccionar que se lea la copia exportada del documento de configuración en el medio portátil, por ejemplo una unidad Flash USB, una unidad de disco duro USB, un CD-ROM, etcétera. 
  
> [!IMPORTANT]
> Si va a instalar el almacén de configuración local en un servidor perimetral, la información de configuración debe estar en un formato que se exportó desde el almacén de administración central ejecutando el cmdlet Windows PowerShell servidor:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
Tras haber seleccionado la opción pertinente, haga clic en **Siguiente**.
  

