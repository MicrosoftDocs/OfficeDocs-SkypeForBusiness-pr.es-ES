---
title: Instalar almacén de configuración local
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: Para comenzar la instalación de un nuevo Skype para servidor de rol de servidor empresarial, primero debe instalar al servidor SQL Server local que se va a hospedar el almacén de configuración local. El almacén de configuración local van a actuar como una réplica de sólo lectura de la Skype para el almacén de Administración Central de servidor empresarial (CMS).
ms.openlocfilehash: ab19a45925a25b97e9b1c478c631ee71fe999b83
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20993673"
---
# <a name="install-local-configuration-store"></a>Instalar almacén de configuración local
 
Para comenzar la instalación de un nuevo Skype para servidor de rol de servidor empresarial, primero debe instalar al servidor SQL Server local que se va a hospedar el almacén de configuración local. El almacén de configuración local van a actuar como una réplica de sólo lectura de la Skype para el almacén de Administración Central de servidor empresarial (CMS). Necesita iniciar sesión en el servidor que ejecute el paso **Instalar almacén de configuración local** como administrador local en el equipo, además de ser miembro del grupo RTCUniversalServerAdmins o del grupo RTCUniversalGlobalReadOnlyGroup. Si la instalación se efectúa en un servidor perimetral, no hace falta ser miembro del grupo RTCUniversalServerAdmins ni del grupo RTCUniversalGlobalReadOnlyGroup. El documento de definición de generador de topología se leerán desde el documento exportado definición en lugar de desde el almacén de Administración Central. Para exportar el documento de definición de generador de topologías y ponerlo a disposición de los servidores perimetrales, vea el tema[exportar la topología y copiar a medios externos para la instalación perimetral](http://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).
  
Para empezar la instalación:
  
1. En el Skype para página Business Server, junto a **paso 1: instalar almacén de configuración Local**, haga clic en **Ejecutar**.
    
2. En la página **Configuración del servidor local**, compruebe que esté seleccionada la opción **Recuperar la configuración automáticamente del almacén de administración central** y haga clic en **Siguiente**.
    
3. Una vez completado el proceso de instalación de configuración del servidor local, haga clic en **Finalizar**.
    
> [!NOTE]
> La instalación del servidor SQL local puede tardar un poco. No verá las actualizaciones en progreso en la pantalla de resumen de instalación mientras se instala SQL Server. Si desea supervisar el progreso de la instalación, use el Administrador de tareas para ver el programa de instalación de SQL Server. 
  

