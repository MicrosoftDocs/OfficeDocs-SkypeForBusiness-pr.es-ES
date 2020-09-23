---
title: Instalar y crear bases de datos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: Seleccione las bases de datos que desee crear para la implementación. De forma predeterminada, la base de datos se creará en el servidor SQL Server definido en el sitio definido e implementará y configurará automáticamente los archivos de base de datos en función del SQL Server en el que esté colocando las bases de datos.
ms.openlocfilehash: ade264fcda73df408f6bb323dd1e3733ccdd45f1
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215391"
---
# <a name="install-and-create-databases"></a>Instalar y crear bases de datos

Seleccione las bases de datos que desee crear para la implementación. De forma predeterminada, la base de datos se creará en el servidor SQL Server definido en el sitio definido e implementará y configurará automáticamente los archivos de base de datos en función del SQL Server en el que esté colocando las bases de datos.

 **Seleccione las bases de datos que desee crear **: seleccione la casilla de verificación de todas las bases de datos que tiene la intención de implementar y configurar. Seleccione la casilla de verificación de todas las bases de datos que desee implementar.

> [!CAUTION]
> SQL Server ya debe estar configurado para la instancia (si existe) y los puertos de Firewall deben estar abiertos para acomodar la instancia en la que está implementando las bases de datos. Para más información, consulte [Configure SQL Server for Lync Server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)

 **Avanzadas**: haga clic en SQL Server y haga clic en el botón **avanzadas** para elegir las opciones de las ubicaciones de los archivos de base de datos en SQL Server. Para más información sobre la ubicación avanzada del archivo de la base de datos, consulte [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)

 **Atrás**: al hacer clic en este botón el usuario vuelve a la pantalla anterior (puede que no siempre esté disponible, en función de cómo haya llegado a este cuadro de diálogo).

 **Siguiente**: al hacer clic en este botón se confirma la selección del cuadro de diálogo actual y se abre el siguiente cuadro de diálogo que permite configurar la información adicional

 **Cancelar**: al hacer clic en este botón se sale de la configuración y se descartan los cambios. Algunas pantallas de configuración, aunque no todas, le pedirán si desea salir y descartar los cambios. Si selecciona **sí** , se cerrará la configuración actual y se cerrará la configuración actual y se le devolverá al generador de topologías. Si selecciona **No** el usuario volverá al cuadro de diálogo de configuración actual desde el que podrá continuar con la configuración.

 **Ayuda**: al hacer clic en el botón **Ayuda** aparece esta información de ayuda relacionada con el cuadro de diálogo de configuración actual.


