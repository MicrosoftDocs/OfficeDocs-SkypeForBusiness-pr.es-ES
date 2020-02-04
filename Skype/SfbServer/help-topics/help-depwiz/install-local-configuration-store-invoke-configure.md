---
title: Instalar invocación de almacén de configuración local (configurar)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: Para comenzar la instalación de la base de datos que contendrá la copia local de solo lectura del almacén de administración central, seleccione entre recuperar la configuración definida publicada mediante el generador de topologías del centro de ya instalado y configurado. Almacén de administración o leer la configuración definida de otros elementos multimedia. Para un equipo que se encuentra en la red interna de su organización, seleccione recuperar configuración automáticamente del almacén de administración central.
ms.openlocfilehash: dcbcbea9b941c83c28ebce5ba9b65cad1c38be9d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687633"
---
# <a name="install-local-configuration-store-invoke-configure"></a>Instalar invocación de almacén de configuración local (configurar)
 
Para comenzar la instalación de la base de datos que contendrá la copia local de solo lectura del almacén de administración central, seleccione entre recuperar la configuración definida publicada mediante el generador de topologías del centro de ya instalado y configurado. Almacén de administración o leer la configuración definida de otros elementos multimedia. Para un equipo que se encuentra en la red interna de su organización, seleccione **recuperar configuración automáticamente del almacén de administración central**.
  
Si está instalando una réplica del almacén de administración central en un servidor perimetral, puede seleccionar leer la copia exportada del documento de configuración desde un medio portátil, como una unidad flash USB, una unidad de disco duro USB, una unidad de CD-ROM u otros medios. 
  
> [!IMPORTANT]
> Si va a instalar el almacén de configuración local en un servidor perimetral, la información de configuración debe estar en un formato que se haya exportado desde el almacén de administración central ejecutando el cmdlet de Windows PowerShell:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
Una vez que haya seleccionado la opción adecuada, haga clic en **siguiente**.
  

