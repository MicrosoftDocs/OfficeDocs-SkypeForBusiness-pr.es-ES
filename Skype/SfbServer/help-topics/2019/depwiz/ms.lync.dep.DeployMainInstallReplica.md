---
title: Instalar almacén de configuración local
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: Para comenzar la instalación de un nuevo servidor de roles de Skype empresarial, primero debe instalar el servidor SQL Server local que hospedará el almacén de configuración local. El almacén de configuración local actuará como una réplica de solo lectura del almacén de administración central (CMS) de Skype empresarial Server.
ms.openlocfilehash: 365529c3c9cb15ea50cd6a482bd2a69143daa219
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794799"
---
# <a name="install-local-configuration-store"></a>Instalar almacén de configuración local

Para comenzar la instalación de un nuevo servidor de roles de Skype empresarial, primero debe instalar el servidor SQL Server local que hospedará el almacén de configuración local. El almacén de configuración local actuará como una réplica de solo lectura del almacén de administración central (CMS) de Skype empresarial Server. Necesita iniciar sesión en el servidor que ejecute el paso **Instalar almacén de configuración local** como administrador local en el equipo, además de ser miembro del grupo RTCUniversalServerAdmins o del grupo RTCUniversalGlobalReadOnlyGroup. Si la instalación se efectúa en un servidor perimetral, no hace falta ser miembro del grupo RTCUniversalServerAdmins ni del grupo RTCUniversalGlobalReadOnlyGroup. El documento de definición del generador de topología se leerá desde el documento de definición exportado en lugar del almacén de administración central. Para exportar el documento de definición del generador de topología y hacer que esté disponible para los servidores perimetrales, vea el tema[exportar su topología y copiarla en medios externos para la instalación perimetral](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).

Para empezar la instalación:

1. En la página de Skype empresarial Server, junto a **STEP1: instalar almacén de configuración local**, haga clic en **Ejecutar**.

2. En la página **Configuración del servidor local**, compruebe que esté seleccionada la opción **Recuperar la configuración automáticamente del almacén de administración central** y haga clic en **Siguiente**.

3. Una vez completado el proceso de instalación de configuración del servidor local, haga clic en **Finalizar**.

> [!NOTE]
> La instalación del servidor SQL Server local puede tardar algún tiempo. No verá actualizaciones en curso en la pantalla Resumen de la instalación mientras se está instalando SQL Server. Si desea supervisar el progreso de la instalación, use el administrador de tareas para ver la configuración de SQL Server.


