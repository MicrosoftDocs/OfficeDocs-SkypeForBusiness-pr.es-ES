---
title: Instalar invocación de almacén de configuración local (configurar)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
ROBOTS: NOINDEX, NOFOLLOW
description: Para comenzar la instalación de la base de datos que contendrá la copia local de sólo lectura del almacén de Administración Central, seleccione uno de recuperar la configuración definida publicada mediante Topology Builder desde la Central ya instalado y configurado Almacén de administración, o leer la configuración definida de otro medio. Para un equipo que se encuentra en la red interna de la organización, seleccione recuperar la configuración automáticamente en el almacén de Administración Central.
ms.openlocfilehash: 20c53827797fb57f1d5d388d95fa2cfbf63f9311
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893605"
---
# <a name="install-local-configuration-store-invoke-configure"></a>Instalar invocación de almacén de configuración local (configurar)
 
Para comenzar la instalación de la base de datos que contendrá la copia local de sólo lectura del almacén de Administración Central, seleccione uno de recuperar la configuración definida publicada mediante Topology Builder desde la Central ya instalado y configurado Almacén de administración, o leer la configuración definida de otro medio. Para un equipo que se encuentra en la red interna de la organización, seleccione **recuperar la configuración automáticamente el almacén de Administración Central**.
  
Si va a instalar una réplica del almacén de Administración Central en un servidor perimetral, seleccione para leer la copia del documento de configuración exportada desde los medios portátiles, como una unidad flash USB, unidad de disco duro USB, CD-ROM u otros medios. 
  
> [!IMPORTANT]
> Si va a instalar el almacén de configuración Local en un servidor perimetral, la información de configuración debe estar en un formato que se han exportado desde la Administración Central almacén ejecutando el cmdlet de Windows PowerShell:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
Después de haber seleccionado la opción adecuada, haga clic en **siguiente**.
  

