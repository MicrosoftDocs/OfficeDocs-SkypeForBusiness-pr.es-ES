---
title: Invocar el almacén de configuración de instalación Local (configurar)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: Para comenzar la instalación de la base de datos que contendrá la copia local de sólo lectura del almacén de Administración Central, selecciona entre recuperar la configuración definida publicada mediante el generador de topología desde la Central ya instalado y configurado Almacén de administración o leyendo la configuración definida de otro medio. Para un equipo que está en la red interna de su organización, seleccione Recuperar configuración automáticamente en el almacén de Administración Central.
ms.openlocfilehash: 74269ee40116b91097c77702942f42de9f7d882a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="install-local-configuration-store-invoke-configure"></a>Invocar el almacén de configuración de instalación Local (configurar)
 
Para comenzar la instalación de la base de datos que contendrá la copia local de sólo lectura del almacén de Administración Central, selecciona entre recuperar la configuración definida publicada mediante el generador de topología desde la Central ya instalado y configurado Almacén de administración o leyendo la configuración definida de otro medio. Para un equipo que está en la red interna de su organización, seleccione **Recuperar configuración automáticamente desde el almacén de Administración Central**.
  
Si está instalando una réplica del almacén de Administración Central en un servidor perimetral, seleccione leer la copia del documento de configuración exportada de medios portátiles, como una unidad flash USB, unidad de disco duro USB, CD-ROM u otros medios. 
  
> [!IMPORTANT]
> Si va a instalar el almacén de configuración Local en un servidor perimetral, la información de configuración debe estar en un formato que se exportó desde la Administración Central almacenar ejecutando el cmdlet de Windows PowerShell:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
Después de haber seleccionado la opción adecuada, haga clic en **siguiente**.
  

