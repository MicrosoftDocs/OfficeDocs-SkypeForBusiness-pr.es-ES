---
title: Página de opción Instalar base de datos
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
description: 'Puede configurar opciones avanzadas para la colocación de archivos de base de datos y registro en su SQL Server. Las opciones disponibles son:'
ms.openlocfilehash: 2d62ab7d8662b2f3e0ad2a46c303bd8d097d9a4d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62388218"
---
# <a name="install-database-options-page"></a>Página de opción Instalar base de datos

Puede configurar opciones avanzadas para la colocación de archivos de base de datos y registro en su SQL Server. Las opciones disponibles son:

> [!IMPORTANT]
> Seleccione la opción que mejor se adapte a sus requisitos y directivas relacionados con la ubicación de datos y archivos de registro en los SQL Server equipos.

 **Determinar automáticamente la** ubicación del archivo de base de datos: la opción predeterminada usa un algoritmo que determina el espacio disponible en el SQL Server y distribuye los archivos de base de datos y registro para un rendimiento óptimo.

 **Use SQL Server predeterminadas** de instancia: seleccione esta opción para colocar archivos de base de datos y archivos de registro en función de la configuración de la instancia en SQL Server. El administrador de la base de datos es quien administra y configura normalmente las opciones.

 **Esta** ruta de acceso en el SQL Server de destino: seleccione esta opción para definir sus propias rutas de acceso para los archivos de registro y base de datos de SQL Server escribiendo la ruta de acceso completa a la unidad y la carpeta donde se colocarán los archivos de registro y la base de datos.

> [!IMPORTANT]
> Las rutas de acceso que se introducen pueden modificarse según los algoritmos de optimización del rendimiento durante la instalación. Para obtener más información, consulte [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell).

 **Aceptar**: haga clic en el botón Aceptar para confirmar los cambios.

 **Cancelar**: haga clic en Cancelar para descartar los cambios y volver a la pantalla de instalación de la base de datos.

 **Ayuda**: haga clic en el botón Ayuda para obtener acceso a esta página de Ayuda.

## <a name="see-also"></a>Vea también

[Colocación del archivo de registro y los datos de SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)