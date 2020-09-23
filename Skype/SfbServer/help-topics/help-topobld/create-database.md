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
- CSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: El generador de topologías proporciona una forma de instalar bases de datos en un almacén de SQL Server. Cuando se instalan las bases de datos mediante el generador de topologías, la aplicación lee la información de la topología y, a continuación, instala las bases de datos necesarias en el equipo de SQL Server especificado o en el clúster de SQL Server. Es el único tipo de instalación de bases de datos disponible mediante Topology Builder. Si necesita instalar una base de datos específica en un equipo específico, o si debe instalar una base de datos combinada, debe usar la interfaz de línea de comandos de Windows PowerShell y el cmdlet install-CsDatabase en su lugar.
ms.openlocfilehash: ea7daab44c6075e40e3f8a1b900fe43b84048ed5
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219511"
---
# <a name="create-database"></a>Crear base de datos
 
El generador de topologías proporciona una forma de instalar bases de datos en un almacén de SQL Server. Cuando se instalan las bases de datos mediante el generador de topologías, la aplicación lee la información de la topología y, a continuación, instala las bases de datos necesarias en el equipo de SQL Server especificado o en el clúster de SQL Server. Es el único tipo de instalación de bases de datos disponible mediante Topology Builder. Si necesita instalar una base de datos específica en un equipo específico, o si debe instalar una base de datos combinada, debe usar la interfaz de línea de comandos de Windows PowerShell y el cmdlet [install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) en su lugar.
  
### <a name="creating-a-database"></a>Creación de una base de datos

1. Haga clic en el nodo Skype empresarial Server 2015 y, a continuación, haga clic en **instalar base de datos**.
    
2. En el cuadro de diálogo **instalar bases** de datos, en la página **crear base de datos** , seleccione el nombre de dominio completo (FQDN) del almacén de SQL Server en el que se van a crear las bases de datos nuevas.
    
3. Haga clic en **Avanzadas**. En el cuadro de diálogo de **selección de la ubicación del archivo de base de datos**, seleccione una de las opciones siguientes:
    
   - **Automatically determine database file location**. Si selecciona esta opción, Topology Builder usa un algoritmo integrado para elegir la ubicación de almacenamiento para los registros de las bases de datos y los archivos de datos.
    
   - **Use SQL Server instance defaults**. Si selecciona esta opción, no se usa el algoritmo integrado para elegir las ubicaciones de almacenamiento para los registros de las bases de datos y los archivos de datos. Por el contrario, los archivos de datos y registros se almacenan en las ubicaciones especificadas por las rutas de acceso predeterminadas de SQL Server (estas rutas debe configurarlas previamente un administrador de SQL Server). Los archivos de datos se almacenarán en la ubicación de archivos de datos de SQL Server predeterminada, mientras que los archivos de registro se almacenarán en la ubicación de archivos de registro de SQL Server predeterminada.
    
4. Haga clic en **Aceptar**.
    
5. En la página **Crear base de datos**, haga clic en **Siguiente**.
    
6. En la página que indica que **ha finalizado la creación de la base de datos**, haga clic en **Finalizar**.
    

