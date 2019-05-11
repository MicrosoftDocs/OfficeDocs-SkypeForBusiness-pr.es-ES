---
title: Instalar almacén de configuración local
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/13/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: Para comenzar la instalación de un nuevo Skype para servidor de funciones de Business Server 2015, primero debe instalar al servidor SQL Server local que se va a hospedar el almacén de configuración local. El almacén de configuración local van a actuar como una réplica de sólo lectura de la Skype para el almacén de Administración Central de servidor empresarial (CMS). Necesita iniciar sesión en el servidor que ejecute el paso Instalar almacén de configuración local como administrador local en el equipo, además de ser miembro del grupo RTCUniversalServerAdmins o del grupo RTCUniversalGlobalReadOnlyGroup. Si la instalación se efectúa en un servidor perimetral, no hace falta ser miembro del grupo RTCUniversalServerAdmins ni del grupo RTCUniversalGlobalReadOnlyGroup. El documento de definición de generador de topología se leerán desde el documento exportado definición en lugar de desde el almacén de Administración Central. Para exportar el documento de definición de generador de topologías y ponerlo a disposición de los servidores perimetrales, vea el tema exportar la topología y copiar a medios externos para la instalación perimetral.
ms.openlocfilehash: c5c06d47b0deb8e82505567750832762a21200e7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33921030"
---
# <a name="install-local-configuration-store"></a>Instalar almacén de configuración local

Para comenzar la instalación de un nuevo Skype para servidor de funciones de Business Server 2015, primero debe instalar al servidor SQL Server local que se va a hospedar el almacén de configuración local. El almacén de configuración local van a actuar como una réplica de sólo lectura de la Skype para el almacén de Administración Central de servidor empresarial (CMS). Necesita iniciar sesión en el servidor que ejecute el paso **Instalar almacén de configuración local** como administrador local en el equipo, además de ser miembro del grupo RTCUniversalServerAdmins o del grupo RTCUniversalGlobalReadOnlyGroup. Si la instalación se efectúa en un servidor perimetral, no hace falta ser miembro del grupo RTCUniversalServerAdmins ni del grupo RTCUniversalGlobalReadOnlyGroup. El documento de definición de generador de topología se leerán desde el documento exportado definición en lugar de desde el almacén de Administración Central. Para exportar el documento de definición de generador de topologías y ponerlo a disposición de los servidores perimetrales, vea el tema [exportar la topología y copiar a medios externos para la instalación perimetral](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).

Para empezar la instalación:

1. En el Skype para página Business Server 2015, junto a **paso 1: instalar almacén de configuración Local**, haga clic en **Ejecutar**.

2. En la página **Configuración del servidor local**, compruebe que esté seleccionada la opción **Recuperar la configuración automáticamente del almacén de administración central** y haga clic en **Siguiente**.

3. Una vez completado el proceso de instalación de configuración del servidor local, haga clic en **Finalizar**.

> [!NOTE]
> La instalación del servidor SQL local puede tardar un poco. No verá las actualizaciones en progreso en la pantalla de resumen de instalación mientras se instala SQL Server. Si desea supervisar el progreso de la instalación, use el Administrador de tareas para ver el programa de instalación de SQL Server.


