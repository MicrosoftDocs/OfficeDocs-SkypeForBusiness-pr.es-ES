---
title: Instalar almacén de configuración local
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/13/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: Para iniciar la instalación de un nuevo servidor de roles de Skype Empresarial Server 2015, primero debe instalar el SQL Server local que hospedará el almacén de configuración local. El almacén de configuración local actuará como una réplica de solo lectura del almacén de administración central (CMS) de Skype Empresarial Server. Debe iniciar sesión en el servidor en el que ejecute el paso Instalar almacén de configuración local como administrador local en el equipo, además de ser miembro del grupo RTCUniversalServerAdmins o del grupo RTCUniversalGlobalReadOnlyGroup. Si la instalación se efectúa en un servidor perimetral, no hace falta ser miembro del grupo RTCUniversalServerAdmins ni del grupo RTCUniversalGlobalReadOnlyGroup. El documento de definición del Generador de topologías se leerá desde el documento de definición exportado en lugar del almacén de administración central. Para exportar el documento de definición del Generador de topologías y que esté disponible para los servidores perimetrales, consulte el tema Export Your Topology and Copy It to External Media for Edge Installation.
ms.openlocfilehash: 630a3682d3dd5ca12381d5f5b549bb22121b579e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827150"
---
# <a name="install-local-configuration-store"></a>Instalar almacén de configuración local

Para iniciar la instalación de un nuevo servidor de roles de Skype Empresarial Server 2015, primero debe instalar el SQL Server local que hospedará el almacén de configuración local. El almacén de configuración local actuará como una réplica de solo lectura del almacén de administración central (CMS) de Skype Empresarial Server. Debe iniciar sesión en el servidor en el que ejecute el paso **Instalar almacén de configuración local** como administrador local en el equipo, además de ser miembro del grupo RTCUniversalServerAdmins o del grupo RTCUniversalGlobalReadOnlyGroup. Si la instalación se efectúa en un servidor perimetral, no hace falta ser miembro del grupo RTCUniversalServerAdmins ni del grupo RTCUniversalGlobalReadOnlyGroup. El documento de definición del Generador de topologías se leerá desde el documento de definición exportado en lugar del almacén de administración central. Para exportar el documento de definición del Generador de topologías y que esté disponible para los servidores perimetrales, consulte el tema [Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).

Para empezar la instalación:

1. En la página de Skype Empresarial Server 2015, junto a **Paso 1:** Instalar almacén de configuración local, haga clic en **Ejecutar**.

2. En la página **Configuración del servidor local**, compruebe que esté seleccionada la opción **Recuperar la configuración automáticamente del almacén de administración central** y haga clic en **Siguiente**.

3. Una vez completado el proceso de instalación de configuración del servidor local, haga clic en  **Finalizar**.

> [!NOTE]
> La instalación de las SQL Server local puede tardar algún tiempo. No verá actualizaciones en curso en la pantalla de resumen de la instalación mientras SQL Server se está instalando. Si desea supervisar el progreso de la instalación, use el Administrador de tareas para ver el SQL Server instalación.


