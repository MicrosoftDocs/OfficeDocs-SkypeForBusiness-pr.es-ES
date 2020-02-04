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
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
description: 'Configure las opciones avanzadas para la ubicación de la base de datos y los archivos de registro en SQL Server. Las opciones disponibles son las siguientes:'
ms.openlocfilehash: 0abcf0be4c6e7a4d808a7abaaad713c1b35cd37e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697205"
---
# <a name="install-database-options-page"></a>Página de opción Instalar base de datos

Configure las opciones avanzadas para la ubicación de la base de datos y los archivos de registro en SQL Server. Las opciones disponibles son las siguientes:

> [!IMPORTANT]
> Seleccione la opción que mejor se adapte a sus requisitos y políticas relativas a los datos y la ubicación del archivo de registro en los equipos SQL Server.

 **Determinar automáticamente la ubicación del archivo de base de datos**: la opción predeterminada usa un algoritmo que determina el espacio disponible en el servidor SQL Server y distribuye los archivos de registro y de base de datos para obtener un rendimiento óptimo.

 **Usar valores predeterminados de instancia de SQL Server**: Seleccione esta opción para colocar archivos de base de datos y de registro basados en la configuración de la instancia de SQL Server. Las opciones las suele administrar y configurar el administrador de la base de datos.

 **Estas rutas en el servidor SQL Server de destino**: Seleccione esta opción para definir sus propias rutas para la base de datos y los archivos de registro de SQL Server escribiendo la ruta de acceso completa de la unidad y la carpeta donde se colocarán los archivos de registro y la base de datos.

> [!IMPORTANT]
> Las rutas de la sesión se pueden modificar en función de los algoritmos de optimización del rendimiento de la instalación. Para obtener más información, vea [instalación de bases de datos mediante el shell de administración de Lync Server](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).

 **Aceptar**: haga clic en el botón Aceptar para confirmar los cambios.

 **Cancelar**: haga clic en Cancelar para descartar los cambios y volver a la pantalla instalar base de datos.

 **Ayuda**: haga clic en el botón ayuda para acceder a esta página de ayuda.

## <a name="see-also"></a>Vea también

[Ubicación de los archivos de datos y registro de SQL Server](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
