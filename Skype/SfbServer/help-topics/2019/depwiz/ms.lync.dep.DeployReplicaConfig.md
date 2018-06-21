---
title: Invocar el almacén de configuración de instalación Local (configurar)
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: Para comenzar la instalación de la base de datos que contendrá la copia local de sólo lectura del almacén de Administración Central, seleccione uno de recuperar la configuración definida publicada mediante Topology Builder desde la Central ya instalado y configurado Almacén de administración, o leer la configuración definida de otro medio. Para un equipo que se encuentra en la red interna de la organización, seleccione recuperar la configuración automáticamente en el almacén de Administración Central.
ms.openlocfilehash: 4a061ddec04e2b80412b8e60badb8600633093d9
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/20/2018
ms.locfileid: "19980005"
---
# <a name="install-local-configuration-store-invoke-configure"></a>Invocar el almacén de configuración de instalación Local (configurar)
 
Para comenzar la instalación de la base de datos que contendrá la copia local de sólo lectura del almacén de Administración Central, seleccione uno de recuperar la configuración definida publicada mediante Topology Builder desde la Central ya instalado y configurado Almacén de administración, o leer la configuración definida de otro medio. Para un equipo que se encuentra en la red interna de la organización, seleccione **recuperar la configuración automáticamente el almacén de Administración Central**.
  
Si va a instalar una réplica del almacén de Administración Central en un servidor perimetral, seleccione para leer la copia del documento de configuración exportada desde los medios portátiles, como una unidad flash USB, unidad de disco duro USB, CD-ROM u otros medios. 
  
> [!IMPORTANT]
> Si va a instalar el almacén de configuración Local en un servidor perimetral, la información de configuración debe estar en un formato que se han exportado desde la Administración Central almacén ejecutando el cmdlet de Windows PowerShell:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
Después de haber seleccionado la opción adecuada, haga clic en **siguiente**.
  

