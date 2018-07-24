---
title: Crear base de datos
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
ROBOTS: NOINDEX, NOFOLLOW
description: Generador de topología proporciona una forma de instalar las bases de datos en un almacén de SQL Server. Al instalar las bases de datos mediante el uso de Topology Builder, la aplicación lee información de la topología y, a continuación, instala las bases de datos necesarios en el equipo de SQL Server especificado o el clúster de SQL Server. Se trata del único tipo de instalación de bases de datos disponible mediante el Generador de topologías. Si es necesario instalar una base de datos específica en un equipo específico, o si se debe instalar una base de datos combinada, debe usar el cmdlet Install-CsDatabase e interfaz de línea de comandos de Windows PowerShell en su lugar.
ms.openlocfilehash: 087bed64e0e1d53cd610433c5695899107a9aa71
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21066115"
---
# <a name="create-database"></a>Crear base de datos
 
Generador de topología proporciona una forma de instalar las bases de datos en un almacén de SQL Server. Al instalar las bases de datos mediante el uso de Topology Builder, la aplicación lee información de la topología y, a continuación, instala las bases de datos necesarios en el equipo de SQL Server especificado o el clúster de SQL Server. Se trata del único tipo de instalación de bases de datos disponible mediante el Generador de topologías. Si es necesario instalar una base de datos específica en un equipo específico, o si se debe instalar una base de datos combinada, debe usar el cmdlet [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) e interfaz de línea de comandos de Windows PowerShell en su lugar.
  
### <a name="creating-a-database"></a>Creación de una base de datos

1. Haga clic en el Skype para el nodo de servidor empresarial y, a continuación, haga clic en **Instalar base de datos**.
    
2. En el cuadro de diálogo **Instalar bases de datos** , en la página **Crear base de datos** , seleccione el nombre de dominio completo (FQDN) del almacén de SQL Server donde están las nuevas bases de datos que se creará.
    
3. Haga clic en **Opciones avanzadas**. En el cuadro de diálogo **Seleccionar la ubicación de los archivos de base de datos**, seleccione una de las siguientes opciones:
    
  - **Ubicar automáticamente los archivos de base de datos**. Si selecciona esta opción, el Generador de topologías usa un algoritmo integrado para elegir la ubicación de almacenamiento de los registros de bases de datos y los archivos de datos.
    
  - **Valores predeterminados de instancia de utilizar SQL Server**. Si selecciona esta opción, no se usa el algoritmo integrado para elegir las ubicaciones de almacenamiento para los registros de la base de datos y archivos de datos. En su lugar, los archivos de registro y datos se almacenan en las ubicaciones especificadas por la ruta de acceso de valores predeterminados de SQL Server (estas rutas de acceso deben estar configurados en avanzada por un administrador de SQL Server). Los archivos de datos se almacenará en la ubicación predeterminada del archivo de datos de SQL Server, mientras que los archivos de registro se almacenará en la ubicación predeterminada del archivo de registro de SQL Server.
    
4. Haga clic en **Aceptar**.
    
5. En la página **Crear base de datos**, haga clic en **Siguiente**.
    
6. En la página **Creación de base de datos completada**, haga clic en **Finalizar**.
    

