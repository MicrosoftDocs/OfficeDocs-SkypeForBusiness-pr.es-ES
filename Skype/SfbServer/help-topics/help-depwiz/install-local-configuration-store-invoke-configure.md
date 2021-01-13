---
title: Instalar almacén de configuración local (invocar) (configurar)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: Para iniciar la instalación de la base de datos que contendrán la copia local de solo lectura del almacén de administración central, seleccione entre recuperar la configuración definida publicada mediante el Generador de topologías del almacén de administración central ya instalado y configurado, o leer la configuración definida desde otros medios. Para un equipo que se encuentra en la red interna de la organización, selecciona Recuperar configuración automáticamente desde el Almacén de administración central.
ms.openlocfilehash: f0e2f54e83831cf6ad626b5d83cf068f40110f07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827210"
---
# <a name="install-local-configuration-store-invoke-configure"></a>Instalar almacén de configuración local (invocar) (configurar)
 
Para iniciar la instalación de la base de datos que contendrán la copia local de solo lectura del almacén de administración central, seleccione entre recuperar la configuración definida publicada mediante el Generador de topologías del almacén de administración central ya instalado y configurado, o leer la configuración definida desde otros medios. Para un equipo que se encuentra en la red interna de la organización, seleccione Recuperar configuración **automáticamente desde el Almacén de administración central.**
  
Si va a instalar una réplica del almacén de administración central en un servidor perimetral, necesita seleccionar que se lea la copia exportada del documento de configuración en el medio portátil, por ejemplo una unidad Flash USB, una unidad de disco duro USB, un CD-ROM, etcétera. 
  
> [!IMPORTANT]
> Si va a instalar el almacén de configuración local en un servidor perimetral, la información de configuración debe estar en un formato exportado desde el almacén de administración central ejecutando el cmdlet Windows PowerShell local:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
Tras haber seleccionado la opción pertinente, haga clic en **Siguiente**.
  

