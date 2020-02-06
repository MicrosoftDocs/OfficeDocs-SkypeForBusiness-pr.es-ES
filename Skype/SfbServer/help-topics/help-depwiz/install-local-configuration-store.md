---
title: Instalar almacén de configuración local
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Para comenzar la instalación de un nuevo servidor de roles de Skype empresarial Server 2015, primero debe instalar el servidor SQL Server local que hospedará el almacén de configuración local. El almacén de configuración local actuará como una réplica de solo lectura del almacén de administración central (CMS) de Skype empresarial Server. Necesita iniciar sesión en el servidor que ejecute el paso Instalar almacén de configuración local como administrador local en el equipo, además de ser miembro del grupo RTCUniversalServerAdmins o del grupo RTCUniversalGlobalReadOnlyGroup. Si la instalación se efectúa en un servidor perimetral, no hace falta ser miembro del grupo RTCUniversalServerAdmins ni del grupo RTCUniversalGlobalReadOnlyGroup. El documento de definición del generador de topología se leerá desde el documento de definición exportado en lugar del almacén de administración central. Para exportar el documento de definición del generador de topología y hacer que esté disponible para los servidores perimetrales, vea el tema exportar su topología y copiarla en medios externos para la instalación perimetral.
ms.openlocfilehash: 7908a862a01871988d6afe6ae1b0cf9c752e9d30
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823624"
---
# <a name="install-local-configuration-store"></a>Instalar almacén de configuración local

Para comenzar la instalación de un nuevo servidor de roles de Skype empresarial Server 2015, primero debe instalar el servidor SQL Server local que hospedará el almacén de configuración local. El almacén de configuración local actuará como una réplica de solo lectura del almacén de administración central (CMS) de Skype empresarial Server. Necesita iniciar sesión en el servidor que ejecute el paso **Instalar almacén de configuración local** como administrador local en el equipo, además de ser miembro del grupo RTCUniversalServerAdmins o del grupo RTCUniversalGlobalReadOnlyGroup. Si la instalación se efectúa en un servidor perimetral, no hace falta ser miembro del grupo RTCUniversalServerAdmins ni del grupo RTCUniversalGlobalReadOnlyGroup. El documento de definición del generador de topología se leerá desde el documento de definición exportado en lugar del almacén de administración central. Para exportar el documento de definición del generador de topología y hacer que esté disponible para los servidores perimetrales, vea el tema [exportar su topología y copiarla en medios externos para la instalación perimetral](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).

Para empezar la instalación:

1. En la página de Skype empresarial Server 2015, junto a **STEP1: instalar almacén de configuración local**, haga clic en **Ejecutar**.

2. En la página **Configuración del servidor local**, compruebe que esté seleccionada la opción **Recuperar la configuración automáticamente del almacén de administración central** y haga clic en **Siguiente**.

3. Una vez completado el proceso de instalación de configuración del servidor local, haga clic en **Finalizar**.

> [!NOTE]
> La instalación del servidor SQL Server local puede tardar algún tiempo. No verá actualizaciones en curso en la pantalla Resumen de la instalación mientras se está instalando SQL Server. Si desea supervisar el progreso de la instalación, use el administrador de tareas para ver la configuración de SQL Server.


