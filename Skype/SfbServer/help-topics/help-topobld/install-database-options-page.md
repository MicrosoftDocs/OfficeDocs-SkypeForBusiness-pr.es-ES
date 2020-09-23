---
title: Página de opción Instalar base de datos
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
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
description: 'Configure las opciones avanzadas para la ubicación de la base de datos y los archivos de registro en SQL Server. Las opciones disponibles son:'
ms.openlocfilehash: 4c8c456aa1fd0e9eee150e184b4d1f7934c26b65
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215311"
---
# <a name="install-database-options-page"></a>Página de opción Instalar base de datos

Configure las opciones avanzadas para la ubicación de la base de datos y los archivos de registro en SQL Server. Las opciones disponibles son:

> [!IMPORTANT]
> Seleccione la opción que mejor se adapte a sus necesidades y directivas relativas a la ubicación de los datos y el archivo de registro en los equipos con SQL Server.

 **Determinar automáticamente la ubicación del archivo de base de datos**: la opción predeterminada usa un algoritmo que determina el espacio disponible en el servidor SQL Server y distribuye los archivos de registro y de base de datos para obtener un rendimiento óptimo.

 **Usar valores predeterminados de instancia de SQL Server**: Seleccione esta opción para ubicar los archivos de base de datos y de registro en función de la configuración de la instancia de SQL Server. El administrador de la base de datos es quien administra y configura normalmente las opciones.

 **Nuestra ruta en SQL Server de destino**: Seleccione esta opción para definir sus propias rutas para la base de datos y los archivos de registro de SQL Server; para ello, escriba la ruta de acceso completa de la unidad y la carpeta donde se colocarán los archivos de registro y la base de datos.

> [!IMPORTANT]
> Las rutas de acceso que se introducen pueden modificarse según los algoritmos de optimización del rendimiento durante la instalación. Para obtener más información, consulte [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).

 **Aceptar**: haga clic en el botón Aceptar para confirmar los cambios.

 **Cancelar**: haga clic en Cancelar para descartar los cambios y volver a la pantalla de instalación de la base de datos.

 **Ayuda**: haga clic en el botón Ayuda para obtener acceso a esta página de Ayuda.

## <a name="see-also"></a>Vea también

[Colocación del archivo de registro y los datos de SQL Server](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
