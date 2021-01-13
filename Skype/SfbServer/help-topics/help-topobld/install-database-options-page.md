---
title: Página de opción Instalar base de datos
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
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
description: 'Configure opciones avanzadas para la colocación de archivos de base de datos y de registro en su SQL Server. Las opciones disponibles son:'
ms.openlocfilehash: f9c2553fb0a4fa8f538a70a2ce496eaf054a0dc4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806920"
---
# <a name="install-database-options-page"></a>Página de opción Instalar base de datos

Configure opciones avanzadas para la colocación de archivos de base de datos y de registro en su SQL Server. Las opciones disponibles son:

> [!IMPORTANT]
> Selecciona la opción que mejor se adapte a tus requisitos y directivas relativas a la ubicación de archivos de registro y datos en los SQL Server equipos.

 **Determinar automáticamente la** ubicación del archivo de base de datos: la opción predeterminada usa un algoritmo que determina el espacio disponible en el SQL Server y distribuye los archivos de registro y base de datos para obtener un rendimiento óptimo.

 **Use SQL Server de instancia** predeterminada: seleccione esta opción para colocar archivos de base de datos y archivos de registro en función de la configuración de la instancia en SQL Server. El administrador de la base de datos es quien administra y configura normalmente las opciones.

 **Us these path on target SQL Server:** Select this option to define your own paths for SQL Server database and log files by typing the full path to the drive and folder where the database and log files will be placed.

> [!IMPORTANT]
> Las rutas de acceso que se introducen pueden modificarse según los algoritmos de optimización del rendimiento durante la instalación. Para obtener más información, consulte [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).

 **Aceptar**: haga clic en el botón Aceptar para confirmar los cambios.

 **Cancelar**: haga clic en Cancelar para descartar los cambios y volver a la pantalla de instalación de la base de datos.

 **Ayuda**: haga clic en el botón Ayuda para obtener acceso a esta página de Ayuda.

## <a name="see-also"></a>Vea también

[Colocación del archivo de registro y los datos de SQL Server](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
