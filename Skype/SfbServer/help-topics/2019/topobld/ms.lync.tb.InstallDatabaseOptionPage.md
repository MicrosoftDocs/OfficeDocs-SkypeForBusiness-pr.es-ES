---
title: Instalar página de opciones de base de datos
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
ROBOTS: NOINDEX, NOFOLLOW
description: 'Configurar opciones avanzadas para la ubicación de archivos de registro y base de datos en SQL Server. Las opciones disponibles son:'
ms.openlocfilehash: 1ef0ba28adb8bbd164fbe9bc24b85430202a5143
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21064860"
---
# <a name="install-database-options-page"></a>Instalar página de opciones de base de datos
 
Configurar opciones avanzadas para la ubicación de archivos de registro y base de datos en SQL Server. Las opciones disponibles son:
  
> [!IMPORTANT]
> Seleccione la opción que mejor se adapte a sus necesidades y directivas relacionadas con la ubicación de archivos de datos y de registro en los equipos de SQL Server. 
  
 **Determinar automáticamente la ubicación del archivo de base de datos**: la opción predeterminada usa un algoritmo que determina el espacio disponible en el servidor SQL Server y distribuye la base de datos y archivos de registro para un rendimiento óptimo.
  
 **Valores predeterminados de instancia de SQL Server de uso**: seleccione esta opción para colocar el archivo de base de datos y los archivos en función de la configuración de instancia de SQL Server de registro. Normalmente, las opciones son administradas y configuradas por el Administrador de base de datos.
  
 **Nos estos ruta de acceso en SQL Server de destino**: seleccione esta opción para definir sus propios rutas de acceso para los archivos de registro y base de datos de SQL Server, escriba la ruta de acceso completa a la unidad y la carpeta donde se colocará la base de datos y archivos de registro.
  
> [!IMPORTANT]
> Las rutas de acceso que especifique se pueden modificar en función de los algoritmos de optimización del rendimiento en la instalación. Para obtener información detallada, vea [Base de datos de instalación de uso de Lync Server Management Shell](http://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx). 
  
 **Aceptar**: haga clic en el botón Aceptar para confirmar los cambios.
  
 **Cancelar**: haga clic en Cancelar para descartar los cambios y volver a la pantalla de instalación de base de datos.
  
 **Ayuda**: haga clic en el botón Ayuda para obtener acceso a esta página de ayuda.
  
## <a name="see-also"></a>Vea también

[Ubicación del archivo de registro y de datos de SQL Server](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)