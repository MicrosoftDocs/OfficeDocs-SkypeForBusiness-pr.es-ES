---
title: Instalar almacén de configuración local
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: Para comenzar la instalación de un nuevo servidor de Skype Empresarial Server de roles, primero debe instalar el SQL Server local que hospedará el almacén de configuración local. El almacén de configuración local actuará como una réplica de solo lectura del Skype Empresarial Server de administración central (CMS).
ms.openlocfilehash: 82e82bc87a20f1bd4c86c4aa7c3e8c6bc8858c1b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859577"
---
# <a name="install-local-configuration-store"></a>Instalar almacén de configuración local

Para comenzar la instalación de un nuevo servidor de Skype Empresarial Server de roles, primero debe instalar el SQL Server local que hospedará el almacén de configuración local. El almacén de configuración local actuará como una réplica de solo lectura del Skype Empresarial Server de administración central (CMS). Debe iniciar sesión en el servidor en el que ejecute el paso **Instalar almacén de configuración local** como administrador local en el equipo, además de ser miembro del grupo RTCUniversalServerAdmins o del grupo RTCUniversalGlobalReadOnlyGroup. Si la instalación se efectúa en un servidor perimetral, no hace falta ser miembro del grupo RTCUniversalServerAdmins ni del grupo RTCUniversalGlobalReadOnlyGroup. El documento de definición del Generador de topologías se leerá del documento de definición exportado en lugar del almacén de administración central. Para exportar el documento de definición del Generador de topologías y hacerlo disponible para los servidores perimetrales, vea el tema[Export Your Topology and Copy It to External Media for Edge Installation](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation).

Para empezar la instalación:

1. En la Skype Empresarial Server, junto a **Paso 1: Instalar almacén de configuración local**, haga clic en **Ejecutar**.

2. En la página **Configuración del servidor local**, compruebe que esté seleccionada la opción **Recuperar la configuración automáticamente del almacén de administración central** y haga clic en **Siguiente**.

3. Una vez completado el proceso de instalación de configuración del servidor local, haga clic en  **Finalizar**.

> [!NOTE]
> La instalación del SQL Server local puede tardar algún tiempo. No verá actualizaciones sobre el progreso en la pantalla de resumen de instalación mientras SQL Server se está instalando. Si desea supervisar el progreso de la instalación, use el Administrador de tareas para ver el SQL Server instalación.