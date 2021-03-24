---
title: Instalar y crear bases de datos
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
ROBOTS: NOINDEX, NOFOLLOW
description: Seleccione las bases de datos que desee crear para la implementación. De forma predeterminada, la base de datos se creará en el SQL Server definido en el sitio definido y se implementarán y configurarán automáticamente los archivos de base de datos en función del SQL Server en el que se colocan las bases de datos.
ms.openlocfilehash: 160b42e510fc54b3f03375a0c86bc9f6bdf83f5f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100056"
---
# <a name="install-and-create-databases"></a>Instalar y crear bases de datos

Seleccione las bases de datos que desee crear para la implementación. De forma predeterminada, la base de datos se creará en el SQL Server definido en el sitio definido y se implementarán y configurarán automáticamente los archivos de base de datos en función del SQL Server en el que se colocan las bases de datos.

 **Seleccione las bases de datos que desee crear**: seleccione la casilla de verificación de todas las bases de datos que tiene la intención de implementar y configurar. Seleccione la casilla de verificación de todas las bases de datos que desee implementar.

> [!CAUTION]
> El SQL Server debe haber sido configurado para la instancia (si existe) y los puertos de firewall deben abrirse para dar cabida a la instancia en la que se implementan las bases de datos. Para obtener más información, vea [Configure SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server)

 **Avanzado:** haga clic en el SQL Server y haga clic en el **botón** Opciones avanzadas para elegir opciones para las ubicaciones de archivos de base de datos en su SQL Server. Para más información sobre la ubicación avanzada del archivo de la base de datos, consulte [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell)

 **Atrás**: al hacer clic en este botón el usuario vuelve a la pantalla anterior (puede que no siempre esté disponible, en función de cómo haya llegado a este cuadro de diálogo).

 **Siguiente**: al hacer clic en este botón se confirma la selección del cuadro de diálogo actual y se abre el siguiente cuadro de diálogo que permite configurar la información adicional

 **Cancelar**: al hacer clic en este botón se sale de la configuración y se descartan los cambios. Algunas pantallas de configuración, aunque no todas, le pedirán si desea salir y descartar los cambios. Si selecciona **Sí,** se cerrará la configuración actual, se cerrará la configuración actual y se devolverá al Generador de topologías. Si selecciona **No** el usuario volverá al cuadro de diálogo de configuración actual desde el que podrá continuar con la configuración.

 **Ayuda**: al hacer clic en el botón **Ayuda** aparece esta información de ayuda relacionada con el cuadro de diálogo de configuración actual.