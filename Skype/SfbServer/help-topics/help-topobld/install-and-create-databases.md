---
title: Instalar y crear bases de datos
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Seleccione las bases de datos que desee crear para la implementación. De forma predeterminada, la base de datos se creará en el SQL Server definido en el sitio definido y se implementarán y configurarán automáticamente los archivos de base de datos en función del SQL Server en el que se colocan las bases de datos.
ms.openlocfilehash: 1a26353ed44529cd19f94b70fdf25f72fbd8f8d4bb81aa0da41c523d3d35a500
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281063"
---
# <a name="install-and-create-databases"></a>Instalar y crear bases de datos

Seleccione las bases de datos que desee crear para la implementación. De forma predeterminada, la base de datos se creará en el SQL Server definido en el sitio definido y se implementarán y configurarán automáticamente los archivos de base de datos en función del SQL Server en el que se colocan las bases de datos.

 **Seleccione las bases de datos que desee crear**: seleccione la casilla de verificación de todas las bases de datos que tiene la intención de implementar y configurar. Seleccione la casilla de verificación de todas las bases de datos que desee implementar.

> [!CAUTION]
> El SQL Server debe estar configurado para la instancia (si la hubiera) y los puertos de firewall deben abrirse para dar cabida a la instancia en la que se implementan las bases de datos. Para más información, consulte [Configure SQL Server for Lync Server 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server)

 **Avanzado:** haga clic en el SQL Server  y haga clic en el botón Avanzadas para elegir opciones para las ubicaciones de archivos de base de datos en su SQL Server. Para más información sobre la ubicación avanzada del archivo de la base de datos, consulte [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell)

 **Atrás**: al hacer clic en este botón el usuario vuelve a la pantalla anterior (puede que no siempre esté disponible, en función de cómo haya llegado a este cuadro de diálogo).

 **Siguiente**: al hacer clic en este botón se confirma la selección del cuadro de diálogo actual y se abre el siguiente cuadro de diálogo que permite configurar la información adicional

 **Cancelar**: al hacer clic en este botón se sale de la configuración y se descartan los cambios. Algunas pantallas de configuración, aunque no todas, le pedirán si desea salir y descartar los cambios. Si selecciona **Sí,** se cerrará la configuración actual, se cerrará la configuración actual y se devolverá al Generador de topologías. Si selecciona **No** el usuario volverá al cuadro de diálogo de configuración actual desde el que podrá continuar con la configuración.

 **Ayuda**: al hacer clic en el botón **Ayuda** aparece esta información de ayuda relacionada con el cuadro de diálogo de configuración actual.