---
title: Crear base de datos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: El generador de topología proporciona una forma de instalar bases de datos en un almacén de SQL Server. Al instalar bases de datos con el generador de topología, la aplicación Lee información de la topología y, a continuación, instala las bases de datos necesarias en el equipo SQL Server especificado o en el clúster de SQL Server. Se trata del único tipo de instalación de bases de datos disponible mediante el Generador de topologías. Si necesita instalar una base de datos específica en un equipo específico, o si debe instalar una base de datos ordenada, debe usar la interfaz de línea de comandos de Windows PowerShell y el cmdlet install-CsDatabase en su lugar.
ms.openlocfilehash: 02d754870cb2d2db16424474a68b8ea0245191f7
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684853"
---
# <a name="create-database"></a>Crear base de datos
 
El generador de topología proporciona una forma de instalar bases de datos en un almacén de SQL Server. Al instalar bases de datos con el generador de topología, la aplicación Lee información de la topología y, a continuación, instala las bases de datos necesarias en el equipo SQL Server especificado o en el clúster de SQL Server. Se trata del único tipo de instalación de bases de datos disponible mediante el Generador de topologías. Si necesita instalar una base de datos específica en un equipo específico, o si debe instalar una base de datos ordenada, debe usar la interfaz de línea de comandos de Windows PowerShell y el cmdlet [install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) en su lugar.
  
### <a name="creating-a-database"></a>Creación de una base de datos

1. Haga clic en el nodo de Skype empresarial Server 2015 y, a continuación, haga clic en **instalar base de datos**.
    
2. En el cuadro de diálogo **instalar bases** de datos, en la página **crear base de datos** , seleccione el nombre de dominio completo (FQDN) del almacén SQL Server en el que se van a crear las nuevas bases de datos.
    
3. Haga clic en **Opciones avanzadas**. En el cuadro de diálogo **Seleccionar la ubicación de los archivos de base de datos**, seleccione una de las siguientes opciones:
    
   - **Ubicar automáticamente los archivos de base de datos**. Si selecciona esta opción, el Generador de topologías usa un algoritmo integrado para elegir la ubicación de almacenamiento de los registros de bases de datos y los archivos de datos.
    
   - **Use los valores predeterminados de instancia de SQL Server**. Si selecciona esta opción, el algoritmo integrado no se usa para elegir las ubicaciones de almacenamiento de los archivos de datos y los registros de la base de datos. En su lugar, los archivos de registro y de datos se almacenan en las ubicaciones especificadas por la ruta de acceso de valores predeterminados de SQL Server (estas rutas deben estar configuradas por un administrador de SQL Server). Los archivos de datos se almacenarán en la ubicación predeterminada de los archivos de datos de SQL Server, mientras que los archivos de registro se almacenarán en la ubicación predeterminada del archivo de registro de SQL Server.
    
4. Haga clic en **Aceptar**.
    
5. En la página **Crear base de datos**, haga clic en **Siguiente**.
    
6. En la página **Creación de base de datos completada**, haga clic en **Finalizar**.
    

